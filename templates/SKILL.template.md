---
name: {{skill_name}}
description: {{skill_description}} Provides {{core_capabilities}}. Use for questions like {{example_questions}}.
---

# {{skill_title}}: {{skill_tagline}}

{{skill_introduction}}

## Core Mental Models

{{#mental_models}}
**{{model_name}}:** {{model_description}}

{{model_details}}
{{/mental_models}}

## Key Principles

{{#principles}}
**{{principle_name}}:**

{{principle_details}}

{{/principles}}

## {{domain_specific_framework_1_name}}

{{domain_specific_framework_1_content}}

## {{domain_specific_framework_2_name}}

{{domain_specific_framework_2_content}}

## Decision Frameworks

**Every {{decision_type}} question:** {{decision_framework}}

{{#decision_criteria}}
### {{criteria_name}}

{{criteria_details}}
{{/decision_criteria}}

## Key Metrics Dashboard

| Category | Metrics | Targets |
|----------|---------|---------|
{{#metrics}}
| {{category}} | {{metric_names}} | {{target_values}} |
{{/metrics}}

## {{industry_specific_section_name}}

{{industry_specific_content}}

## Review Rhythms

**Weekly ({{weekly_time}}):**
{{#weekly_items}}
- {{item}}
{{/weekly_items}}

**Monthly:**
{{#monthly_items}}
- {{item}}
{{/monthly_items}}

**Quarterly:**
{{#quarterly_items}}
- {{item}}
{{/quarterly_items}}

## Benchmarks

{{benchmarks_content}}

## Common Scenarios

{{#scenarios}}
### {{scenario_name}}

**Situation:** {{situation}}

**Approach:**
{{approach}}

**Key Considerations:**
{{considerations}}
{{/scenarios}}

---

## References

- See [references/metrics-benchmarks.md](references/metrics-benchmarks.md) for detailed calculations and industry benchmarks
- See [references/case-studies.md](references/case-studies.md) for real-world examples and patterns
{{#additional_references}}
- See [{{reference_path}}]({{reference_path}}) for {{reference_description}}
{{/additional_references}}
