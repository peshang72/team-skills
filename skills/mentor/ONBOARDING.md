# Onboarding a new learner

Run when `~/.learning/profile.md` does not exist. The goal is a placement that
is right on day one: too high and the learner drowns in undefined terms, too
low and they're bored and the product stalls. Take about 15 minutes, and keep it
friendly — this is a conversation, not an exam.

## 1. Interview

Ask one question at a time:

1. Which language should I explain things in? (Kurdish Sorani, Arabic, English,
   or another.)
2. What do you want to be able to do in six months? Push for something concrete
   ("build and ship a feature on my own", "get a junior developer job"), not
   "learn coding".
3. What have you built or studied before? Ask for an example, not a rating.
4. How do you like to learn: by reading first, or by trying and breaking things?
5. How much time per week?

## 2. Diagnostic

Assess by doing, not by asking. Stop early once the level is clear. Use code
from **this repo**, picking small pieces:

1. **Read** — show a short function (10–20 lines). Ask: what does it return
   for this input, and why?
2. **Test** — show a short test. Ask: what behaviour does this protect? Then
   break one line in the code and ask them to predict which test goes red.
3. **Write** — ask for a small change (a new condition, a renamed value)
   with its test. Only if steps 1–2 went well.
4. **Structure** — ask where in the repo they'd put a new page or API route,
   and why. Only if step 3 went well.

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

## 3. Save and confirm

1. Write `~/.learning/profile.md` and one record per thing the diagnostic
   showed they can already do.
2. Tell the learner their levels in plain words, what they'll do themselves at
   each, and that they can change them anytime.
3. Explain that every coding session in a repo with this skill will now run in
   mentor mode, and that "deadline" switches to fast mode for one task.
