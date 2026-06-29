# Member Persona & Cohort Knowledge Base

This is an [OKF](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md) bundle (v0.1). It holds the **building blocks** for member personas and cohorts so that humans can read them and agents can traverse them to produce marketing strategy, UX direction, and feature priorities.

The model: a **persona** sits where several **lenses** intersect; each persona is built from reusable **factors**; each factor is backed by a **reference** (a cited source). **Cohorts** size groups of members; **plays** are the marketing/UX/feature moves a persona's needs call for.

# Lenses

The five ways we slice a member. Sizing comes from the first two; behavior from the next two; barriers from the fifth.

* [Line of Business](lenses/line-of-business.md) - Coverage type: Commercial, Medicare Advantage, Medicaid, ACA, Dual-Eligible.
* [Health Status](lenses/health-status.md) - Clinical risk tier: Healthy, Rising-Risk, Chronic, Complex.
* [Life Stage](lenses/life-stage.md) - Life events and demographic moments of truth.
* [Psychographic](lenses/psychographic.md) - How members think, engage, and trust.
* [Social Determinants of Health](lenses/social-determinants.md) - Non-medical barriers; a lens that operates as an overlay.

# Factors

Reusable building-block attributes attached to personas and cohorts.

* [High Digital Adoption](factors/high-digital-adoption.md) - Prefers self-serve, app-first, instant.
* [Low PAM Activation](factors/low-pam-activation.md) - Passive, low confidence managing own health.
* [Caregiver Burden](factors/caregiver-burden.md) - Coordinating care for others alongside their own.
* [Transportation Barrier](factors/transportation-barrier.md) - Cannot reliably reach care (SDOH).
* [Food Insecurity](factors/food-insecurity.md) - Limited reliable access to adequate food (SDOH).

# Personas

Named archetypes representing cohorts.

* [Maya - the Digital-First Avoider](personas/maya.md) - Commercial, healthy, app-first.
* [Gloria - the Multi-Condition Manager](personas/gloria.md) - Medicare Advantage, chronic, needs direction.
* [Tanya - the New-Parent Member](personas/tanya.md) - Medicaid, postpartum, high SDOH burden.
* [Walter - the Complex Dual](personas/walter.md) - Dual-eligible, complex, disengaged.

# Cohorts

Sized, trackable groups.

* [MA Chronic Multi-Condition](cohorts/ma-chronic-multicondition.md) - Medicare Advantage members with 3+ chronic conditions.
* [Medicaid Postpartum](cohorts/medicaid-postpartum.md) - Recent Medicaid-covered births.

# Plays

Marketing / UX / feature moves.

* [SMS-First Renewal Nudge](plays/sms-renewal-nudge.md) - Proactive low-bandwidth reminders to prevent coverage churn.
* [Directive Care-Plan Adherence](plays/directive-care-plan-adherence.md) - Clear, single-next-step guidance for low-activation members.

# References

External sources backing claims, as first-class concepts.

* [KFF Coverage Data 2025](references/kff-coverage-2025.md)
* [Upfront Healthcare Psychographics](references/upfront-psychographics.md)
* [Patient Activation Measure (PAM)](references/pam-activation.md)
* [Healthy People 2030 - SDOH Framework](references/healthy-people-2030-sdoh.md)
* [CDC/ATSDR Social Vulnerability Index](references/cdc-svi.md)
* [CMS Chronic Conditions Warehouse](references/cms-chronic-conditions.md)
