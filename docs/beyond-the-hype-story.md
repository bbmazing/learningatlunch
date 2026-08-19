# Beyond the Hype: What AI Can Actually Do Today

Working draft of the deck story and talk script.

- **Speaker**: Bryan Bernardi, Analytics & Decision Making
- **Event**: Learning @ Lunch Series · AI, Digital & Data Series · OCBC Indonesia
- **When**: Kamis, 20 Agustus 2026, 11.30–12.30 WIB, virtual via Ms. Teams
- **Length**: 45–50 minutes of content, buffer for Q&A
- **Audience**: bank employees new to AI. No jargon without a plain
  explanation first. Pace stays relaxed: one idea per slide, pauses after
  each demo, questions welcome in the Teams chat throughout.
- **Status**: deck built at `web/beyond-the-hype.html` (30 slides; slide 2 = LLM
  intro with maker logos, slide 3 = the OCBC on-premise/Qwen setup).
  MoM AI and LuminaLM play as embedded videos; Statement Analyzer is a
  five-step flow diagram; Adverse News is an animated agent console in
  Part 2.

## Shape of the talk

Three acts. Act 1 demystifies the technology: an LLM is a text predictor,
which explains both its talents and its failures. Act 2 shows how tools and
agents turn that predictor into something that does work. Act 3 proves it
with four projects built inside the bank, then closes with how to start
using AI safely this week.

| Act | Slides | Minutes |
|---|---|---|
| Opening (cover, LLM, chatbot, on-premise, premise) | 1–5 | 9 |
| Act 1 · What is an LLM, really? | 6–16 | 17 |
| Act 2 · From chatbot to coworker, with Adverse News, LuminaLM and MoM AI live | 17–26 | 21 |
| Act 3 · The last use case + the pattern | 27–28 | 4 |
| Close + Q&A | 29–30 | 4 + buffer |

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

## Slide 2 · LLM — Large Language Models — 2 min

**Layout**: two-column; left bullets, right a scattered cloud of logo
cards: ChatGPT/OpenAI, Claude/Anthropic, Gemini/Google, DeepSeek,
Qwen/Alibaba, Z.ai/Zhipu, Mistral, Llama/Meta, Grok/xAI.
**On slide**: an LLM is an AI model trained on mountains of text — it
reads, writes and reasons in human language · every name is an LLM,
different makers, same core idea · ChatGPT is a product, the LLM is the
technology underneath · you have already used one.

**Say:**

> Before anything else, a name. The technology behind this wave is the
> LLM, the Large Language Model: an AI model trained on mountains of
> text, which reads, writes and reasons in human language. Every logo
> here is one — or a product built on one. ChatGPT from OpenAI, Claude,
> Gemini, DeepSeek, Qwen from Alibaba, Z.ai, and more. One correction
> worth making: ChatGPT is a product, the way an iPhone is a product.
> The technology inside is the LLM, and many companies build their own.
> Most of you have used at least one, probably this week.

## Slide 3 · The best first use case: a chatbot — 2 min

**Layout**: two-column; bullets left, right an animated chat:
a user message with a PDF attachment card (Laporan-Kinerja-Q2.pdf,
30 halaman) → typing dots → reply → follow-up → reply, playing in
sequence when the slide opens.

**Say:**

> One of the best uses of an LLM is also the simplest: a chatbot.
> Watch the rhythm on the right. You type, it answers, you refine. A
> conversation, not a search box. Summarise a thirty-page report, then
> turn it into an email for the team, all in one thread. It lifts your
> productivity and work efficiency: drafts, summaries and answers in
> seconds instead of hours. And later in this session I will show you
> ours.

## Slide 4 · Here at OCBC Indonesia: on-premise — 2 min

**Layout**: two-column; left bullets, right a "data center perimeter"
diagram: our hardware (GPU servers) + our model (Qwen 3.6, Alibaba's
open LLM) inside the OCBC box, "no public cloud" strike line beneath.
**On slide**: public AI tools run in someone else's cloud — bank data
cannot go there · we bought the hardware: GPU servers in our own data
center · we host our own LLM: Qwen 3.6 · every demo runs on this setup,
data never leaves the bank.

