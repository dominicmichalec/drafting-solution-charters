---
name: drafting-solution-charters
description: Turns transcripts of a consultant's conversations with a client or prospect into a solution charter (problem, ranked objectives, outcomes, appetite) plus private consultant notes. It grills the consultant one question at a time on what the transcripts leave open, and anything still unresolved becomes a client follow-up. Use whenever someone wants a solution charter, wants to turn discovery or sales-call transcripts into a charter, or wants to update an existing charter with new conversations, even if they don't say "skill". Not for project charters that authorize budget or staff, PRDs, design docs, or plain meeting summaries.
---

# Drafting solution charters from client conversations

A solution charter aligns two people, the **Owner** (the consultant) and the **Decider** (the client sponsor), on what problem is worth solving, what success would look like, and roughly how much it's worth. It does not pick a solution. Its value comes entirely from being trustworthy: one invented fact makes every line suspect, and a consultant can't share a charter they don't trust.

So the skill has three jobs:

1. Get everything the transcripts can support onto the page, with citations.
2. Get what *only the consultant* knows by grilling them, and keep their guesses out of the charter.
3. Turn everything that's left into follow-ups the consultant can ask the client.

You produce two files: `charter.md` (client-ready, from `CHARTER-TEMPLATE.md`) and `consultant-notes.md` (private, from `NOTES-TEMPLATE.md`). Read both templates in this folder before starting. Keep their headings, order and markers.

## Definitions (use these, not textbook ones)

- **Market:** the people whose behavior we're trying to change. They can be customers, users, employees, partners or a community, so the charter works for internal work too.
- **Problem:** an observed issue in the market (or an unmet opportunity) that, if addressed, would open up chances to solve other issues.
- **Objective:** what we could say in a future newspaper headline if we addressed the problem successfully.
- **Outcome:** a new or changed behavior, observed in the market, that shows we've achieved an objective. Each outcome is scoped to one link of BJ Fogg's Ability Chain as given in *Tiny Habits*: **time, money, physical effort, mental effort, or routine**. That link is the barrier that comes down. There are five links. Earlier versions of Fogg's model had a sixth, social deviance, which he has since dropped, so don't add it back.

## Step 1: Work out what kind of run this is

- **First run:** only transcripts are provided.
- **Later run:** a previous `charter.md` and `consultant-notes.md` are provided along with new transcripts. Follow Step 1 and Step 2 for the new transcripts only, then use the rules in "Later runs" below.

Transcripts can arrive in any form: pasted, attached, any vendor's export, or pulled from a meeting-notes connector if one is available. Never require a particular tool or format.

## Step 2: Intake

For each conversation, confirm the **date**, **attendees and their roles**, and **which attendee is the client sponsor** (the Decider). Assign each one an ID: T1, T2, and so on. Pull whatever you can from the transcript and ask the consultant only to confirm or fill gaps, in a single message. This is the one step where several questions go together, because they're quick facts.

Then note the transcript's quality, and work around it without inventing anything:
- **No speaker labels:** ask the consultant to say who said the passages you plan to rely on. Don't attribute quotes by guessing.
- **No timestamps:** cite with a short quoted phrase instead, `[T1 "we'll see about budget"]`.
- Record the quality in the notes so citation precision is visible.

## Step 3: Read before asking

Read every transcript in full and, before drafting anything, extract:

- **Quotes for each field**, copied word for word: market, problem, observations, unlocks, hoped-for results, budget or time signals, ideas for solutions, things ruled out.
- **Candidate observations.** Apply the **specificity test**: a client's statement counts as an observation only if it says *what* happened, *to whom*, and roughly *when*. "Last month two of our biggest accounts escalated over wrong invoices" passes. "Customers hate our invoicing" fails. Keep the failures as hypotheses, each with a follow-up asking for a specific recent example.
- **Moments worth a room-read probe:** short or evasive answers, topic changes, someone deferring to someone else, sudden energy, hedged commitments, long pauses, and anyone who was present but barely spoke.
- **Conflicts:** two figures or accounts that don't agree, including the same person contradicting themselves.
- **Solutions disguised as problems:** "the problem is we don't have an app." Note them. They belong under Directions, and the underlying problem still has to be found.

