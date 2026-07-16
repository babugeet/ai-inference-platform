# MiniStack / LocalStack Behavioural Notes

This file documents known differences between MiniStack (local AWS simulator) and real AWS encountered during this project. Real teams maintain this kind of document when working with simulators or mock environments — it prevents "works locally, breaks in CI" surprises.

---

## How to Use This File

When you discover that MiniStack behaves differently from what the AWS documentation describes, add an entry here with:

- The service and feature affected
- What the real AWS behaviour is
- What MiniStack does instead
- Any workaround applied

---

## Known Differences

_None documented yet. Add entries here as you discover them during each phase._

---

## Template

```
### [Service] — [Feature]
**Real AWS:** <what AWS does>
**MiniStack:** <what MiniStack does>
**Workaround:** <how you handled it in code or config>
**Phase discovered:** Phase N
```
