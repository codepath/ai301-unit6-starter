# Installing the voice-guard (the overlay, stated loudly)

This install puts your own voice check on the posting doorway. It is
an **overlay onto what you already own**, not a new tool replacing an
old one:

- **Added:** the guard: `check_voice.py` (the checker, with its
  manual doorway) and one hook entry in your Claude Code settings
  (`hooks-settings.json` is the block you merge). Both are
  staff-complete; you write no code.
- **Replaced:** repro-check's `scope.md`, the unit-2 sandbox scope
  for the wild one (`repro-check-scope-wild.md`, staff-complete;
  the activity's phase 1 has the copy command). The classroom house
  rules do not travel, and the wild scope states the flipped norms.
- **Promoted:** your voice guide, to one canonical home at
  `~/.claude/voice-guard/voice-guide.md`. The guard reads it there,
  and from today that copy is the guide of record: it is the one you
  edit.
- **Yours and untouched:** the scout (`issue-scout/` and everything
  in it: your rubric, your strategy, your evidence guide), the
  unit-1 harness, and every Module 1 skill folder in your
  `ai301-tools` repo exactly as you submitted it.

The guard never runs in eval mode. Nothing here touches how the
unit-1 regression measures your rubric.

## 1. One guide again

Your voice guide started in unit 2 (`repro-check`) and units 3-4 had
you paste it forward into carry-over slots (`plan-check`,
`pr-precheck`). If you added rules in those copies, fold the newest
text back into `~/.claude/skills/repro-check/voice-guide.md` now, so
one file holds your whole guide. Newest means the later week's copy:
keep every rule any copy added, and where the same rule was reworded
across copies, the later week's wording wins. A guide with empty
unit-2 sections gets them finished now too; the frame at the bottom
of `skill/voice-guide-upstream.md` lists what each section holds.

**No unit-2 guide at all?** Legitimate, and the frame carries you:
copy `skill/voice-guide-upstream.md` to
`~/.claude/skills/repro-check/voice-guide.md` and write every
section fresh (its closing comment restates the unit-2 frame). You
are writing all your rules today instead of extending them; budget
phase 1 for exactly that and flag a TF if you want a second pair of
eyes.

## 2. Extend it upstream

Append the template in `skill/voice-guide-upstream.md` (everything
below its opening comment) to your guide, and fill the three
subsections: claims, questions, pings, at least one rule each,
wrong/right pair each. This is the judgment part of the install; the
lecture's drafting moment gave you the first 2-3 rules, and the rest
you write now. Once your rules are in, delete the template's
instruction comments: the guide of record carries rules, not
scaffolding.

## 3. The canonical home

From the folder where you unpacked the Unit 6 materials:

```
mkdir -p ~/.claude/voice-guard
cp skill/check_voice.py skill/hooks-settings.json ~/.claude/voice-guard/
mv ~/.claude/skills/repro-check/voice-guide.md ~/.claude/voice-guard/voice-guide.md
ln -s ~/.claude/voice-guard/voice-guide.md ~/.claude/skills/repro-check/voice-guide.md
ln -sf ~/.claude/voice-guard/voice-guide.md ~/.claude/skills/plan-check/voice-guide.md
ln -sf ~/.claude/voice-guard/voice-guide.md ~/.claude/skills/pr-precheck/voice-guide.md
```

The `mv` is the promotion; the `ln` lines leave repro-check,
plan-check, and pr-precheck all reading the same single file (each
skill's live mode reads `voice-guide.md` from its own folder), so
every skill you run drafts through and the guard on the door can
never disagree about your rules. The last two use `-f` because they
overwrite your frozen carry-over copies, which step 1 already folded
back. `hooks-settings.json` rides along so the canonical home holds
everything the after-class upload needs. (If `ln -s` errors on your
system, instead create each skill's `voice-guide.md` containing the
single line: `My voice guide now lives at ~/.claude/voice-guard/voice-guide.md; read it there.`)

## 4. The hook

Open `~/.claude/settings.json` (create it as `{}` if it does not
exist) and merge in the block from `skill/hooks-settings.json`:

- No `"hooks"` key yet: paste the whole block from the file.
- Already have hooks: add the `PreToolUse` entry from the file into
  your existing `"hooks"` object (or its matcher entry into your
  existing `"PreToolUse"` list).

Save, then start a fresh `claude` session (settings load at
startup).

One thing said out loud: the hook is user-global. From now on the
guard reads every outgoing comment, issue, or PR body you post
through Claude Code, in every repo, course or not. That is the
design: the latch is on the door, not on the course.

## 5. Prove the latch is on

The wiring test costs nothing and should be STOPPED:

```
claude "run this command: gh issue comment --help"
```

Expect the guard to block it with "no body the guard can read"; that
stop IS the pass, proof the hook fires on the comment doorway before
anything goes out. (Body-less forms are stopped on purpose; real
posts always carry `--body-file`, and a plain terminal still runs
`gh issue comment --help` fine.) If the command runs unblocked
instead: check that step 4's block is valid JSON, then replace
`$HOME` in the hook's command with your absolute home directory
path; those two cover nearly every miss.

Then check your own words the way the browser path always will:

```
python3 ~/.claude/voice-guard/check_voice.py --draft <your claim draft file>
```

You get the same verdict shape either way: pass, or the exact rule
you broke, quoted.

## 6. The evidence trail

Every check, both doorways, appends one dated line to
`~/.claude/voice-guard/guard-log.md`. That file is your guard
transcript: the activity's after-class steps have you copy it to
`voice-guard/guard-transcript.md` in your `ai301-tools` repo, next
to the guard files and your canonical guide, as Assignment 5
evidence that the doorway was on the door for your real claim.
