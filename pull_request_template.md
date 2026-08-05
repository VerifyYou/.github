## Summary
<!-- The problem and who it's for. Not a diff recap — the reviewer can read the diff. -->
Closes VY-___

## Test plan
<!-- Numbered steps a STRANGER could walk to verify this. Start with setup / flag toggle.
     If you changed tests, name the regression each one catches that no existing test did.
     Agents: do NOT claim manual testing you didn't do — list only what you actually ran. -->
1.

## Risk
<!-- One line each. "n/a" on its own is not an answer — say why, e.g.
     "n/a — no auth, input-handling or dependency surface touched". Most changes
     are n/a on most lines; that's expected. -->
- **Security:**
- **Data integrity:**
- **Availability:**

## Feature flag / rollout
<!-- Delete this whole section if there's no flag. -->
- **Key / state at merge:** `area-thing-release` — off
- **Rollout:** me → team → 10% → 100%
- **Off switch:** disable the flag — legacy path intact, no deploy needed
- **Removal:** temporary, remove by YYYY-MM-DD, owner @_**, ticket VY-**_  <!-- or: permanent kill switch, keep -->
- **How I'll know if it's wrong:** <!-- the dashboard or alert you'll watch -->

## Demo
<!-- When UI or behavior changed: link a short screen recording. -->

<details>
<summary>Self-review checklist</summary>

- [ ] I read my own diff first, as a reviewer would
- [ ] Stripped stale AI-review / scratch comments and debug noise
- [ ] Small and single-purpose; unrelated changes split out
- [ ] Tests ship with the change (or the test plan says why not)
- [ ] CI is green
- [ ] No secrets, keys, or real user data in the diff

</details>
