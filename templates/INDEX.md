# Skill Template System

A complete system for reverse-engineering and building AI skills for any industry or company type.

---

## Quick Start

1. **Discovery**: Complete `DISCOVERY-PROMPT.md` with your client/company
2. **Learn**: Read `SKILL-BUILDER-GUIDE.md` for best practices
3. **Build**: Use templates to create your skill files
4. **Test**: Validate with real questions
5. **Publish**: Push to GitHub and install

---

## File Index

### Core Templates

| File | Purpose | Use When |
|------|---------|----------|
| `SKILL.template.md` | Main skill definition template | Starting a new skill |
| `README.template.md` | User documentation template | Creating skill readme |
| `DISCOVERY-PROMPT.md` | Client questionnaire | Gathering skill requirements |
| `SKILL-BUILDER-GUIDE.md` | Best practices guide | Learning how to build skills |

### Reference Templates

| File | Purpose | Use When |
|------|---------|----------|
| `references/metrics-benchmarks.template.md` | Metrics and calculations | Adding quantitative reference |
| `references/case-studies.template.md` | Real-world examples | Adding qualitative reference |

### Examples

| Directory | Description |
|-----------|-------------|
| `examples/restaurant-coo-skill/` | Complete example of template applied to restaurant operations |

---

## Workflow

```
┌─────────────────────────────────────────────────────────────────┐
│                        DISCOVERY PHASE                          │
├─────────────────────────────────────────────────────────────────┤
│  1. Complete DISCOVERY-PROMPT.md with client                    │
│  2. Identify mental models, metrics, and decision frameworks    │
│  3. Gather case studies and benchmarks                          │
│  4. Define activation keywords                                  │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                        BUILD PHASE                              │
├─────────────────────────────────────────────────────────────────┤
│  1. Create repo: {org}/{skill-name}-skill                       │
│  2. Fill SKILL.template.md → SKILL.md                           │
│  3. Fill README.template.md → README.md                         │
│  4. Fill reference templates → references/                      │
│  5. Add LICENSE (MIT recommended)                               │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                        TEST PHASE                               │
├─────────────────────────────────────────────────────────────────┤
│  1. Install skill locally                                       │
│  2. Test activation with expected questions                     │
│  3. Verify accuracy of metrics and recommendations              │
│  4. Check tone and format of responses                          │
│  5. Iterate based on feedback                                   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                        PUBLISH PHASE                            │
├─────────────────────────────────────────────────────────────────┤
│  1. Push to GitHub                                              │
│  2. Test installation: npx skills add {org}/{repo}              │
│  3. Share with users                                            │
│  4. Collect feedback and iterate                                │
└─────────────────────────────────────────────────────────────────┘
```

---

## Template Variables

Templates use `{{variable}}` syntax for placeholders. Replace all variables with your specific content.

### SKILL.md Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `{{skill_name}}` | Lowercase identifier | `charlie` |
| `{{skill_description}}` | Activation description | `Your AI CFO for...` |
| `{{skill_title}}` | Display name | `Charlie CFO` |
| `{{mental_models}}` | Core principles | Array of models |
| `{{metrics}}` | Key metrics table | Array of metrics |

### Mustache-Style Loops

For repeating sections:
```markdown
{{#items}}
- {{item_property}}
{{/items}}
```

---

## What Makes a Great Skill

### Essential Elements

1. **Specific Numbers** — Not "good margins" but "target 70-80% gross margin"
2. **Decision Frameworks** — Not "be careful" but "ask these 4 questions"
3. **Benchmarks** — Not "industry standard" but "by stage: $1-5M = X, $5-10M = Y"
4. **Mental Models** — Not "think strategically" but "every dollar has 3 costs"
5. **Warning Signs** — Not "watch out" but "if X drops below Y, take action Z"

### Common Mistakes

- Too generic (no specific numbers)
- Too broad (tries to cover everything)
- Missing decision criteria (what triggers advice)
- No reference materials (calculations undefined)
- Activation keywords too narrow or too broad

---

## Resources

- **Original Charlie CFO Skill**: See parent directory for working example
- **Vercel Skills CLI**: `npx skills add --help`
- **Anthropic Prompt Guide**: https://docs.claude.com
- **Every.to**: https://every.to

---

*Built by reverse-engineering Charlie CFO Skill from Every.to*
