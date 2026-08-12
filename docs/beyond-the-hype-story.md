# Beyond the Hype: What AI Can Actually Do Today

Working draft of the deck story and talk script.

- **Speaker**: Bryan Bernardi, Analytics & Decision Making
- **Event**: Learning @ Lunch Series · AI, Digital & Data Series · OCBC Indonesia
- **When**: Kamis, 20 Agustus 2026, 11.30–12.30 WIB, virtual via Ms. Teams
- **Length**: 45–50 minutes of content, buffer for Q&A
- **Audience**: bank employees new to AI. No jargon without a plain
  explanation first. Pace stays relaxed: one idea per slide, pauses after
  each demo, questions welcome in the Teams chat throughout.
- **Status**: rough cut. Demo slides carry placeholders until the four
  videos arrive; the per-demo scripts below get rewritten against the
  actual footage.

## Shape of the talk

Three acts. Act 1 demystifies the technology: an LLM is a text predictor,
which explains both its talents and its failures. Act 2 shows how tools and
agents turn that predictor into something that does work. Act 3 proves it
with four projects built inside the bank, then closes with how to start
using AI safely this week.

| Act | Slides | Minutes |
|---|---|---|
| Opening | 1–3 | 4 |
| Act 1 · What is an LLM, really? | 4–9 | 13 |
| Act 2 · From chatbot to coworker | 10–13 | 9 |
| Act 3 · Built here: four demos | 14–19 | 17 |
| Close + Q&A | 20–21 | 5 + buffer |

Timings assume each demo video runs 2–3 minutes. Adjust after the videos
arrive.

---

## Slide 1 · Cover — 1 min

**Layout**: cover (dark, skyline).
**On slide**: "Beyond the Hype / What AI Can Actually Do Today" ·
Learning @ Lunch · AI, Digital & Data Series · 20 Agustus 2026.

**Say:**

> Selamat siang, everyone, thank you for spending your lunch here. I'm
> Bryan from Analytics and Decision Making. For the next fifty minutes I
> want to do two things. First, explain what this AI wave is in plain
> language, no math, no buzzwords. Second, show you four working tools we
> built inside this bank, on video, so you can judge for yourself what AI
> can do today. Drop questions in the chat any time. I'll pause for them
> after each demo.

## Slide 2 · The hype vs. the question — 2 min

