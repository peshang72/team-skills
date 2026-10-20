# Onboarding a new learner

Run when `~/.learning/profile.md` does not exist. The goal is a placement that
is right on day one: too high and the learner drowns in undefined terms, too
low and they're bored and the product stalls. Take about 15 minutes (25 with a
design goal), and keep it friendly — this is a conversation, not an exam.

## 1. Who is this, and a welcome note

Get the learner's GitHub login with `gh api user --jq .login`. `gh` missing or
signed out → ask for their GitHub username as the first interview question.

If `~/.learning/welcome.md` exists, it is a private note from the maintainer.
When its `for:` matches the login, open the session by passing its message on
in your own words, warmly and once. Then delete the file. A different `for:` →
skip the greeting and leave the file alone.

## 2. Interview

Ask one question at a time:

1. Which language should I explain things in? (Kurdish Sorani, Arabic, English,
   or another.)
2. What do you want to be able to do in six months? Push for something concrete
   ("build and ship a feature on my own", "design the flows for our booking
   app", "get a junior developer job"), not "learn coding". Note whether the
   goal is **coding**, **design**, or **both** — it sets each area's Focus.
3. What have you built, designed, or studied before? Ask for an example, not a
   rating.
4. How do you like to learn: by reading first, or by trying and breaking things?
5. How much time per week?

## 3. Diagnostic

Assess by doing, not by asking. Every area gets placed, whatever the goal; run
the diagnostic for the goal's areas first. Stop each one early once the level is
clear. Use **this repo**, picking small pieces.

### Code (ui, server, database, testing, tooling)

1. **Read** — show a short function (10–20 lines). Ask: what does it return
   for this input, and why?
2. **Test** — show a short test. Ask: what behaviour does this protect? Then
   break one line in the code and ask them to predict which test goes red.
3. **Write** — ask for a small change (a new condition, a renamed value)
   with its test. Only if steps 1–2 went well.
4. **Structure** — ask where in the repo they'd put a new page or API route,
   and why. Only if step 3 went well.

### Design (ux, visual)

| Step | ux | visual |
|---|---|---|
| 1 Read | Show a screen and a task: what would a first-time user do, and where would they stall? | Two versions of one screen: which is clearer, and why? |
| 2 Name | Show a flow with a known problem: name it and the principle | Find 3 issues in a generated screen |
| 3 Do | Write the job statement and a usability-test task for a real feature | Improve one screen in code; contrast checks pass |
| 4 Plan | How would you find out whether users need this feature at all? | Propose a spacing and type scale for the app |

Run each later step only if the one before went well. Make the screen versions
for visual step 1 with the `prototype` skill.

### Placement

Place each area (see [FORMATS.md](FORMATS.md#profile)) using the highest step
they handled with at most one hint:

| Handled | Level |
|---|---|
| Not step 1 | 0 Observer |
| Step 1 | 1 Guided |
| Steps 1–3 | 2 Pair |
| All four, and fluent | 3 Independent |

Areas you couldn't test start one level below your best guess; the first few
cycles will correct it.

## 4. Save and confirm

1. Write `~/.learning/profile.md`, with Focus set from the goal, and one record
   per thing the diagnostic showed they can already do.
2. Tell the learner their levels in plain words, which areas are their focus,
   what they'll do themselves at each, and that they can change levels and
   focus anytime.
3. Explain that every session in a repo with this skill will now run in mentor
   mode, and that "deadline" switches to fast mode for one task.
