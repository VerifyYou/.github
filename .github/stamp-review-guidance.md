# Stamp review guidance

What a second reader checks before a pull request in this repository can merge on the review
gate's approval. The gate decides eligibility from `.github/stamp-policy.yml`; this file tells
the reader what to look at inside the diff it is handed. It never widens eligibility.

This is the org-level `.github` repository. The one file it holds, `pull_request_template.md`,
is the default pull request template for every VerifyYou repository that does not carry its
own copy. A diff here changes what every author sees when they open a PR.

## What to check

- The sections survive, in order: Summary, Test plan, Risk, Feature flag / rollout, Demo, and
  the collapsed Self-review checklist. Removing one, or renaming it, is blocking.
- The HTML comments stay. They are the instructions an author reads in the editor and never
  ships; a change that turns one into visible text, or drops it, is a finding.
- The instructions keep their teeth: a stranger can walk the Test plan, `n/a` alone is not a
  Risk answer, an agent lists only what it ran, a `Depends-on` PR stays a draft, and the
  Feature flag section is deleted when there is no flag. Softening any of these is blocking.
- The `Closes VY-___` line is a placeholder for a link, not bare text; guidance around it
  must not invite a bare identifier.
- The rendered Markdown is valid: the `<details>` block still opens and closes, the checklist
  items are `- [ ]`, and a trailing comment does not swallow a heading.
- Repositories with their own `.github/pull_request_template.md` do not inherit this one. A
  change meant for all of them says so in the PR body, and names the follow-ups.
- US spelling, no emojis, and the PR title is a Conventional Commit.

## What is never eligible

The gate refuses these before the reader sees them, so a diff touching them here means the
policy file is wrong, not that the reader should try harder.

- Anything under `.github/`: the gate itself and CI.
- Workflow templates, an org profile, `SECURITY.md` or a funding file, once they exist; the
  policy lists them the day they land.
- A pull request an agent opened. The fleet does not stamp itself.

## How to write a finding

- One finding per thread, on the line it is about. Prefix it: `blocking:` must change before
  merge; `suggestion:` worth considering; `nit:` the author can ignore; `question:` you need
  the answer before you can judge.
- Say what is wrong and what would make it right. Do not restate the diff.
- No wording comments beyond the rules above. Terse, decide-first prose is the house style.
- If a finding is outside the change, say so and stop; it is not this PR's problem.

## Verdict

End the review with exactly one line:

- `verdict: no_blocking_findings` when nothing above is blocking.
- `verdict: blocking` when at least one finding is blocking; the threads say which.
- `verdict: needs-human` when the change touches something a person should read regardless
  of the paths: a new required section, a claim about what reviewers or CI enforce, or
  anything you could not judge from the diff alone.
