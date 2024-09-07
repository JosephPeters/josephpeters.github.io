# Flowise JSON Flow Creation Guidelines

## 1. Overall Structure

A valid Flowise JSON flow consists of two main parts:
- `nodes`: An array of node objects
- `edges`: An array of edge objects connecting the nodes

The flow should be structured from top to bottom, with the final output node at the top and input nodes at the bottom.

## 2. Node Structure

Each node in the `nodes` array should have the following properties:

- `id`: A unique identifier for the node, typically in the format `{nodeName}_{number}` (e.g., "chatOpenAI_0")
- `position`: An object with `x` and `y` coordinates for the node's position in the UI
- `type`: Always set to "customNode" for Flowise nodes
- `data`: An object containing the node's configuration (detailed below)
- `width`: The width of the node in the UI (typically 300)
- `height`: The height of the node in the UI (varies based on complexity, often between 400-550)
- `selected`: Boolean indicating if the node is selected (typically false)
- `positionAbsolute`: An object with `x` and `y` coordinates, usually identical to `position`
- `dragging`: Boolean indicating if the node is being dragged (typically false)

### Node Data Structure

The `data` object within each node should include:

- `id`: Same as the node's `id`
- `label`: Human-readable name of the node
- `version`: Version number of the node type
- `name`: Internal name of the node type
- `type`: The specific type of the node (e.g., "ChatOpenAI", "ConversationalRetrievalQAChain")
- `baseClasses`: Array of classes the node inherits from
- `category`: The category the node belongs to (e.g., "Chat Models", "Chains")
- `description`: A brief description of the node's functionality
- `inputParams`: Array of input parameter objects (detailed below)
- `inputAnchors`: Array of input anchor objects (detailed below)
- `inputs`: Object mapping input names to their values or references to other nodes
- `outputAnchors`: Array of output anchor objects (detailed below)
- `outputs`: Object specifying which outputs are used (often empty `{}`)
- `selected`: Boolean indicating if the node is selected (typically false)

### Input Parameters

Each input parameter object in `inputParams` should include:

- `label`: Human-readable label for the input
- `name`: Internal name of the input
- `type`: Data type of the input (e.g., "string", "number", "options")
- `id`: Unique identifier for the input, typically `{nodeId}-input-{inputName}-{inputType}`
- Additional properties as needed (e.g., `default`, `optional`, `placeholder`)

### Input/Output Anchors

Input and output anchor objects should include:

- `id`: Unique identifier for the anchor
- `name`: Internal name of the anchor
- `label`: Human-readable label for the anchor
- `type`: Data type of the anchor (e.g., "BaseLanguageModel", "VectorStore")

## 3. Edge Structure

Each edge in the `edges` array should have the following properties:

- `source`: ID of the source node
- `sourceHandle`: ID of the output anchor on the source node
- `target`: ID of the target node
- `targetHandle`: ID of the input anchor on the target node
- `type`: Always set to "buttonedge" for Flowise edges
- `id`: Unique identifier for the edge, typically `{sourceId}-{targetId}`

## 4. Node Positioning

- Position nodes vertically from top to bottom, with the final output node at the top
- Space nodes evenly, typically with 400-500 pixels between each node vertically
- Align nodes horizontally, typically around x-coordinate 250-300

## 5. Node Connections

- Ensure that all required inputs for each node are connected to appropriate outputs from other nodes
- Connect nodes in a logical flow, from input sources (bottom) to final output (top)

## 6. Specific Node Types

### Chat Models (e.g., ChatOpenAI)
- Include credential configuration
- Specify model name and parameters like temperature

### Chains (e.g., ConversationalRetrievalQAChain)
- Connect to a language model and a retriever
- Include optional parameters like chain name

### Vector Stores (e.g., Pinecone)
- Include credential configuration
- Specify index name
- Connect to document source and embedding model

### Retrievers (e.g., VectorStoreRetriever)
- Connect to a vector store
- Specify search type and parameters

### Text Splitters
- Specify chunk size and overlap
- Connect to text input source

## 7. Best Practices

- Use descriptive IDs for nodes and edges to improve readability
- Ensure all required connections are made between nodes
- Include all necessary nodes for a functional flow (e.g., embedding models for vector stores)
- Set appropriate default values for optional parameters
- Use consistent naming conventions across the flow

## 8. Validation

Before finalizing the JSON:
- Ensure all node IDs are unique
- Verify that all referenced nodes and anchors in edges exist
- Check that all required inputs for each node are provided or connected
- Validate that the JSON structure is correct and free of syntax errors

By following these guidelines, future LLMs should be able to create valid and functional Flowise JSON flows.