## Step 4: Grill the consultant

Start with a short summary of what the transcripts already settle, with citations, so the consultant doesn't get asked about it. Then ask about everything else **one question at a time**, in this order. Upstream answers change which downstream questions are worth asking.

1. Market
2. Problem and its observations, overall confidence, biggest unknown, unlocks
3. **Room-read pass** (see below)
4. Objectives and their ranking
5. Outcomes, including each one's ability link
6. Appetite
7. Directions and non-goals

Format every question the same way:

> **[Field]:** [The question]
> **My recommendation:** [your best answer from the transcripts, with citations, or "none, the transcripts don't touch this"]
> *Answer, or say "skip" to log it as a follow-up, or "done for now" to write up what we have.*

The recommendation matters. Most of the time the consultant should be able to just confirm it. There's no cap on questions, but don't ask anything the transcripts already answer with enough evidence.

### Only ask what the consultant could legitimately know

Ask the consultant about:
- context from off the transcript: emails, earlier work with this client, side conversations, what happened before and after the call
- what they saw and heard that the words don't show
- what ambiguous passages meant ("when they said 'the ops team', who did they mean?")
- calls that are theirs to make: ranking objectives, a first-pass appetite, which directions to list, how to phrase a headline

Don't ask the consultant to supply the client's facts, intentions or commitments: the client's numbers, budget, priorities or decisions. Those go straight to follow-ups. If the consultant offers one anyway, it goes through the source probe like any other answer.

### The source probe

After any substantive answer whose source isn't already clear, ask **"How do you know?"** Then put the answer in one of three buckets:

| Bucket | What it looks like | What happens |
|---|---|---|
| **Sourced** | A specific source they can point to: a transcript line, an email, a document, something they saw themselves, or a named person and a rough date | Fill the field and cite the source: `[consultant: email from COO, 2026-10-14]` |
| **Judgment** | A call that's the consultant's to make (see the list above) | Fill the field and mark it `[judgment]`. Record the reasoning in the notes |
| **Unsourced** | "I think", "probably", "they usually", "in my experience", a round number with no origin, or no real answer to the probe | Leave the field `_Open_`, create a follow-up, and record the answer as a **hypothesis** in the notes |

Ask the probe once. Don't argue with the answer. If the consultant pushes back ("just put it in"), explain once that unsourced answers wait as hypotheses so the charter stays shareable, then move on. Industry knowledge in general ("HVAC firms usually run 70% first-time fix") is unsourced for *this* client, however expert the consultant is.

**Cross-check sourced answers against the transcripts.** If the consultant says "they told us churn was 20%" and the transcript says 12%, don't pick one. Show both, record the conflict in the notes, mark the field open, and create a follow-up.

**Provenance.** Every observation carries `[client-reported]` (the client told us) or `[consultant-observed]` (the consultant saw it directly), so the Decider can see whose eyes the evidence came through.

### The room-read pass

Transcripts miss tone, energy, body language and silence, which are often the most important inputs. After the problem section, go through the moments you flagged in Step 3, **one moment at a time**, quoting the line:

> **[T1 @14:32]** Dana: "We'll see about budget." How did that land? Was it a brush-off, real uncertainty, or something else? Anything in how she said it?

Then ask one **off-transcript sweep**: what happened before the call started and after it ended, whether anyone was in the room who doesn't appear in the transcript, and whether anyone who barely spoke seemed to have views.

What the consultant reports here is `[consultant-observed]` evidence. It can change the charter's *content*: a hesitant answer about appetite lowers that field's confidence and creates a follow-up. It never appears in the charter as a reading of a person. "The COO seemed unconvinced" goes in the notes, never in the charter.

### Ability links

For each outcome, if the transcripts don't make the link clear, use Fogg's discovery questions as the probe: *Does this behavior take too much time today? Cost too much? Too much physical effort? Too much mental effort? Does it clash with an existing routine?* The link is whichever barrier the change removes. If the consultant can't say, the outcome stays open with a follow-up.

### Stopping