**Say:**

> One thing makes our situation different from just using those apps.
> Public AI tools run in someone else's cloud, and bank data cannot go
> there. So OCBC Indonesia went on-premise. We bought the hardware, GPU
> servers in our own data center, and we host our own model on it: Qwen
> 3.6, Alibaba's open LLM family — same technology as the logos you
> just saw, running entirely inside the bank. Every demo today runs on
> this setup. Prompts, documents, transcripts: nothing leaves our
> perimeter.

## Slide 5 · The premise (reworded) — 2 min

**Layout**: dark quote-style slide, or a two-column of headline chips vs.
one plain question.
**On slide**: a cluster of real headline fragments ("AI will take your
job", "AGI by 2027", "AI bubble about to burst") fading behind:
"AI already does useful work in this bank — now it needs your ideas."
Sub-line: understand how it works · watch it work · leave with ideas
for your own desk.

**Say:**

> You have seen the headlines. AI will take every job, AI will save the
> world, AI is a bubble. The noise is loud and most of it argues about a
> future nobody can verify. Here is the thing though: for us this is not
> a question anymore. AI already does useful work in this bank — you
> just saw the model it runs on. So today has a different goal. By the
> end you will understand how the technology works, you will have
> watched it work in four demos, and I want you to leave with ideas for
> your own desk. The best use cases will come from you, not from IT.

## Slide 6 · Divider — Act 1 — 30 sec

**Layout**: dark section divider.
**On slide**: "Part 1 / What is an LLM, really?"

**Say:**

> Let's open the box. What actually sits behind all of these tools?

## Slide 7 · Autocomplete on steroids — 3 min

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
> prediction. One confession before we move on: "word" is not exactly
> the right unit. The next slide sharpens it.

## Slide 8 · The correction: tokens, not words — 2 min

**Layout**: two-column; bullets left, right a tokenizer visual: the
savings-account sentence split into 9 colored token chips, the word
"menguntungkan" split into 3 pieces, and a ratio card (1,000 tokens ≈
750 English words).

**Say:**

> Here is the correction. The model does not read words. It reads
> tokens, small pieces of text. So what is a token? A numbered entry
> in the model's dictionary of about 100,000 pieces. A short word is
> one entry, and a long word like menguntungkan breaks into three.
> Now the dark strip: this is what the model actually receives. No
> letters. The sentence arrives as a list of numbers, and the word
> "account" is just number 3157. Inside, that number becomes a long
> list of numbers, thousands of them, and predicting the next token is
> math on those lists. AI never sees letters. It does very fast
> arithmetic on numbers. Rule of thumb: a thousand tokens is about 750
> English words. So next-word prediction is really next-token
> prediction. Same idea, exact unit.

## Slide 9 · Tokens are the meter — 2 min

**Layout**: two-column; bullets left, right two task cards with
animated cost bars (short email ~300 tokens vs 40-page report ~30,000
tokens) and three pricing chips (ChatGPT Free · ChatGPT Plus $20/mo ·
companies pay per token).

**Say:**

> Why do tokens matter? They are the meter. Every token in and every
> token out gets counted. A short email costs a few hundred tokens. A
> forty-page report costs tens of thousands. More tokens means more
> computing, and that costs money. For consumers it is a subscription:
> free with limits, or 20 US dollars a month for ChatGPT Plus. For
> companies like us it is per token, and this is the row that matters.
> Our self-hosted Qwen 3.6 works out around 3 dollars per million
> tokens, mostly the cost of running our own GPUs. Compare that with
> GPT-5.5, the best GPT today: 30 dollars per million output tokens.
> Ten times ours. That is why the bank
> sizes the model to the task. Nothing you need to do about it today.
> Just be aware that AI work has a price tag.

## Slide 10 · It read a lot, up to a date — 2 min

**Layout**: full-width timeline: a solid "what it read" panel with
source chips (books, articles and news, code, forums, websites), a red
"training stops here" flag, then a dashed empty "after that date"
panel. Takeaway line beneath.

**Say:**

> Where do good predictions come from? Reading. During training the
> model read a huge library: books, articles, code, forums, much of the
> public internet. Here is the catch. Training stops at a date. After
> that date the model has read nothing. This week&rsquo;s news, a new OJK
> regulation, today&rsquo;s rates: not in its memory. So it is fluent about
> the past and blind to the present. Keep that in mind, because in part
> two we fix it by handing the model fresh information.

## Slide 11 · What it does brilliantly — 2 min

**Layout**: 2×2 strength cards (Drafting, Summarising, Translating,
Explaining), each carrying a copy-able Bahasa starter prompt.

**Say:**

> Good news first. Anything shaped like language work, it does well.
> Draft an email or rewrite one. Summarise a forty-page circular into a
> page you can act on. Translate between Bahasa and English with the
> tone kept intact. Explain any concept at any level, as many times as
> you need, without getting impatient. If the task is language in,
> language out, it is probably good at it. That covers a surprising
> share of office work.

## Slide 12 · Prompting: be clear — 2 min

**Layout**: transformation flow: vague prompt card → three "+" chips
(task, background, format/tone/length) → clear prompt card.

**Say:**

> Before the tools, the skill you can use today: asking well. Clarity
> beats everything. Say the task exactly. Give the background the model
> cannot know. Name the format, the tone, the length. Compare these
> two: "tulis email ke nasabah" gets a generic answer. The clear
> version gets something ready to edit. And if the answer is not right,
> refine and ask again. It never gets tired.

## Slide 13 · Or use a framework: COSTAR — 2 min

**Layout**: six tiles: Context, Objective, Style, Tone, Audience,
Response.

**Say:**

> If you want a structure instead of remembering tips, use a framework.
> The one I like is COSTAR. Context: the background. Objective: the
> task, stated exactly. Style: how it should be written. Tone: how it
> should feel. Audience: who will read it. Response: the format, length
> and language of the answer. Six boxes to fill before you press enter.
> Skip what you do not need.

## Slide 14 · COSTAR, filled in — 2 min

**Layout**: the annotated prompt card (lines tagged C/O/S/T/A/R, in
Bahasa) beside the result: a complaint-recap report table with the
exact ordered columns, one cell showing N/A, and a green note "data
kosong ditulis N/A, tidak dikarang".

**Say:**

> Here is COSTAR filled in, and notice the prompt is in Bahasa. The
> framework works in any language. The scenario: generating a report,
> which is exactly where unwanted extras and hallucination hurt. So the
> R box does the heavy work. Kolom persis: Tanggal, Kanal, Jenis
> Komplain, Status, Tindak Lanjut. Hanya dari catatan saya. Data yang
> tidak ada tulis N/A. Jangan menambah atau mengarang. And on the
> right, the table it produced: five columns as ordered, and look at
> the last row. Where the notes had no follow-up, it wrote N/A instead
> of inventing one. Specify the shape and the rules, and you get the
> report you wanted. Copy this shape for your own reports.

## Slide 15 · You will never be good at it unless you try — 2 min

**Layout**: two-column; bullets and two check-chips left, right a
browser mock of Chat OCBC: padlock URL bar, dark chat body with the
greeting bubble beside the Qwen logo ("Hello Bryan Bernardi. How can I
help you today?"), starter prompt in the input.

**Say:**

> One more thing before we move on: practice. You will never be good
> at this unless you try, and you do not need to wait. We have our own
> internal ChatGPT. It is called Chat OCBC, it runs inside the bank on
> our own setup, and the address is on screen: bookmark it. For daily
> work this app is already enough: summaries, drafts, translations,
> explanations, ideas. Open it after this session and try the starter
> prompts from today. Use COSTAR when the answer matters. Your first
> ten prompts will be clumsy. Prompt fifty will not be.

## Slide 16 · The limits, and their fixes — 3 min

**Layout**: four limit rows, each with an arrow to a green fix chip:
no recent news → web search (Part 2) · sloppy arithmetic → calculator
(Part 2) · blind to our data → our documents (Part 2) · invents facts
→ citations plus your review.

**Say:**

> Now the honest part: the limits. Four big ones. Its knowledge stops
> at the training date, so no recent news. It predicts numbers instead
> of computing them, so check its arithmetic. Our customers and systems
> were never in its training, so it is blind to our data. And the
> famous one, hallucination: it can invent a fact, like an OJK rule
> that does not exist, formatted well and stated with confidence.
> Here is the key message of this slide: every limit on the left has a
> fix on the right, and most of the fixes are tools. Web search for
> fresh facts. A calculator for math. Our documents for our world. We
> will see exactly how in part two. The last one, hallucination, has a
> fix you own: ask for citations, and review before you send. That is
> part two. Let us go.

## Slide 17 · Divider — Act 2 — 30 sec

**Layout**: dark section divider.
**On slide**: "Part 2 / From chatbot to coworker" — four ideas: tools,
agents, grounding, and a human in the loop.

**Say:**

> Part two. How a text predictor becomes something that does work.

## Slide 18 · Tool calling: give it hands — 3 min

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

## Slide 19 · Agents: the loop — 2 min

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

## Slide 20 · Adverse News: an agent at work — 3 min

**Layout**: centered. Top: the compact five-step flow (names in → AI
writes searches → reads & filters → verdict + narrative → human
review, green). Below: the dark agent console playing line by line
(goal → web_search, court_lookup, sanctions_check with result counts →
filtering → generate_report), then a red arrow pops and the report
card lands outside the terminal: ADVERSE NEWS REPORT, HIGH badge, a
red PDF file chip (AdverseNews-PT-Maktour.pdf · 12 pages · ready for
review), officer review → KYC file. Footnote: *web search is a paid, licensed
tool; scraping is not allowed for regulatory reasons.

**Say:**

> Here is the agent loop for real. We added one tool: web search. A
> paid, licensed tool, because scraping is not allowed for regulatory
> reasons. We give the goal: screen this company for negative news.
> Now watch the console. The agent calls the search tool with its own
> queries. It checks the court databases, SIPP and Mahkamah Agung. It
> runs the sanction and PEP lists. It reads all 43 results and keeps
> the credible sources only, searching again where the signal is weak.
> And when the loop is done, watch the right side: out of the terminal
> comes the report. A risk verdict, a written narrative, every claim
> cited, an evidence appendix. The officer reviews it, and it goes to
> the KYC file. That is tool calling plus the loop. One goal in, one
> report out.

## Slide 21 · It has never read your documents. Provide them. — 2 min

**Layout**: a mini app, animated. Left: a "Project files" panel where four
files upload one by one — PRD-Lumina-v3.pdf, Timeline-Q3.xlsx,
SteerCo-Minutes-Jul.pdf, Project-Charter.docx. Right: a chat. A question
about a specific project comes in ("When did Project Lumina go live,
and who is the PIC?"), a scan line reports "searching 4 files… 2 relevant
pages found", the two matching files light up with match tags (row 18,
p. 4), and the answer card pops in — go-live 10 July 2026, PIC Bryan,
ADM — with a citation chip per claim. Caption: answers from your pages, "not found" instead of
inventing; engineers call this RAG / LLM Wiki.

**Say:**

> Third idea, and it fixes the blindness to our data. The model has
> never read your documents, so provide them. Upload the project files
> once: the PRD, the timeline, the minutes, the charter. Then ask about
> a specific project, in plain words. Watch the left panel: it finds
> the two files that matter and ignores the rest. The answer is
> written from those pages, and every claim carries a citation you can
> click and check. And if the answer is not in the files, it says not
> found. No inventing. Engineers call this RAG, or an LLM Wiki; the
> name matters less than the effect. The next slide is this exact idea, live in the bank.

## Slide 22 · LuminaLM — grounding, live in the bank — 4 min (video 0:50)

**Layout**: video slide — embedded `lumina-web.mp4` with poster frame,
side rail of four chips in plain words.
**On slide chips**: put the project files in (157 documents become one
place to search and ask) · ask in plain words (every answer shows the
page it came from) · see the whole plan (one timeline, built from every
file) · it writes documents too (drafts Word, Excel and PowerPoint).
**Video content, mapped**: (0:00) montage: charters, playbooks, status
packs, minutes piling up — "42 documents… 157 documents. Your
programme's truth is scattered across all of them." → (0:10) LuminaLM
title: "AI powered project management, without the headache" → (0:13)
notebook "Banking M&A Integration — Project Hampton": Living Wiki,
sources compiled into cross-linked always-current pages, knowledge graph
(21 pages, 103 links) → (0:22) Grounded Chat: "What are the strategic
imperatives for this programme?" → four imperatives, each with numbered
citation chips back to source documents → (0:31) Programme Timeline:
every workstream, dependency and tollgate in one Gantt view → (0:40)
Studio: format catalog — Workstream Charter (Word), Risk Register
(Excel), JESC Pack (PowerPoint), drafted from the wiki in the house
template → (0:46) outro.

**Say (setup, before play):**

> And this is grounding live in the bank: LuminaLM, built here. The
> pain: one project, 157 documents, and the answer always in a file you
> did not open. The video opens with that number. Watch three things.
> The files become one place you can search and ask. Every answer shows
> the page it came from, exactly like the last slide. And at the end it
> drafts documents for you: Word, Excel, PowerPoint. Fifty seconds.

**Say (after play):**

> A colleague who has read every project document and never forgets a
> page number. New joiners ramp up in days, old decisions stop getting
> relitigated from memory, and the Friday status pack drafts itself.
> And when the answer is not in the files, it says so. That is the last
> slide, on camera.

## Slide 23 · Be clear: one step at a time — 2 min

**Layout**: two rows, animated. Top row "Asking for magic": Recording →
AI summarizes → Minutes, which gets struck through in red with a flag
"misheard words and names go straight in". Bottom row "Proper
instructions: step by step, with a checkpoint": 1 Transcript first (AI
writes out who said what) → 2 Human edits (fix misheard lines, confirm
each speaker name, green human-in-the-loop card) → 3 Then summarize
(minutes from the corrected transcript). Caption: same rule as
prompting; MoM AI is built this way.

**Say:**

> Remember the prompting slide: be clear about what you want. The same
> rule applies when AI runs a whole job, doubled. The tempting way is one jump:
> recording in, minutes out. But then misheard words and wrong names go
> straight into the minutes. So we give the agent proper instructions,
> step by step. Transcript first: the AI writes out who said what. Then
> a human checkpoint: fix misheard lines, confirm the speaker names.
> Only then summarize, from the corrected transcript. That is exactly
> how MoM AI is built, and it is the next video.

## Slide 24 · MoM AI — clear steps, live in the bank — 4 min (video 0:30)

**Layout**: video slide — embedded `mom-ai-web.mp4` with poster frame, side
rail of four "watch for" chips.
**On slide chips**: drop in the recording (it writes the transcript:
who said what) · name the speakers (play a short sample) · fix the
transcript (correct wrong words before the summary) · get the minutes
(summary, actions, PIC · English or Bahasa, PDF or Word).
**Video content, mapped**: (0:00) problem card "Every meeting ends the
same way. Someone still has…" with note cards piling up → (0:05) MoM AI
logo, the ghost-with-headphones mascot, "Minutes of Meetings" → (0:08)
upload: New session in "Bob's meeting minutes" workspace — a
Sustainability Committee Q3 Review .wav, optional supporting PDFs the
model uses as context, meeting title/date/type/focus → (0:14) Speakers
step: 3 speakers detected, play a sample, name them, merge duplicates,
ignore noise; four-step sidebar Upload → Speakers → Transcript →
Minutes → (0:18) generating: "Identifying decisions and action items…"
→ (0:22) the Minutes: header with date, type, focus, next meeting;
Summary; Attendees (3) with roles; Agenda (5) with topic, discussion,
action needed and PIC per item; English / Bahasa Indonesia toggle,
Regenerate per section, version history, Copy / PDF / DOCX → (0:28)
outro: "Minutes, minus the meeting after the meeting."

**Say (setup, before play):**

> And this is that pipeline for real: MoM AI, built here. Every meeting
> ends the same way: someone still has to write the minutes. Thirty
> seconds, watch the steps from the last slide. Drop in the recording
> and it writes the transcript first: who said what. Name the speakers
> from a short sample. Fix the transcript where it misheard. Only then
> does it summarize: minutes with an action and a person in charge per
> item. Sound on.

**Say (after play):**

> Speech-to-text is the tool in the loop; the model drafts the
> structure. The draft is ready when the meeting ends, in English or
> Bahasa, exportable to PDF or Word. You review it, fix what it
> misheard, and send. Thirty minutes of typing becomes five minutes of
> checking — and the sign-off stays yours. One note for the chat: it
> handles a committee meeting recorded in one room as well as a Teams
> call.

## Slide 25 · Most requested: OCR, reading documents — 2 min

**Layout**: two-column. Bullets left (OCR = optical character
recognition; point it at a form, fields become data; example: transfer
forms; messy scans and handwriting included). Right: a slightly tilted
scanned "Form transfer" card in handwriting → red arrow → the OCR
result card with extracted fields and confidence chips (99%, 98%, 87%
in amber, 99%). Caption: seconds instead of minutes — but look at the
yellow one.

**Say:**

> One of our most requested projects is OCR: optical character
> recognition. AI that reads scans. Point it at a form and the fields
> become data. The example here is a transfer form: name, account
> number, amount, destination bank. With an LLM behind it, even messy
> scans and handwriting come out as structured fields, in seconds
> instead of minutes. But look at the confidence scores on the right,
> especially the yellow one. Fast is not the same as right. Hold that
> thought.

## Slide 26 · But remember: double-check — 2 min

**Layout**: centered title, 2×2 grid of cards, one per project shown
today. Each card: what the AI does, then a green ✓ line for the human
checkpoint. Adverse News (officer reviews before the KYC file) ·
LuminaLM (you open the cited page) · MoM AI (you fix the transcript,
sign off the minutes) · OCR (you double-check account number, name,
amount). Caption: AI drafts. A human verifies. Every time.

**Say:**

> But remember: double-check. This is the rule that ties everything
> together. Every project you just saw keeps a human in the loop after
> the AI produces its result. Adverse News: the officer reviews the
> report before it reaches the KYC file. LuminaLM: you open the cited
> page before you rely on the answer. MoM AI: you fix the transcript
> and sign off the minutes. And OCR: before anything moves, a person
> double-checks the account number, the name, the amount. AI drafts. A
> human verifies. Every time.

## Slide 27 · The last use case — Bank Statement Analyzer — 3 min

**Layout**: five-step flow diagram: bank statement (PDFs, phone scans)
→ OCR + fraud check → human verifies (green, human-in-the-loop tag) →
categorised (who, what type, business or personal) → dashboard.
Caption: hours of retyping become minutes of checking.

**Say:**

> The last use case, and a pain every credit and ops person knows.
> Statements from other banks arrive as PDFs and phone-camera scans,
> dozens of pages, every bank a different format, and someone retypes
> them for hours. Walk the flow with me. OCR reads every line, and a
> fraud check flags signs of tampering on the document itself. Then
> the checkpoint from the last slide: a person verifies the fields
> that matter, account numbers, names, totals. Next the model
> categorises every transaction: who was paid, what type of
> transaction, business or personal. And everything lands in one
> dashboard: money in, money out, account behaviour, ready for credit
> analysis. Hours of retyping become minutes of checking, and the
> credit judgment never leaves the analyst.

## Slide 28 · The pattern behind all four — 2 min

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

## Slide 29 · Using it well, starting this week — 3 min

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

## Slide 30 · Close + Q&A — 1 min, then open floor

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

1. Statement Analyzer video to arrive; drop it into slide 15 (same
   pattern as the three embedded ones) and rewrite that walkthrough
   against the footage.
2. Confirm product names and owning teams for each demo slide.
3. Check whether internal AI usage policy wording on slide 20 matches the
   bank's current guidance.
4. In the deck, videos play with native controls; `R` restarts the video
   on the current slide. Videos stay as separate files under
   `web/assets/videos/` — the standalone build inlines fonts and images
   but references the videos relatively, so keep the folder next to the
   HTML (or serve via GitHub Pages).
