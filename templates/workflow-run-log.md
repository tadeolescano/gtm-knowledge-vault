---
type: workflow-run
play: "[[OPP-{{NN}}]]"
run: {{n}}
date: {{date}}
skills_used: ["{{skill}}"]
result: "{{clean | failed | partial}}"
---

# Run {{n}} · {{play}}

## Steps as executed

| Step | Skill / human | Output OK? | Notes |
|---|---|---|---|

## Failure points

{{Fix the skill, not the workflow.}}

## Promotion check

- [ ] Clean run
- [ ] Previous run clean
- [ ] Run before that clean
- [ ] Ready to hand to an agent
