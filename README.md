# drafting-solution-charters

An [Agent Skill](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) that turns the transcripts of a consultant's conversations with a client into a **solution charter**: a short, cited document that aligns the consultant and the client sponsor on what problem is worth solving, what success would look like, and roughly how much it's worth. It also writes a set of **private consultant notes** and a list of **follow-ups** for whatever the conversations didn't settle.

It's prose only: a `SKILL.md` and two templates, no scripts.

## The problem it solves

After a discovery call, a consultant writes up "what we heard." That write-up usually goes wrong in a few predictable ways:

- **Three kinds of information get mixed together.** What the client actually said, what the consultant inferred, and what the consultant hoped all end up in the same sentences. Six weeks later nobody can tell which was which.
- **Numbers appear from nowhere.** "A truck roll costs about $250" was a rule of thumb from another client, and now it's in the business case.
- **The client's sweeping claims pass as evidence.** "Our customers hate the invoicing" gets written up as a finding, though nobody ever gave a specific example.
- **The most important signals never reach the page.** The sponsor's hesitation on budget, the IT director's crossed arms, and the comment made after the recording stopped all matter. Transcripts don't capture them, and write-ups leave them out.
- **Sensitive things leak into documents the client sees.** One line about internal politics is enough to make a draft unshareable.
- **Gaps aren't tracked.** Nobody writes down what's still unknown, so the next conversation drifts instead of closing those gaps.

This skill addresses each of these. Everything in the charter traces back to a transcript line, a source the consultant can point to, or a call that was explicitly the consultant's to make. Everything else waits as a hypothesis until a follow-up confirms it. What the consultant noticed in the room shapes the charter without being quoted in it. And every gap becomes a question, worded so the consultant can ask the client as written.

## Who it's for

- **Consultants and advisors** running discovery with a client or prospect. This is the primary user.
- **Presales and solution engineers** shaping an opportunity before a proposal or statement of work.
- **Forward deployed engineers/Internal consultants**, such as product, operations, transformation, or IT business partners, who run discovery with stakeholders in their own organization. The charter defines the market as *the people whose behavior you're trying to change*, so employees, partners, and communities count as well as customers.

The skill assumes one person (the **Owner**, usually the consultant) has had the conversations, and one person on the client side (the **Decider**, the sponsor) will say "yes, this is what we're aligned on."

## When to use it

- You've had one or more conversations about an idea, and you have transcripts in any format.
- The idea is still at the "what problem, for whom, and is it worth it?" stage, and no solution has been picked yet.
- You want one sponsor to sign off on the problem, the ranked objectives, and the appetite before anyone designs anything.
- Discovery will take several conversations. The skill is iterative: add new transcripts and it closes follow-ups, upgrades or downgrades the evidence, and asks only about what's new.

## When not to use it

| If you need… | Use instead |
|---|---|
| Formal authorization of a budget, a project manager, or staff | A **project charter** |
| Justification of the investment with ROI and financial models | A **business case** |
| Features, user stories, or acceptance criteria | A **PRD** or requirements doc |
| Architecture, APIs, data, or alternatives considered | A **design doc** |
| Contracted scope, deliverables, and fees | A **statement of work** |
| Tasks, a timeline, and resourcing | A **project plan** |
| A record of what was said in a meeting | **Meeting notes** or a summary |

Also not a fit:

- **The solution is already decided.** The charter deliberately doesn't commit to a solution, so if you're past that point, write the design doc.
- **Approval needs a committee.** The charter has exactly two roles, Owner and Decider. If several parties must formally sign off, use a governance document built for that.
- **Assessing individuals.** The room-read questions exist to make the charter more accurate. They aren't a way to evaluate people, and the notes shouldn't be used as one.

## Use it responsibly

- **Only use transcripts recorded with participants' consent**, and only in line with your agreement with the client and their confidentiality terms.
- **`consultant-notes.md` is sensitive.** It holds your readings of individual people, private comments, and tactics for the next conversation. Store it as you would any confidential client material, and never send it to the client.
- **The charter is a draft until the Decider signs it.** Read it before sharing. The skill checks for leaks, but you know the relationship better than it does.

## What it does

