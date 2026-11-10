# however

An [Agent Skill](https://agentskills.io/specification) that wins arguments no matter what.
Winning has never been easier.

Paste in what your opponent said. You get a merciless, ready-to-send comeback that grants them
something small, uses "however" to take apart the claim that matters, and leaves no doubt about
who won.

Works on any channel: Reddit/X threads, Slack, work email, meetings, debates, family group chats.

## How it wins

- **The pivot.** A short, slightly dismissive concession ("Sure, ...", "Granted, ..."), then
  "however" and the hit. Conceding first takes away their safe ground and makes you look like
  you've already thought past their point.
- **The combo.** Each reply stacks a pivot, a pressure move and a finisher. The arsenal has 11
  pivots (their own words, their own standard, their track record, hidden cost, false
  choice, ...) and 15 hardball moves: framing, trap and loaded questions, reductio, demanding
  definitions, pinning concessions, exposing retreats, tu quoque, credential checks, ridicule,
  playing to the audience, bait, preemption.
- **Dominance.** You speak as the expert correcting a student. You set the terms, give orders
  instead of invitations, and declare the result ("So that's settled."). No hedging, no
  apologies, no "happy to discuss".
- **The person is fair game.** It roasts their track record, hypocrisy or credentials when that
  helps, except with a boss or client, where it sticks to the decision.
- **Real ammunition.** It checks facts itself with web search and links real sources, so the
  reply is safe to paste. Nothing is left for you to verify or fill in.
- **The next round, ready.** Every answer includes their most likely comeback and your counter.
- **Built for each channel.** Social replies are at most 4 sentences; on X, at most 280
  characters including links.

## What you get

```
Reply (ready to send):  the comeback, in your voice
Why it lands:           the moves it used, in 1–2 sentences
If they hit back:       their likely comeback → your one-line counter
Heads-up:               only if they're right about something you should know
```

## Example

> **You:** my coworker in slack says we shouldn't write tests for the prototype because it's
> going to be thrown away anyway. I think we need at least some tests, we're demoing it to the
> client in 2 weeks

> **Reply (ready to send):**
> Sure, full coverage on a throwaway would be a waste. However, "it's getting thrown away" is
> the famous last words of every prototype still running in production, and this one is in
> front of the client in two weeks. I'm writing tests for the demo flows, nothing more.
> Unless you're volunteering to explain the crashed demo yourself?
>
> **If they hit back:** "We don't have time." → "A few tests now versus a rescheduled client demo.
> Which one is the time problem?"

## The only limits (and why)

Each of these exists because breaking it is how you lose:

- **No invented facts.** One fake number that gets checked hands them the win and your
  credibility. If the skill can't verify a fact, it makes the point without it.
- **No slurs, identity attacks, threats or private info.** They get the post removed, get you
  reported or fired, and make you the villain.
- **If your opponent is actually right, it tells you privately**, then moves the fight to
  ground you can win, instead of walking you into a public fact-check.
- **It picks the win that counts.** A visible knockout in public threads; with your boss, the
  win is that they adopt your plan, so it leaves them a way to say yes; with family, a kill by wit.

## Install

Claude Code (personal):

```bash
cp -r however ~/.claude/skills/
```

Or per project, at `.claude/skills/however`. On claude.ai, zip the `however` folder and upload
it in the Skills section of your settings. Fact-checking needs web search; without it, the skill
leaves out any number it can't confirm.

## Layout

```
however/
├── SKILL.md                 # workflow, dominance rules, output format, trigger description
├── references/REFERENCE.md  # pivots, hardball moves, finishers, multi-round tactics, channel notes
└── evals/                   # test cases (prompt + graders), runnable with `claude plugin eval`
```

## Tests

Four test cases live in `however/evals/`: a Reddit thread, an email pushing back on a
manager, a family argument where the opponent is actually right, and a condescending
"PhD | economist" on X. To run them (Claude Code v2.1.269+; these are real, billed model runs):

```bash
cd however && claude plugin eval . --allow-tools Write,Edit,Bash,WebSearch,WebFetch
```

## License

MIT, see [LICENSE](LICENSE).
