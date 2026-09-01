# AI301 Unit 6 starter: voice-guard and repo memory

Materials for Unit 6 of AI301 (working with maintainers, claim day).
This repo holds the unit's runnable package: the voice-guard, the
wild scope swap for repro-check, the rubric scope patch, and the
repo-memory template. All instructions live on the course portal
(Overview, Activity, and Check-In tabs for Unit 6); this repo is the
package those pages tell you to install.

## What's here

- `skill/INSTALL.md`: the whole install, steps 1-6. The activity's
  phase 1 runs steps 1-5; step 6 explains the guard's evidence log.
- `skill/check_voice.py` and `skill/hooks-settings.json`: the guard
  (staff-complete; you write no code). The hook puts your own voice
  check on the posting doorway; the checker also runs standalone as
  the manual doorway (`--draft FILE`).
- `skill/voice-guide-upstream.md`: the upstream section template for
  your voice guide (claims, questions, pings). The rules are yours to
  write; the template's closing comment carries the unit-2 frame if
  you are writing the guide fresh.
- `skill/repro-check-scope-wild.md`: the staff-complete wild scope
  that replaces repro-check's unit-2 sandbox scope.
- `skill/rubric-scope-patch.md`: the taught scope patch for your
  scout's rubric (scope becomes a difficulty dial; umbrellas still
  fail). Pasted in phase 1, before the scan launches.
- `skill/claude-local-template.md`: the repo-memory template. After
  class you copy it to your target repo's clone root as
  `CLAUDE.local.md` and follow it top to bottom.

## Install

The Activity tab has the full steps and the warnings. In short: get
this repo onto your machine (`git clone
https://github.com/smoran02/ai301-unit6-starter.git`, or Code then
Download ZIP on the repo page), then follow `skill/INSTALL.md` from
the top. The install is an overlay onto what you already own: it adds
the guard, replaces repro-check's scope, and promotes your voice
guide to its one canonical home. Your rubric, strategy, evidence
guide, and every Module 1 skill folder stay yours and untouched.

## No eval/ here, on purpose

Unit 6 ships no eval set and no harness. If today's rubric patch (or
any patch a fresh scan drives) changes your rubric, the regression
instrument is still Unit 1's harness, unchanged: run it from the
`eval/` directory of your
[Unit 1 materials](https://github.com/smoran02/ai301-unit1-starter)
clone, as the Activity tab's after-class steps describe. The run is
graded as evidence, never as a score.