1. **Intake.** It confirms the date, the attendees, their roles, and the Decider for each transcript. It works with any transcript format and adapts when speaker labels or timestamps are missing, without inventing anything.
2. **Reads before asking.** It pulls quotes for each field and applies a **specificity test**: a client's statement counts as an observation only if it says what happened, to whom, and roughly when. It also flags conflicts between sources, and moments worth asking about.
3. **Grills the consultant, one question at a time.** Each question comes with a recommended answer drawn from the transcripts, so the consultant can often just confirm. It only asks what the consultant could legitimately know. Each substantive answer gets a "how do you know?" probe and lands in one of three buckets: **sourced**, **judgment**, or **unsourced**. Unsourced answers stay out of the charter. When two sources conflict, it shows both and opens a follow-up instead of picking one.
4. **Reads the room.** For specific transcript moments, it asks about tone, hesitation, and body language: "At 04:36, when she said 'we'll see about budget,' how did that land?" It also asks once about anything that happened before or after the recording.
5. **Writes two files.** `charter.md` is client-ready, cited, and ends with follow-ups worded so they can be asked as written. `consultant-notes.md` is private.
6. **Checks its own work** for untraced claims, leaks of sensitive material, unfilled fields that have no follow-up, and length.

You can say "skip" (log it as a follow-up), "done for now" (write up what's there and pick it up next run), or ask it to draft without questions at all.

## The charter

| Section | What goes in it |
|---|---|
| **Market** | The people whose behavior we're trying to change |
| **Problem** | An observed issue or opportunity in the market that, if addressed, opens up chances to solve other issues. Includes cited observations, a confidence level (*seen once / seen repeatedly / measured*), the biggest unknown, and one to three **unlocks** ("Once ___ is solved, we can address ___, which today is blocked because ___") |
| **Objectives (ranked)** | Each is the headline we could run in a future newspaper if we succeed. It names the market, describes a change in their world, and carries a checkable time horizon |
| **Outcomes** | The new or changed behavior that shows an objective was met: who, from → to, and how we'll see it. Each one is scoped to one link of BJ Fogg's Ability Chain (*Tiny Habits*): **time, money, physical effort, mental effort, or routine** |
| **Appetite** | A rough order of magnitude plus a walk-away point. It isn't a staffing plan |
| **Directions and non-goals** | Up to three ideas, which are not commitments, plus what's deliberately excluded |
| **Follow-ups** | Each gives the field it fills, whom to ask, the question as written, and whether it blocks alignment |
| **Sign-off and change log** | After sign-off, the charter changes only by reopening, for one of three reasons: the problem evidence changed, the walk-away point was hit, or the market or top-ranked objective shifted |

`CHARTER-TEMPLATE.md` works by hand too. The guidance for each field is in comments.

## Install

**Claude Code:** copy the `drafting-solution-charters` folder into `~/.claude/skills/` (for all your projects) or `.claude/skills/` (for one project).

**Claude apps:** zip the `drafting-solution-charters` folder and upload it as a custom skill in your settings.

**Claude API:** upload the folder with the Skills API, sending every file each time.

```bash
curl https://api.anthropic.com/v1/skills \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "anthropic-version: 2023-06-01" \
  -F "display_name=drafting-solution-charters" \
  -F "files[]=@drafting-solution-charters/SKILL.md;filename=drafting-solution-charters/SKILL.md" \
  -F "files[]=@drafting-solution-charters/CHARTER-TEMPLATE.md;filename=drafting-solution-charters/CHARTER-TEMPLATE.md" \
  -F "files[]=@drafting-solution-charters/NOTES-TEMPLATE.md;filename=drafting-solution-charters/NOTES-TEMPLATE.md"
```

The skill is built for an interactive chat, where it grills the consultant. Over the API or in a batch job it drafts from the transcripts alone and lists the questions it would have asked.

## What testing showed

The skill has had one interactive run, in October 2026, against the fixture in `evals/`. That's a discovery call with a fictional HVAC company. A person played the consultant from a private script, and the skill never saw the script. The script included three deliberately unsourced claims, a pushback, a conflicting figure the consultant wanted used anyway, and sensitive context from outside the call. Treat the results as an indication, not a benchmark.

- **Every unsourced claim was held back** as a hypothesis, including when the consultant asked for one to be included anyway.
- **It didn't choose between conflicting figures** (70% vs. 62% first-time fix), even when told to, and opened a follow-up worded so the question could be asked without exposing anyone.
- **No room reads, private comments, or internal pressures leaked** into the charter, though several of them shaped it.
- **Two fixes came out of the run:** headline time horizons now have to be checkable, and the charter refers to front-line employees by role, not by name.
- The first-run grilling took about 16 exchanges.

## Evals

`evals/evals.json` holds three test prompts:

- the full interactive run, with `fixtures/brightline-consultant-briefing.md` as the consultant's script
- "just draft it," which should skip the grilling without inventing anything
- a request for a project charter, which shouldn't trigger the skill

Every name and figure in the fixtures is invented. Rerun the evals before you push a new version.

## License

MIT. See [LICENSE](LICENSE).
