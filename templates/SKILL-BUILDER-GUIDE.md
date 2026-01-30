# Skill Builder Guide

A comprehensive guide to creating effective AI skills using best practices from prompt engineering, knowledge architecture, and the skills ecosystem.

---

## Table of Contents

1. [What is a Skill?](#what-is-a-skill)
2. [Skill Architecture](#skill-architecture)
3. [The Discovery Process](#the-discovery-process)
4. [Writing Effective Skill Content](#writing-effective-skill-content)
5. [Prompt Engineering Best Practices](#prompt-engineering-best-practices)
6. [Building Reference Materials](#building-reference-materials)
7. [Testing and Iteration](#testing-and-iteration)
8. [Publishing Your Skill](#publishing-your-skill)

---

## What is a Skill?

A skill is a reusable instruction set that extends an AI coding agent's capabilities. When activated, it injects domain-specific knowledge, frameworks, and mental models into the AI's context.

### Skills vs. General Knowledge

| General AI | AI + Skill |
|------------|------------|
| Generic advice | Industry-specific guidance |
| Surface-level responses | Deep domain expertise |
| No benchmarks | Specific metrics and targets |
| Abstract frameworks | Actionable decision criteria |
| No context awareness | Company/situation-aware |

### When to Build a Skill

Build a skill when:
- You find yourself repeatedly giving the same context to AI
- Domain expertise requires specific benchmarks, metrics, or frameworks
- Decisions need to be filtered through industry-specific criteria
- Common questions have non-obvious answers that require expertise

---

## Skill Architecture

### File Structure

```
your-skill/
├── SKILL.md              # Core skill definition (required)
├── README.md             # User documentation (required)
├── LICENSE               # License file (required)
└── references/           # Supporting materials (recommended)
    ├── metrics-benchmarks.md
    ├── case-studies.md
    └── [additional refs].md
```

### SKILL.md Anatomy

```markdown
---
name: skill-name          # lowercase, no spaces
description: Brief description with activation keywords
---

# Skill Title: Tagline

[Introduction]

## Core Mental Models
[Principles and frameworks]

## Key Metrics
[Specific numbers and targets]

## Decision Frameworks
[Step-by-step processes]

## Benchmarks
[Industry standards]

## References
[Links to supporting docs]
```

### Critical Components

1. **YAML Frontmatter** (Metadata)
   - `name`: Skill identifier (used in installation command)
   - `description`: Activation trigger + capability summary

2. **Mental Models** (Core Logic)
   - First principles that guide all advice
   - Should be memorable and actionable
   - Example: "Profit is a constraint, not a goal"

3. **Specific Metrics** (Quantified Guidance)
   - Concrete numbers, not vague advice
   - Include thresholds and targets
   - Example: "LTV:CAC ≥ 3:1" not "good customer economics"

4. **Decision Frameworks** (Action Steps)
   - Repeatable processes for common decisions
   - Clear criteria and trade-offs
   - Example: Hiring decision checklist with specific questions

5. **Benchmarks** (Industry Context)
   - What "good" looks like in this domain
   - Stage-appropriate expectations
   - Comparison points for evaluation

---

## The Discovery Process

Before writing any skill content, complete a thorough discovery. Use the `DISCOVERY-PROMPT.md` template to gather:

### Essential Information

1. **Company/Industry Context**
   - Business model and stage
   - Funding model and constraints
   - Geographic and regulatory context

2. **Goals and Vision**
   - Short-term (12 months)
   - Medium-term (1-3 years)
   - Long-term (5-10 years)

3. **Challenges and Pain Points**
   - Current blockers
   - Resource constraints
   - Knowledge gaps

4. **Expert Knowledge**
   - Mental models used by experts
   - Counterintuitive truths
   - Common mistakes to avoid

5. **Activation Patterns**
   - Questions users frequently ask
   - Decision triggers
   - Desired output formats

### Discovery Interview Tips

- Ask "what" before "how"
- Probe for specific numbers and thresholds
- Request examples of good and bad decisions
- Identify recurring patterns and anti-patterns
- Capture the language the domain uses

---

## Writing Effective Skill Content

### Principles of Effective Skills

#### 1. Be Specific, Not Generic

```markdown
❌ Generic:
"Maintain healthy cash reserves"

✅ Specific:
"Maintain 24-36 months runway minimum. Reserve structure:
- Operating: 3-6 months fixed costs
- Contingency: 1-2 months expenses
- Growth: Excess cash"
```

#### 2. Provide Frameworks, Not Just Facts

```markdown
❌ Just facts:
"LTV:CAC should be 3:1"

✅ Framework:
"Every investment question: What is the payback period? Target <12 months.
LTV:CAC minimum 3:1 (best-in-class: 7-8x)
If below 3:1, either reduce CAC or increase LTV before scaling"
```

#### 3. Include Decision Criteria

```markdown
❌ Vague:
"Be careful about hiring"

✅ Decision criteria:
"Hiring decisions:
1. Will this hire directly contribute to revenue?
2. What's the time-to-productivity? (Factor into ROI)
3. What else could this salary fund?
4. Does this make existing team more productive?
Never grow a department >50% at once"
```

#### 4. Use Tables for Quick Reference

```markdown
| Metric | Target | Warning Sign |
|--------|--------|--------------|
| Runway | 24-36 months | <12 months |
| LTV:CAC | ≥3:1 | <2:1 |
| Gross margin | 70-80% | <60% |
```

#### 5. Link to Reference Materials

Keep SKILL.md focused on actionable frameworks. Move detailed calculations, extensive benchmarks, and case studies to reference files.

### Writing Mental Models

Mental models should be:
- **Memorable**: Easy to recall when making decisions
- **Actionable**: Provide clear guidance
- **Non-obvious**: Add expertise beyond common knowledge
- **Defensible**: Based on evidence and experience

Example structure:
```markdown
**[Principle statement]:** [Explanation of why this matters]

[Supporting details or implications]
```

### Writing Metrics Sections

For each metric include:
- **Formula**: How to calculate it
- **Target**: What "good" looks like
- **Thresholds**: Warning signs and danger zones
- **Context**: When this metric matters most

---

## Prompt Engineering Best Practices

Based on [Anthropic's guidelines](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/claude-4-best-practices) and [IBM's 2026 guide](https://www.ibm.com/think/prompt-engineering):

### 1. Be Explicit

Claude 4.x models respond to precise instructions. Don't assume—state clearly.

```markdown
✅ "When evaluating a hire, always calculate payback period as:
   (Fully loaded cost × months to productivity) / expected monthly contribution"

❌ "Think about whether hires are worth it"
```

### 2. Provide Context (The "Why")

Explain the reasoning, not just the rule.

```markdown
✅ "Revenue per employee matters because bootstrapped companies can't
   subsidize inefficiency with investor capital. Target $200K+ RPE at
   $10M ARR to maintain competitive margins."

❌ "Track revenue per employee"
```

### 3. Use Structured Formats

XML tags, tables, and clear hierarchies help Claude parse complex information.

```markdown
## Decision Framework

### Step 1: Assess
[Details]

### Step 2: Analyze
[Details]

### Step 3: Decide
[Details]
```

### 4. Include Examples (Few-Shot Learning)

Show the pattern you want followed.

```markdown
**Example calculation:**
- Monthly ARPU: $100
- Gross margin: 75%
- Monthly churn: 2%
- LTV = ($100 × 75%) / 2% = $3,750
```

### 5. Define Output Expectations

Specify format, tone, and structure.

```markdown
When asked about hiring decisions, respond with:
1. Initial assessment (1-2 sentences)
2. Payback calculation
3. Opportunity cost analysis
4. Recommendation with confidence level
```

### 6. Use Positive Instructions

Tell Claude what TO do, not just what not to do.

```markdown
✅ "Prioritize profitability metrics over growth metrics"
❌ "Don't focus too much on growth"
```

---

## Building Reference Materials

### Metrics & Benchmarks Document

Structure:
1. **Formula definitions** with clear notation
2. **Interpretation guides** with thresholds
3. **Industry benchmarks** by segment/stage
4. **Warning signs** and red flags
5. **Data sources** for credibility

Tips:
- Include calculation examples
- Specify data vintage (when benchmarks were valid)
- Note regional or segment variations
- Link to primary sources when possible

### Case Studies Document

Structure:
1. **Company profile** (timeline, metrics, context)
2. **Key decisions** that drove success/failure
3. **Outcomes** with specific numbers
4. **Lessons** applicable to the reader

Tips:
- Choose companies the target audience will recognize
- Focus on decisions, not just outcomes
- Extract transferable patterns
- Include failures and anti-patterns

### Additional References

Consider creating:
- Industry glossary
- Regulatory requirements
- Regional variations
- Tool recommendations
- Process templates

---

## Testing and Iteration

### Testing Checklist

1. **Activation Test**
   - Does the skill activate on expected questions?
   - Does it stay dormant for unrelated questions?

2. **Accuracy Test**
   - Are metrics and benchmarks correct?
   - Are recommendations appropriate?

3. **Completeness Test**
   - Are common scenarios covered?
   - Are edge cases handled?

4. **Tone Test**
   - Does the output match desired style?
   - Is it appropriate for the audience?

5. **Usefulness Test**
   - Would an expert approve the advice?
   - Would a user find it actionable?

### Iteration Process

1. Test with real questions from target users
2. Note where advice is wrong, incomplete, or unclear
3. Add missing frameworks or clarify existing ones
4. Re-test and repeat

### Common Issues and Fixes

| Issue | Cause | Fix |
|-------|-------|-----|
| Too generic | Lack of specifics | Add concrete numbers/thresholds |
| Wrong activation | Description too broad | Narrow activation keywords |
| Incomplete advice | Missing frameworks | Add decision criteria |
| Inconsistent | Conflicting guidance | Review for coherence |

---

## Publishing Your Skill

### Pre-Publication Checklist

- [ ] SKILL.md with valid YAML frontmatter
- [ ] README.md with installation instructions
- [ ] LICENSE file
- [ ] All referenced files exist
- [ ] Links work correctly
- [ ] Spelling and grammar checked
- [ ] Expert review completed
- [ ] Testing completed

### Repository Setup

1. Create GitHub repository
2. Use clear naming: `{org}/{skill-name}-skill`
3. Add appropriate topics/tags
4. Write clear README with examples

### Installation Command

Users install via:
```bash
npx skills add {org}/{repo-name}
```

### Maintenance

- Update benchmarks annually (note data vintage)
- Add new case studies as they emerge
- Refine based on user feedback
- Track industry changes that affect advice

---

## Quick Reference: Skill Quality Checklist

### Must Have
- [ ] Clear, lowercase `name` in frontmatter
- [ ] Description with activation keywords
- [ ] At least 3 mental models/principles
- [ ] Specific metrics with targets
- [ ] At least 1 decision framework
- [ ] Reference links (if using reference docs)

### Should Have
- [ ] Tables for quick reference
- [ ] Stage-appropriate benchmarks
- [ ] Real-world examples
- [ ] Warning signs and red flags
- [ ] Case studies

### Nice to Have
- [ ] Formulas for calculations
- [ ] Industry comparisons
- [ ] Regional variations
- [ ] Tool recommendations
- [ ] Process templates

---

## Resources

### Prompt Engineering
- [Anthropic Claude Best Practices](https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/claude-4-best-practices)
- [Prompting Guide](https://www.promptingguide.ai/)
- [IBM Prompt Engineering 2026](https://www.ibm.com/think/prompt-engineering)

### Skills Ecosystem
- [Vercel Skills](https://github.com/vercel-labs/skills)
- [Agent Skills Repository](https://github.com/vercel-labs/agent-skills)

### Knowledge Architecture
- [Claude Code Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)

---

*Built with insights from Charlie CFO Skill by Every.to*