**Layout**: dark quote-style slide, or a two-column of headline chips vs.
one plain question.
**On slide**: a cluster of real headline fragments ("AI will take your
job", "AGI by 2027", "AI bubble about to burst") fading behind one line:
"Can it do useful work at a bank, today?"

**Say:**

> You have seen the headlines. AI will take every job, AI will save the
> world, AI is a bubble. The noise is loud and most of it argues about a
> future nobody can verify. I want to ask a smaller question, one we can
> answer before lunch ends: can this technology do useful work at a bank,
> today? By the end you'll have seen four answers, and each one is running
> here, built by teams you know.

## Slide 3 · Agenda — 1 min

**Layout**: three journey cards.
**On slide**: 01 What an LLM is · 02 From chatbot to coworker ·
03 Four projects, four demos.

**Say:**

> Three parts. Part one, what a large language model is. Once you see how
> it works, its strengths and its weird failures both make sense. Part
> two, how a chatbot becomes something closer to a coworker, through tools
> and agents. Those two words will make sense by then. Part three, the
> demos: a bank statement analyzer, an adverse news screener, a meeting
> minutes assistant, and Lumina, a project Q&A tool. All four run on the
> ideas from parts one and two.

## Slide 4 · Divider — Act 1 — 30 sec

**Layout**: dark section divider.
**On slide**: "Part 1 / What is ChatGPT, really?"

**Say:**

> Let's open the box. What sits behind ChatGPT, Gemini, Copilot, all of
> them?

## Slide 5 · Autocomplete on steroids — 3 min

**Layout**: two-column. Left: three bullets. Right: an animated
completion widget: "Saldo rekening Anda adalah ___" with candidate words
and probability bars.
**On slide bullets**: predicts the next word, over and over · trained on
patterns in text · every answer is built one word at a time.

**Say:**

> A large language model does one thing: given some text, it predicts the
> next word. Your phone keyboard does a tiny version of this when it
> suggests the next word of your SMS. An LLM is that idea scaled up by a
> factor of billions. When you ask it a question, it predicts the first
> word of a good answer, adds it, predicts the next word, and repeats
> until the answer is done. That's the whole trick. Everything impressive
> you have seen, essays, emails, code, comes from very good next-word
> prediction. Keep this picture, because it explains the failures we'll
> see in a minute.

## Slide 6 · How it learned — 2 min

**Layout**: stat row with three counters, plus a caption.
**On slide**: ~trillions of words read during training · months of
training compute · 0 databases inside. Caption: it learned patterns, it
did not memorise a lookup table.

**Say:**

> Where do good predictions come from? Training. The model read a huge
> slice of the public internet, books, articles, code, forums, and from
> that it learned patterns: grammar, facts, styles, how an apology email
> differs from a legal clause. One thing to hold on to: there is no
> database inside. It does not look answers up. It reconstructs them from
> patterns, the way you can hum a song you've heard many times without
> owning the recording. That is why it sounds fluent, and why it can be
> fluently wrong.

## Slide 7 · Brilliant and unreliable — 3 min

**Layout**: two-column comparison. Left card "Great at", right card
"Trips on".
**On slide**: Great at: drafting and rewriting · summarising long
documents · translation, English–Bahasa both ways · explaining concepts at
any level. Trips on: fresh events after its training data · precise
arithmetic · facts about your specific customers or systems · and it
invents details with full confidence (hallucination).

**Say:**

> So what falls out of next-word prediction? Strengths first. Anything
> shaped like language transformation, it does well: draft an email,
> rewrite it politely, summarise a forty-page circular into one page,
> translate between Bahasa and English. Now the failures, and this part
> matters more for us. Ask about last week's events and it may not know.
> Ask it to multiply two large numbers and check it. Ask about a specific
> nasabah and it knows nothing, your data was never in its training. And
> the famous one: hallucination. Ask for a regulation that supports your
> case and it may cite OJK regulation number such-and-such, well
> formatted, confident, and nonexistent. It is predicting what a citation
> looks like. Remember the rule from that: treat every fact it gives you
> as a draft to verify, in banking above all.

## Slide 8 · Context in, quality out — 2 min

**Layout**: two-column, bad prompt vs. good prompt in code-style cards.
**On slide**: Left: "tulis email ke nasabah". Right: role + situation +
what to include + tone + format, with the resulting difference noted
underneath.

**Say:**

> One practical skill before we move on: the quality of the answer tracks
> the quality of what you put in. Compare these two. "Write an email to a
> customer" gets you something generic. Now give it what you would give a
> new team member on day one: who you are, the situation, the three points
> to cover, the tone, the length. Same model, different result. That
> mental model, brief it like a smart intern who joined this morning, gets
> you eighty percent of prompting skill. The intern is brilliant, fast,
> and knows nothing about your job until you tell it.

## Slide 9 · The chatbot's three walls — 2 min

**Layout**: three icon cards.
**On slide**: Frozen in time (training cutoff) · Blind to your data (no
access to your files or systems) · All talk (writes text, takes no
action).

**Say:**

> Put it together and a plain chatbot has three walls. Wall one: time. Its
> knowledge stops at its training cutoff. Wall two: access. It cannot see
> your inbox, your core banking system, or that spreadsheet from this
> morning. Wall three: action. It produces words, it cannot send, search,
> or file anything. Keep these three walls in mind through the break,
> because part two is about how engineers knock them down. That is the
> difference between a toy and the tools you'll see in the demos.

## Slide 10 · Divider — Act 2 — 30 sec

**Layout**: dark section divider.
**On slide**: "Part 2 / From chatbot to coworker".

**Say:**

> Part two. How a text predictor becomes something that does work.

## Slide 11 · Tool calling: give it hands — 3 min

**Layout**: process flow, four steps with a worked example underneath.
**On slide**: You ask → model decides it needs a tool → tool runs (search,
database, calculator) → model answers with the result. Example: "Berapa
kurs USD hari ini?" → calls a rate lookup → answers with today's number.

**Say:**

> Knock down the walls with something called tool calling. Instead of
> asking the model to know everything, we hand it tools: a web search, a
> calculator, a database query, and we teach it to say "to answer this, I
> should use that tool". Ask for today's dollar rate. The model knows its
> training data is stale, so it calls the rate lookup, gets the live
> number, and writes the answer around it. The model supplies judgment
> and language; the tool supplies facts and action. This one idea powers
> almost every serious AI product you will touch this year, including all
> four demos coming up.

## Slide 12 · Agents: the loop — 2 min

**Layout**: circular loop diagram: Plan → Act → Check → repeat, exit
arrow "Done".
**On slide**: an agent = an LLM that loops with tools until the job is
finished.

**Say:**

> Now let it use tools more than once. Give the model a goal instead of a
> question, let it plan, act, look at the result, and decide what to do
> next, and loop until the job is done. That loop is what people mean by
> an AI agent. Take a real task from our world: screen this company for
> negative news. One search is never enough. You search the name, read
> ten articles, notice a different company with the same name, refine the
> search, check the directors too, then write up findings. An agent runs
> that same loop. You will watch one do exactly this in demo two.

## Slide 13 · Ground it in your documents — 2 min

**Layout**: simple flow: your documents → indexed → question → answer with
citations.
**On slide**: upload documents, ask questions, get answers with citations
from those pages. The fix for hallucination on document work.

**Say:**

> Last concept, and it fixes the wall-two problem, the model being blind
> to your data. Give it your documents at question time. Upload the files,
> and when you ask something, the system finds the relevant pages and
> instructs the model: answer from these pages, cite where you found it,
> and say so if the answer is not there. Grounding the model this way
> turns "confident guesser" into "fast reader of your files". Engineers
> call it RAG; the name matters less than the effect. Two of the four
> demos are built on it.

## Slide 14 · Divider — Act 3 — 1 min

**Layout**: dark section divider, four small chips naming the demos.
**On slide**: "Part 3 / Built here" · Statement Analyzer · Adverse News ·
MoM AI · Lumina.

**Say:**

> Everything so far becomes concrete now. Four projects, four videos, all
> built by teams here, all running on the ideas you just learned:
> prompting, tools, agents, grounding. For each one I'll tell you the
> pain it removes, play the video, and connect it back to the concepts.
> Questions in the chat after each.

## Slide 15 · Demo 1 — Bank Statement Analyzer — 4 min

**Layout**: demo slide. Placeholder frame for video, side rail with
"watch for" bullets.
**On slide**: reads uploaded bank statements (PDF and scans) with OCR ·
extracts every transaction into clean tables · summarises inflow, outflow,
balances for analysis.
**TODO**: swap in video, rewrite the walkthrough against actual footage.

**Say (setup, before play):**

> Start with a pain every credit and operations person knows: bank
> statements from other banks arrive as PDFs and phone-camera scans,
> dozens of pages, every bank with a different format. Someone reads them
> line by line and retypes transactions into a spreadsheet. Hours per
> application. This tool takes the upload, runs OCR to read the pages,
> and the model turns messy text into structured transactions, then
> summarises the account behaviour. Watch how it handles different
> formats without anyone configuring templates.

**Say (after play):**

> Concepts from part one and two at work: reading and restructuring text
> is the model's home turf, and OCR is a tool in the loop. The analyst
> still makes the credit judgment. The retyping is gone.

## Slide 16 · Demo 2 — Adverse News — 4 min

**Layout**: demo slide, same pattern.
**On slide**: screens companies (PT) and individuals for negative news ·
agent searches, reads, and filters same-name false matches · returns a
sourced summary.
**TODO**: swap in video, rewrite walkthrough.

**Say (setup):**

> Demo two, compliance and onboarding territory. Before we deal with a
> company or an individual, we screen for adverse news: fraud cases,
> sanctions, court records. Done by hand this means dozens of searches
> and a same-name problem; search a common name and most hits are about
> somebody else. This is the agent loop from part two, live. It plans
> searches, reads the results, discards articles about the wrong entity,
> digs further where the signal is bad, and writes a summary with links
> to every source. Watch the steps it takes; you can audit each one.

**Say (after play):**

> The output arrives with sources, so a human verifies in minutes instead
> of searching for an hour. The agent does the legwork, the officer makes
> the call.

## Slide 17 · Demo 3 — MoM AI — 4 min

**Layout**: demo slide, same pattern.
**On slide**: transcribes meeting recordings, Bahasa and English ·
drafts minutes: decisions, action items, owners, deadlines · minutes
ready to review after the meeting ends.
**TODO**: swap in video, rewrite walkthrough.

**Say (setup):**

> Demo three touches everyone: minutes of meeting. Somebody in every
> meeting is half-listening because they are typing notes, and the
> minutes still arrive two days late. MoM AI takes the recording,
> transcribes it, speech-to-text is the tool here, and the model drafts
> the minutes: what was decided, who owes what, by when. Notice in the
> video how it separates decisions from discussion.

**Say (after play):**

> A draft, ready when the meeting ends. You review it, fix what it
> misheard, and send. The half-hour of typing becomes five minutes of
> checking, and nobody has to skip the discussion to take notes.

## Slide 18 · Demo 4 — Lumina — 4 min

**Layout**: demo slide, same pattern.
**On slide**: a notebook for your project: upload BRDs, timelines,
vendor docs · ask anything, get answers with citations to the page ·
answers only from your documents, or it says it cannot find one.
**TODO**: swap in video, rewrite walkthrough.

**Say (setup):**

> Last demo, Lumina, and it is grounding from part two in production. A
> project accumulates hundreds of documents: requirements, decision
> memos, vendor contracts, meeting notes. Six months in, someone asks why
> a decision was made, and the answer lives in a file nobody can find.
> With Lumina you upload the project documents and ask in plain language.
> It answers from those documents with a citation to the exact page, and
> tells you when the answer is not in there instead of inventing one.
> That last behaviour is the hallucination fix, on camera.

**Say (after play):**

> Think of it as a colleague who has read every project document and
> never forgets a page number. New joiners ramp up in days, and old
> decisions stop getting relitigated from memory.

## Slide 19 · The pattern behind all four — 2 min

**Layout**: card grid or table mapping demo → concept → human's role.
**On slide**: Statement Analyzer = model + OCR tool · Adverse News =
agent loop + search · MoM AI = model + speech-to-text · Lumina =
grounding + citations. Bottom line: AI does the reading and drafting,
people keep the judgment.

**Say:**

> Look at the four side by side and one pattern emerges. Each one is the
> same text predictor from part one, plus tools, plus your documents.
> And in each one the person stays in charge of the judgment: the analyst
> approves the credit, the officer clears the name, you sign off the
> minutes. What the AI removed was the reading, retyping, searching and
> formatting that sat between people and their judgment. That is what AI
> can do today. Less magic than the headlines, and more useful.

## Slide 20 · Using it well, starting this week — 3 min

**Layout**: two-column: "Start here" and "Rules of the road".
**On slide**: Start here: summarise long documents · draft and polish
emails · translate Bahasa–English · explain unfamiliar terms. Rules:
never paste customer or confidential data into public AI tools · verify
every fact and number · you own what you send, AI output is a draft.

**Say:**

> Before we close, how to start, and how to stay safe. Start with tasks
> where a rough draft has value: summarise a long circular, draft a reply,
> translate a document, ask it to explain a term from a meeting you didn't
> follow. Three rules while you do. One: customer data and confidential
> material never go into public AI tools; use what the bank provides and
> follow our data policy. Two: verify facts, numbers and citations before
> they travel, you saw why in part one. Three: whatever you send still
> carries your name. Treat the output the way you treat an intern's
> draft: useful, fast, and reviewed before it leaves your desk.

## Slide 21 · Close + Q&A — 1 min, then open floor

**Layout**: dark closing slide, recap left, next steps right.
**On slide**: Covered: how LLMs work · tools and agents · four working
projects. Next: try one task this week · reach out to Analytics &
Decision Making about use cases in your unit.

**Say:**

> Fifty minutes ago the question was whether AI can do useful work at a
> bank today. You've now seen how the machine works, what its limits are,
> and four running answers built in this building. If a task in your unit
> looks like the pattern, lots of reading, retyping, searching or
> summarising, come talk to us in Analytics and Decision Making. Try one
> small task this week and see how it fits your work. Terima kasih, and
> let's take questions.

---

## Delivery notes

- Chill pace means silence is fine. After each demo, count three seconds
  before speaking, and read the chat out loud.
- Bahasa or English per slide as feels natural; the slides stay in
  English, the delivery can mix. Terms to keep in English: prompt, tool,
  agent, hallucination.
- The intern analogy is the spine of the talk. It appears on slides 8, 15
  and 20; keep the wording consistent so it lands as a theme.
- If running long, compress slides 6 and 13 (both are one-idea slides)
  and trim the demo setups, never the videos.
- `?static` on the deck URL snaps animations for a PDF handout after the
  session.

## Open items

1. Four demo videos to arrive; then rewrite each demo walkthrough against
   the footage (what is on screen, where to pause, what to point at).
2. Confirm product names and owning teams for each demo slide.
3. Check whether internal AI usage policy wording on slide 20 matches the
   bank's current guidance.
4. Build the deck at `web/beyond-the-hype.html` from `web/template.html`
   once this story is approved.