- **"skip" / "log it":** create the follow-up now, record any partial answer as a hypothesis, and move to the next question.
- **"done for now":** stop asking and go to Step 5. List anything you didn't get to under "Questions for the consultant" in the notes, so the next run picks up from there.
- **No one to ask** (a batch or API run, or "just draft it"): skip the grilling. Fill only what the transcripts support, and put every question you would have asked, with its recommended answer, under "Questions for the consultant."

## Step 5: Write both files

**charter.md** follows `CHARTER-TEMPLATE.md`. Remove the template's guidance comments from the output.

- Every filled field carries its citation and markers. Fields you couldn't fill read `_Open: FU-n_`. Never leave a field blank, and never fill one with a placeholder that looks like content.
- **Headlines** must name the market as subject, describe a change in their world (not the client's action or output), and carry a time horizon a reader could check later: a date or quarter ("by Q4 2027"), or a span tied to a dated event. "About a year after the pilot starts" is not checkable until the pilot has a start date, so write it and add a follow-up. If the material only supports a weaker headline, write the best honest one and add a follow-up.
- **Outcomes** need who, from → to, ability link, and how we'll see it. A target is optional. Include one only when there's a source, and label its confidence.
- **Unlocks** use the "Once / we can address / blocked because" form, or "No clear unlocks yet."
- **Directions:** three at most, worded as ideas. Any solutions disguised as problems go here.
- **Follow-ups:** each is wording the consultant could read aloud to the person it's addressed to. It names no one's mood, rival, hesitation or internal politics. Use *blocks alignment* priority for anything the Decider couldn't sign without: the market, the problem, at least one observation, the top objective and its outcomes, and the appetite. Everything else is *strengthens charter*.
- **Status** is Draft until the Decider has signed.

**consultant-notes.md** follows `NOTES-TEMPLATE.md`. It holds the intake table, the room reads tied to transcript moments, the hypotheses (keyed to follow-up IDs), source conflicts, the reasoning behind judgment calls, tactics for the next conversation, unasked questions, and the run log.

## Step 6: Check before handing over

Go through both files as a skeptical Decider would:

1. Does every filled field in the charter trace to a transcript citation, a consultant source, or `[judgment]`? Anything else is a leak. Move it to a hypothesis.
2. Does every observation pass the specificity test and carry provenance and confidence?
3. **Client-safety:** read the charter as the client sponsor would. Does any line reveal a room read, a hypothesis, a rival, or what someone said privately? Move it to the notes. Does it name an individual employee next to a failure, a complaint or a personal estimate ("Luis didn't have the part")? Use the role instead ("a tech"). Names go in the notes.
4. Does every `_Open_` field have a follow-up, and does every follow-up point at a real field?
5. Do the sections 1–5 fit on about two pages? If not, the excess probably belongs in a design doc, a plan or the notes.

Fix anything that fails, then check again.

Then tell the consultant, in a few lines: what got filled, how many follow-ups are open and how many of those block alignment, and the single most important thing to ask in the next conversation.

## Later runs

Bring in the previous `charter.md` and `consultant-notes.md` along with the new transcripts, then:

1. **Close follow-ups** that the new conversations answer. Fill the field, cite the new transcript, mark the follow-up Closed with the citation, and promote or discard the matching hypothesis.
2. **Re-grade evidence.** A specific example can turn a hypothesis into an observation. Corroboration can move *seen once* to *seen repeatedly*. A claim the client walked back gets downgraded or removed, and the change is noted.
3. **Grill only on what's new:** new gaps, new conflicts, room reads for the new conversations, and any "Questions for the consultant" left over from last time.
4. **Respect alignment.**
   - **Status is Draft:** revise freely, and log each change in the notes' run log.
   - **Status is Aligned:** don't edit the aligned content. If the new evidence would change it, check it against the three reopen triggers: (1) the problem evidence changed, (2) the appetite's walk-away point was hit, (3) the market or the top-ranked objective shifted. If one applies, propose the reopen to the consultant with the evidence. If they agree, set Status back to Draft, bump the version, and add a change-log row naming the trigger, so the Decider can re-sign. If none applies, record the evidence in the notes and leave the charter as it is.
