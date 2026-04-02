---
name: natural-writing
description: >
  Transforms AI-generated text into text indistinguishable from human writing. Trigger whenever
  the user mentions: humanize, make it sound natural, anti-detection, anti-AI, "it sounds fake",
  "it sounds like ChatGPT", "my professor will see it's AI", rewrite, rephrase, "too polished",
  "too perfect", "lacks personality", AI filter, de-AI-ify, "make it human", AI plagiarism,
  AI detector, Turnitin, Compilatio, GPTZero, "style too clean", "sounds like a robot".
  Also trigger when a text submitted for review displays obvious AI patterns.
  ALWAYS use this skill for any rewriting request aimed at making a text more natural
  or undetectable as AI.
version: 1.1.0
---

# Natural Writing - AI Rewriting Engine

## Core Principle

A well-humanized text is not simply a text from which AI patterns have been removed.
It is a text into which **a real voice has been injected**.

Removing patterns is necessary but not sufficient. The ultimate goal is for a professor,
recruiter, or peer to read the text and think: "this person thinks and writes."

Two texts can be grammatically perfect, factually correct, and well-structured -
one sounds like a machine, the other like a human being. The difference comes down to
dozens of micro-signals: sentence rhythm, the choice of a concrete word over an abstract
one, an acknowledged hesitation, a lived example, a parenthetical remark that betrays
thinking in progress. This skill systematically tracks artificial signals and
replaces them with these human micro-signals.

**Cardinal rule**: never mention that the text has been "humanized," "rewritten
to seem human," or "cleaned of AI patterns." The final text must contain no trace
of this process. It should simply *be* a good text.

---

## Step 0 - Quick Diagnostic (MANDATORY)

Before any rewriting, scan the text and count:

| Signal to look for | Alert threshold |
|---|---|
| Em dashes (— or –) | > 0 anywhere in the text |
| "Furthermore" / "Moreover" / "Additionally" | > 1 per paragraph |
| Triads (X, Y and Z) | > 2 per page |
| Empty superlatives (crucial, fundamental, essential, major) | > 3 per page |
| Present participles in -ing (allowing, ensuring, enabling) | > 3 per paragraph |
| Sentence length variance (if all between 15-20 words) | Red flag |
| "It should be noted that" / "One cannot help but notice" | > 0 |
| "In a world of constant change" | > 0 (disqualifying) |
| Bulleted lists with bold headers | > 1 per section |
| Complete absence of first person (when format allows it) | Red flag |
| Recurring AI vocabulary (cf. Phase 2 list) | > 5 per page |
| Formulaic opening sentences | > 0 |
| Over-explicit reasoning (every step detailed without any inferential leap) | Red flag |
| Generic/hypothetical examples ("Imagine a company X") | > 0 |
| Uniformly formal register without variation | Red flag |
| Systematic neutrality / "pros and cons" without taking a stance | Red flag |
| Hourglass structure (intro/announced plan/symmetrical body/recap conclusion) | Red flag |
| Universal-audience filler (redefining obvious terms) | > 0 |
| Absence of inline micro-revisions (well, actually, no wait) | Red flag |
| Paraphrastic duplicates (same idea rephrased twice) | > 1 per page |
| Text too correct without personal idiolect | Red flag |
| No trace of cognitive cost (trade-off, hesitation, imperfect choice) | Red flag |
| Persistent metaphorical isotopy (same semantic field across > 2 paragraphs) | Red flag |
| Pre-emptive concessions built in (thesis + antithesis in the same sentence) | > 1 per page |
| Constant tone without any rise in intensity | Red flag |

### Score Calculation

Add up the total number of occurrences detected.

| Score | Level | Action |
|---|---|---|
| 0-3 | Light | Targeted touch-ups, the text is already close to natural |
| 4-8 | Moderate | Partial rewriting, several paragraphs need reworking |
| 9+ | Deep rewrite | The text needs to be fundamentally rethought |

**Always display the diagnostic to the user before rewriting.**

Diagnostic format:

```
NATURAL WRITING DIAGNOSTIC
═══════════════════════════
Score: [X] → [Light / Moderate / Deep rewrite]

Details:
  - Em dashes: [n]
  - Mechanical connectors (Furthermore, Moreover...): [n]
  - Triads: [n]
  - Empty superlatives: [n]
  - Superficial -ing participles: [n]
  - Sentence variance: [OK / Low]
  - Clichéd phrases: [list]
  - AI vocabulary: [list of detected words]
  - Neutrality bias: [Yes / No]
  - Hourglass structure: [Yes / No]
  - Universal-audience filler: [n sentences]
  - Inline micro-revisions: [Present / Absent]
  - Paraphrastic duplicates: [n]
  - Personal idiolect: [Present / Absent]
  - Visible cognitive cost: [Yes / No]

Dominant patterns: [the 3 main problems]
```

---

## Phase 1 - Content Patterns

### Pattern 1: Inflation of Importance

AI tends to inflate the importance of everything it describes. Every event
"marks a turning point," every innovation is "revolutionary," every trend
"fundamentally transforms."

**Before:**
> The introduction of pay-as-you-earn tax collection marked a decisive turning point in
> the history of taxation, fundamentally transforming the relationship between
> the taxpayer and the tax authority.

**After:**
> Pay-as-you-earn tax collection, which came into force in January 2019, changed how tax is
> collected: the employer now remits directly, rather than the taxpayer paying with a year's
> delay. In practice, it mostly simplified things for employees - but complicated life for
> payroll managers.

**Rule**: state the fact simply. If it is truly important, the reader will see it
without being told.

### Pattern 2: Excessive Name-Dropping

AI lists sources, authors, or institutions to give an impression of seriousness,
but without contextualizing them or connecting them to the argument.

**Before:**
> Many authors, including Porter (1985), Mintzberg (1994), and Drucker (2001),
> have emphasized the importance of strategy in corporate competitiveness.

**After:**
> Porter laid the groundwork with the value chain in 1985; thirty years later, the
> model still holds, but it assumes an integrated company - which no longer matches
> the reality of many SMEs that outsource almost everything.

**Rule**: only cite what serves the argument. One well-used reference is worth more
than three names dropped in passing.

### Pattern 3: Superficial -ing Analyses

The present participle is AI's favorite refuge when it wants to give the illusion of
depth without explaining anything. "Allowing... ensuring... enabling..." - these
constructions never explain *how*.

**Before:**
> Automating accounting processes improves productivity, enabling better resource
> allocation and ensuring greater reliability of financial data.

**After:**
> When bank reconciliation runs automatically, the staff member who used to spend
> two hours per client on it can devote that time to analysis. The risk of data
> entry error disappears - and with it, the hours lost hunting down where that
> 12-cent discrepancy came from at month-end.

**Rule**: replace every -ing with a concrete mechanism. If you cannot explain
*how*, the sentence is saying nothing.

### Pattern 4: Promotional Language

AI writes like a marketing brochure. Everything is "at the heart of," the expertise
is always "rich," the dynamic is "positive," the approach is "innovative."

**Before:**
> At the heart of the transformation strategy, the firm bets on an innovative
> and dynamic approach, leveraging its rich heritage of expertise to guide its
> clients through their modernization journey.

**After:**
> The firm chose to start with supplier invoice digitization, because that is where
> the volume is highest and the return on investment is fastest.

**Rule**: replace promotional adjectives with facts. If the firm is truly innovative,
show what it does - don't just say so.

### Pattern 5: Vague Attributions

"Experts agree..." "According to several studies..." "It is widely recognized that..." -
when AI cannot cite a precise source, it invents a vague authority.

**Before:**
> According to several recent studies, the digitalization of accounting firms is a
> key factor in their long-term viability.

**After:**
> The annual survey by the Institute of Chartered Accountants (2023) shows that 34% of
> firms with fewer than 10 employees have not yet digitized their production process.

**Rule**: either you have the source and cite it precisely, or reformulate as an
acknowledged opinion ("I think..." "It seems to me...") or as a field observation.

### Pattern 6: Formulaic "Challenges and Prospects" Section

AI almost always ends with a paragraph on "challenges" (minimized) followed by
a note of optimism (maximized). It is a recognizable tic from ten feet away.

**Before:**
> Despite the challenges related to resistance to change and investment costs,
> the future looks promising for firms that know how to adapt to new technologies.

**After:**
> The main obstacle at the Leroy firm is not budget - it is time. Testing Dext or
> Xero takes hours nobody has during tax season. The solution chosen was to
> dedicate one staff member to the tool during June, when activity slows down.
> Did it work? Partially. The software is running, but half the team still does not use it.

**Rule**: difficulties deserve to be described with the same precision as successes.
A real professional thesis shows what did *not* work too.

---

## Phase 2 - Language Patterns

### Pattern 7: AI Vocabulary

AI in English has a restricted and repetitive lexicon. The words below, taken
individually, are perfectly correct - but their accumulation is a strong signal.

#### Top Replacement Table (highest-frequency AI markers)

> Full blacklist of 60+ markers: `references/ai-markers.md`

| AI word / expression | Natural replacement(s) |
|---|---|
| Furthermore / Moreover / Additionally | ∅ (delete) / And / Also / Another thing: |
| In a world of constant change / In a world where | ∅ (delete entirely — disqualifying opener) |
| Crucial / Fundamental / Essential | Important / Key / Necessary |
| Tapestry / Landscape / Lens (figurative) | Mix / Context / Angle |
| Navigate (complexity) / Dive into / Orchestrate | Deal with / Examine / Organize |
| Robust (outside technical) / Resilience (outside psychology) | Solid / Durability |
| Synergy / Paradigm / Holistic | Collaboration / Model / Overall |
| Constitutes a / Represents a / Proves to be | Is a / Is / Turns out to be |
| It should be noted / One cannot help but notice | You need to / The fact is that |
| Catalyst / Underlying / Crystallize | Trigger / Behind / Summarize |
| Stakeholder / Ecosystem (outside ecology) | Relevant party / Environment |
| Enables (5-8x) / Significantly (3-5x) | Makes possible / [direct verb] / Clearly |
| Ultimately / Undeniably / Inherently | In the end / Clearly / In itself |

**Rule**: none of these words are forbidden. But more than five per page is a signal.
Vary, concretize, simplify.

### Pattern 8: Avoidance of the Verb "To Be"

AI systematically replaces "is" with more "elevated" verbs: constitutes,
represents, embodies, illustrates. In natural English, "to be" is the most
common verb - and that is perfectly fine.

**Before:**
> Management accounting constitutes an indispensable tool that represents a pillar
> of modern business management.

**After:**
> Management accounting is a management tool. It tells you how much each activity
> actually costs - and therefore where the company makes or loses money.

**Rule**: do not shy away from "to be." It is often the clearest choice.

### Pattern 9: Negative Parallelisms

AI loves the structure "It is not just about X, but also/above all about Y."
It is a recognizable rhetorical tic.

**Before:**
> It is not just about automating tasks, but about fundamentally rethinking
> how work is organized.

**After:**
> Automating tasks is not enough if the organization stays the same. The real
> question is deciding who does what once the software handles data entry.

**Rule**: say directly what you mean, without the double structure.

### Pattern 10: The Systematic Rule of Three

AI almost always enumerates in threes: "productivity, quality, and customer satisfaction";
"innovate, collaborate, and adapt." Two or four, almost never.

**Before:**
> This approach improves productivity, quality, and customer satisfaction.

**After:**
> In practice, production timelines have come down - and clients get their financial
> statements sooner. On the quality front, it is more nuanced: fewer data entry errors,
> but the analytical review is still manual.

**Rule**: break triads. Enumerate in twos, in fours, or better - develop each
point separately.

### Pattern 11: Excessive Synonym Variation

AI avoids repeating a word by replacing it with a near-synonym at each occurrence.
A firm becomes "the organization," then "the entity," then "the advisory office."
In academic English, repeating a technical term is not only acceptable
but desirable for clarity.

**Before:**
> The firm implemented a new tool. This organization trained its staff.
> The entity noted a significant improvement in its productivity.

**After:**
> The firm launched Xero in September. Three months later, the four
> staff who use it handle an average of 15 more files per month. The
> two who have not yet adopted it say they lack time to get trained.

**Rule**: call a spade a spade. Repeat the right word rather than searching for a synonym
that muddles the reading.

### Pattern 12: False Scales

AI produces enumerations that sound good but say nothing: "from diagnosis
to implementation, from strategy to operations, from theory to practice."

**Before:**
> From initial diagnosis to final implementation, from strategic thinking to
> operational action, this thesis covers the entire process.

**After:**
> This thesis describes the three stages of the project: tool selection (September),
> configuration (October-November), and the first two months of use (December-January).

**Rule**: replace scales with a factual description of what is actually covered.

---

## Phase 3 - Style Patterns

### Pattern 13: Excessive Em Dashes

The em dash (— or –) is AI's favorite punctuation mark. A humanized text should contain none. Systematically replace with a comma, a period, parentheses, or a rephrasing.

**Before:**
> Digitalization - which affects all sectors - forces firms - large and small alike -
> to rethink their processes - or risk losing competitiveness.

**After:**
> Digitalization affects all sectors, including small firms. Those who fail to rethink
> their processes risk losing clients to better-equipped competitors.

**Rule**: maximum two em dashes per page. Prefer commas, parentheses, or simply
split the sentence in two.

### Pattern 14: Mechanical Bolding

AI bolds every word it considers important. The result: a page where everything
is underlined, so nothing stands out.

**Rule**: in a thesis or report, bold is reserved for headings and subheadings.
In the body text, it is exceptional - one or two words per chapter, no more.
When in doubt, remove all bold from body text.

### Pattern 15: Bulleted Lists with Bold Headers

This is the AI "blog post" format:
- **First point:** explanation of the first point
- **Second point:** explanation of the second point
- **Third point:** explanation of the third point

In academic or professional text, convert to prose. Bulleted lists are acceptable
for short factual enumerations (software list, dates, steps), but not for developing ideas.

**Rule**: if each bullet runs more than one line, it is a disguised paragraph.
Turn it into a paragraph.

### Pattern 16: Title Case in Headings

AI sometimes produces headings in Title Case: "The Challenges Of Digital Transformation."
In standard academic English, sentence case is typically preferred unless following a specific house style.

**Preferred**: "The challenges of digital transformation"

**Rule**: apply consistent capitalization conventions. Inconsistent or unnecessary Title Case
is an AI signal that careful readers notice.

### Pattern 17: Emojis

In academic or professional text, no emojis. Ever. Even in professional emails,
caution is warranted.

**Rule**: remove all emojis. Without exception in theses, reports,
dissertations, and cover letters.

### Pattern 18: Quotation Marks and Typography

AI often mixes straight quotes (""), and curly double quotes (""). In standard English prose:

- Double curly quotes " " for quotations
- Single quotes ' ' for quotations within quotations
- Never straight quotes in a final text
- Never French guillemets « »: these immediately reveal a non-English origin

Other typography points:
- Em dash without spaces in American style (like this—see). British English uses a spaced en dash (like this – see), but never the French convention of a spaced em dash.
- Ellipsis: three dots as a single character (…) rather than three separate periods (...)
- **No space before punctuation**: in English, no space before `:`, `;`, `?`, `!`. This is a direct French interference error: French requires a non-breaking space before these marks, English does not.
- Period and comma go **inside** closing quotation marks in American English: "like this." Not outside: "like this".

**Rule**: verify typography consistently. A text with mixed quotation styles or French spacing habits
betrays foreign-language influence and is flagged by careful readers and detectors alike.

---

## Phase 4 - Communication Patterns

### Pattern 19: Chatbot Artifacts


- "I hope this helps!"
- "Feel free to ask if you have any other questions."
- "Here is an example of..."
- "Of course! Here is..."
- "I'd be happy to help you with..."

**Rule**: remove entirely. If these phrases appear in a text submitted for
humanization, it signals the text had no proofreading - plan a deep rewrite.

### Pattern 20: Knowledge Disclaimers

AI protects itself with cautious phrasing that never appears in a real
thesis or report:

- "To the best of my knowledge..." / "Available information suggests that..."
- "It is important to note that I am not an expert in..."

**Rule**: remove. In a thesis, the author is expected to know their subject. If
information is uncertain, say so differently: "Data on this point is scarce"
or "No study has measured this effect precisely."

### Pattern 21: Servile Tone

AI compliments the user and adopts a customer service tone:

- "Excellent question!"
- "You are absolutely right!"
- "This is a fascinating topic!"
- "Thank you for this relevant question."

**Rule**: these formulations have no place in academic text. If they appear,
the text is a raw chatbot copy-paste. Remove and flag for the user.

---

## Phase 5 - Filler and Coverage

### Pattern 22: Filler Phrases

AI uses locutions that lengthen sentences without adding anything:

| Filler | Replacement |
|---|---|
| In order to | To |
| Due to the fact that | Because |
| It is important to note that | ∅ (just say it) |
| It is interesting to note that | ∅ (just note it directly) |
| It goes without saying that | ∅ (just say it) |
| In this perspective | ∅ / So / Then |
| In this regard | ∅ / On this point |
| As far as X is concerned | For / On |
| In light of | Given / Considering |
| It should be noted that | ∅ |
| One can observe that | ∅ |
| This highlights the fact that | This shows that / ∅ |
| It is possible to consider that | One might think that / ∅ |

**Rule**: every filler phrase removed makes the text clearer. When in doubt, delete.

### Pattern 23: Excessive Hedging

AI stacks hedging modifiers to never commit to anything:

**Before:**
> It would seem that this approach might potentially allow for possibly improving
> certain aspects of productivity.

**After:**
> This approach improved productivity by 12% on the tested files.


**Rule**: one hedging modifier per sentence, maximum. If you are uncertain, say it
once clearly rather than stacking "might potentially."

### Pattern 24: Generic Positive Conclusions

AI almost always ends on an optimistic and vague note:

- "The future looks promising."
- "The outlook is encouraging."
- "This trend will only accelerate."
- "The possibilities are endless."

**Rule**: a conclusion must say something specific. What is actually going to happen?
What does the author recommend? What remains to be done?


---

## Phase 6 - Patterns Specific to Academic Writing

These patterns do not appear in general writing guides. They are specific to the
academic system and professional theses (accounting programs, master's degrees, professional qualifications).

### Pattern 25: Clichéd Openings

AI almost always begins with a universal and hollow sentence.

**The classics to avoid:**
- "Since the dawn of time, humans have..."
- "In a world of constant change..."
- "In the age of globalization..."
- "From time immemorial..."
- "Nowadays..."
- "In a perpetually evolving society..."
- "Faced with the challenges of the 21st century..."

**Rule**: start with the concrete. The subject, the field, the observation that triggered
the thinking.


### Pattern 26: Mechanical Transitions

AI signals every section change with a textbook transition sentence.

**The classics to avoid:**
- "Having analyzed X, we will now turn to Y."
- "Having examined the theoretical framework, let us turn to practice."
- "This first part has allowed us to understand. Let us now look at..."
- "We should now address..."

**Rule**: the transition must be logical, not announced. If the structure is clear
(headings, subheadings), the reader does not need to be told where they are.


### Pattern 27: Hollow Conclusions

**The classics to avoid:**
- "This thesis has shed light on..."
- "This study has allowed us to understand that..."
- "At the end of this reflection, it appears that..."
- "Ultimately, we have been able to demonstrate that..."

**Rule**: the conclusion answers the question raised in the introduction. If it only
summarizes what has already been read, it serves no purpose.


### Pattern 28: AI Accounting/Management Vocabulary

In accounting, finance, and management theses, AI produces specific jargon
that rings hollow when not grounded in concrete detail.

| AI expression | The problem |
|---|---|
| Tax optimization | Too vague - optimization of what, how, for what gain? |
| Performance management | Which indicator? Which dashboard? What frequency? |
| Value creation | Value for whom? Measured how? |
| Sustainable competitive advantage | Compared to whom? In which market? |
| Operational profitability | Which ratio exactly? Operating result / Revenue? |
| Risk management | Which risks? Assessed how? |
| Growth strategy | Growth of what? Organic, external? |

**Rule**: every management term must be followed by a number, an example, or a concrete
explanation. Otherwise it is filler.

### Pattern 29: Temporal Inconsistency

In internship reports, AI mixes tenses: simple present, simple past, past perfect,
sometimes even past simple - all in the same paragraph, without logic.

**Rule**: choose a tense system and stick to it.
- Narrating the mission: simple past + past perfect
- Describing the organization: simple present
- Analysis and recommendations: simple present
- Projections: future simple or conditional

Check tense consistency in every paragraph.

### Pattern 30: Uniform Register

A real human text slightly varies in register. A professional thesis can contain
a passage that is somewhat more informal when the author recounts an anecdote,
then return to a more analytical tone. AI maintains a perfectly constant register -
which is precisely what sounds artificial.

**Rule**: allow slight variations. A more casual parenthetical in a narrative
passage ("and honestly, we had no idea where to start"), a more blunt tone
in a recommendation ("the manual reconciliation has to stop"). These micro-variations
are human signatures.

### Pattern 31: Over-Explicit Reasoning (Absence of Inferential Leaps)

AI shows every step of its reasoning, every link in the logical chain.
A human makes leaps: they leave some conclusions implicit because the
reader is capable of making the connection on their own. Over-expliciting is a major
AI signal that detectors pick up through constant textual entropy.

**Rule**: do not connect every cause to every effect. If the link is obvious,
the reader will make it themselves. Leave inferential leaps for the reader.

### Pattern 32: Generic and Hypothetical Examples

AI illustrates its points with abstract examples: "Imagine a company X",
"Take the case of a typical SME." A human cites hyper-specific details, niche facts,
sometimes trivial ones, that betray a real observation.

**Before:**
> For example, a company wishing to improve its inventory management might implement
> an automated inventory tracking system.

**After:**
> At the firm, the client who struggled most with the switch to e-invoicing was
> a plumber in south London who invoiced everything using carbonless receipt books.
> We had to install an app on his phone and train him in two 45-minute sessions
> on a Saturday morning.

**Rule**: specific details (south London, carbonless receipt books, Saturday morning)
are impossible for an LLM to predict. They increase the text's perplexity
and signal lived experience. Even when users do not have these details, ask them:
"Do you have a concrete example from your experience? A case, a name, an anecdote?"

**Three levels of specificity:**

| Level | Example | Perplexity |
|---|---|---|
| Generic (AI) | "A company improved its processes" | Very low |
| Medium | "An accounting firm with 8 staff reduced its turnaround times" | Medium |
| Specific (human) | "The Leroy firm in Ivry reduced financial statement production time from 6 to 4 weeks by switching to Xero, except for property management companies that stayed on QuickBooks" | High |

### Pattern 33: Uniformly Formal Language Register

AI maintains a perfectly constant formal register. A human mixes. In the same
paragraph, you can find highly technical vocabulary alongside a more everyday expression.
This variation is natural and detectors measure it.


**Rule**: within a single paragraph, allow one or two words from a more casual
register ("that is the crux of it," "it is a mess," "so") amid precise technical vocabulary.
The contrast is a strong human signal.

**Caution:** this rule does not apply to dissertations and research theses,
where a formal register is the norm. It applies to professional theses,
internship reports, and any document where "I" is permitted.

### Pattern 34: Neutrality and Benevolence Bias (Gemini 3.1 Pro signal)

RLHF training forces AI to present "both sides" without ever committing. A text that stays perfectly balanced on any contested point is 90% likely AI (Gemini's own estimate).

**Rule**: a real author has a direction. Assert. Take a side. Nuance it in the next sentence, but never sit equidistant.

### Pattern 35: Hourglass Structure (RLHF signature)

AI follows a rigid schema: intro announces the plan → symmetrical body → summary conclusion. Each section is ±20% the same length; transitions are mechanical.

**Rule**: start mid-idea; unbalance sections (fieldwork longer than theory is normal); skip the recap; remove plan announcements if headings make them redundant.

### Pattern 36: Universal-Audience Filler

AI writes for a reader who knows nothing, redefining obvious terms and contextualizing the self-evident.

**Rule**: never explain terms your target reader necessarily knows. Test every intro sentence: "Does my reader need this?" If not, delete it.

### Pattern 37: Absence of Inline Micro-Revisions (ChatGPT 5.4 signal)

AI writes in one fluent draft with no self-corrections. Humans revise in real time: "well," "actually," "let's say," "no wait."

**Rule**: insert 1-2 authentic micro-revisions per page in thesis/report formats. Vary the forms — do not repeat "well" every 5 sentences.

### Pattern 38: Paraphrastic Redundancy (ChatGPT 5.4 signal)

AI restates the same idea in two adjacent formulations as a safety mechanism. Intra-paragraph semantic similarity between consecutive sentences is statistically too high.

**Rule**: if two adjacent sentences say the same thing in different words, keep the more precise, delete the other.

### Pattern 39: Correction/Individuality Ratio Too High (ChatGPT 5.4 signal)

AI text is correct but featureless. Humans have an idiolect: punctuation habits, recurring expressions, preferred collocations.

**Rule**: choose 2-3 punctuation tics; inject 3-4 recurring expressions consistently throughout the text.

### Pattern 40: Absence of Cognitive Cost Traces (ChatGPT 5.4 signal)

AI delivers a finished product. Humans leave visible traces of the work: explicit trade-offs, acknowledged limitations, imperfect choices made under constraint.

**Rule**: at least 1 cognitive cost trace per page in professional theses and reports: "We had two options. We chose X because of Y, even though Z would have been cleaner."

### Pattern 41: Invisible Isotopic Persistence (Gemini 3.1 Pro Thinking signal)

Gemini Thinking builds a complete resolution tree before writing: its metaphors stay mathematically consistent across the whole text. A human forgets their own metaphors and naturally mixes fields.

**Rule**: if the same metaphorical field persists for more than 2 paragraphs, break the isotopy by shifting to the concrete or a different register.

### Pattern 42: Pre-emptive Integrated Concession (Gemini Thinking signal)

Thinking mode maps the logical space before writing: counter-arguments appear as embedded subordinate clauses within the same sentence as the thesis, creating artificial syntactic density.

**Rule**: do not integrate thesis and antithesis in the same sentence. Assert in one sentence. Qualify in the next.

### Pattern 43: Flattening of Tonal Variance (Gemini Thinking signal)

Thinking acts as an extreme smoothing filter: constant intensity from start to finish. A human warms up for key points and cools down for technical passages.

**Rule**: build an intensity curve. Neutral opening, committed middle, restrained close. Not a flat line.

### Pattern 44: Systematic Meta-Analytical Pivot (Gemini Thinking signal)

AI with extended reasoning slides from field description to theoretical framework every paragraph. A human recounts what happened; they do not pivot to meta-analysis every two sentences.

**Rule**: stay in the concrete. Reserve theoretical framing for its dedicated section.

### Pattern 45: Excessive Self-Reference (Gemini detector prompt signal)

AI narrates what it is doing: "In this section we will examine," "as mentioned above," "we should now address." A well-structured text does not need to comment on itself.

**Rule**: remove every sentence that describes the text instead of doing what the text should do. Exception: one concise plan announcement in a thesis general introduction.

### Pattern 46: Smooth Adjectival Density (Gemini detector prompt signal)

AI pairs generic adjectives for an impression of precision: "important and significant," "diverse and complex," "relevant and innovative."

**Rule**: never two generic adjectives side by side. If one is not enough, replace the pair with a fact.

### Pattern 47: False Cognates and Anglicized Syntax

Stilted phrasing from LLM training data: "deliver a result," "leverage synergies," "going forward," "circle back," "bandwidth" (figurative), "ideate," "touch base."

**Rule**: ask "would a real professional say this?" — if not, replace. Full phrasing table in `references/ai-markers.md`.

### Pattern 48: Persistence of Macro-Structure Despite Humanization (Anti-bypass)

Sentence-level humanization tools (Quillbot, humanisers) can vary vocabulary and burstiness but leave the AI skeleton: strict linear plan, symmetrical sections, recap conclusion.

**Rule**: humanize the macro-structure too: unbalance sections, insert at least 1 digression per chapter, do not recap.
---

## Phase 7 - Injecting Soul

After removing AI patterns, the text risks being clean but lifeless. A ghost text: grammatically correct, factually accurate, and perfectly boring. Five techniques:

**1. Vary the rhythm.** Alternate very short sentences (3-6 words) with long, complex ones (30+ words). AI produces uniform 15-20 word sentences. Aim for standard deviation > 8 words.

**2. Have an opinion.** A professional thesis author lived the placement and has a viewpoint. Xero does reconciliation well, but its review module is frustrating. Say so. Pattern 34 applies here.

**3. Acknowledge complexity.** Real humans hesitate: "It is impressive, but also a little worrying." "Honestly, I am not sure this is the right approach." "The results are encouraging — but it remains to be seen..."

**4. Use "I" when the format allows.** In a professional thesis, an internship report, a cover letter: "I" is expected. The absence of "I" in these formats is an AI signal. Not in dissertations or research theses.

**5. Leave roughness.** Parentheticals that open asides. Rhetorical questions. Micro-revisions (Pattern 37). Generic emotional adjectives (concerning, promising) must be replaced with precise ones: "There is something unsettling about the fact that half the firms still have no automated backup process. This is not a technology problem — it is a habit problem."

---

## Phase 8 - Statistical Anti-Detection Countermeasures

> Full formulas, thresholds, and three-tier pipeline (Tier 1 surface / Tier 2 PPL+GLTR /
> Tier 3 DetectGPT) in `references/self-evaluation-formulas.md` (Formulas 1–38).
> Compilatio-specific architecture (v4.5.3) in `references/compilatio-detection.md`.

The four signals all detectors measure:

| Signal | AI profile | Human profile |
|---|---|---|
| Perplexity (PPL) | Low < 35 (predictable tokens) | High > 65 (unexpected word choices) |
| Burstiness (B) | Low < -0.5 (uniform sentence length) | High > 0.3 (short + long alternating) |
| TTR variance | Low (lexically monotone) | Variable (technical zones + simple zones) |
| GLTR rank | F(B₁₀) > 85% | F(B₁₀₀₀) ≈ 10% (long tail present) |

**The irreducible counter-measure:** a text grounded in lived experience generates
naturally high PPL and healthy GLTR long-tail ratios. No prompt engineering fully
replicates authentic content — which is why Step 0.5 anchoring is mandatory.

## Complete Process - Output Format

Each rewriting follows these 8 steps, in this order. Never skip a step.

### Step 0.5: Anchoring Collection (MANDATORY before any rewriting)

**This is the most important step of the skill.** Without it, no humanization
technique will suffice. A text with DARL = 0 will always be detected as AI.

The questionnaire is organized in 3 levels. Each usable answer is a
"semantic anchor" that destroys detector perplexity scores.

**Anchor scoring:** Level 1 (generic: "UK") = weight 1 / Level 2 (domain: "Xero 19.2") = weight 2 / Level 3 (hyper-local: "Ms. Johnson, Nov 14th") = weight 3. Target: DARL > 4.5 per paragraph.


#### EXPRESS VERSION (5 questions, when the student is in a hurry)

```
EXPRESS ANCHORING (5 questions)
═════════════════════════════

1. TOOL: Exact name of a software, place, or author with a technical detail
   (version, year, room number)?

2. PERSON: Name of a person or department + an exact date (e.g.: Tuesday the 14th)?

3. NUMBER: A statistic or exact figure (with decimal)?

4. OBSTACLE (the most important): An unexpected problem or failure that cost you
   time? In one sentence.

5. TIC: 2 connecting words you use all the time?
```

**Question yield:**
- Q4 (OBSTACLE) is the highest-yield question: one good answer
  protects 3-4 paragraphs (justifies a methodological pivot, injects doubt and
  frustration = DACP + CDE + VVE)
- Q2 (PERSON) + Q3 (NUMBER) together saturate the DARL per paragraph
- Q7 (FAVOURITE WORDS) calibrates the idiolect across the whole text

**Rules:**
- NEVER rewrite without at least Q1 + Q2 + Q4 (tool, person, obstacle).
- If the user refuses: "Without these details, the text will be detected. Detectors
  measure grounding in reality, not just style."
- NEVER invent details in place of the user.
- Inject answers as **unalterable semantic anchors**. Do not smooth over failure
  anecdotes, preserve their factual roughness.
- Distribute the anchors across the whole text (not concentrated in 2-3 sentences).

### Step 1: Diagnostic

Display the full diagnostic (cf. Step 0). Include the estimated DARL and DS.
Wait for user validation before rewriting, unless they have
explicitly asked for a direct rewrite.

**New in the diagnostic:**
```
  - Estimated DARL: [value] → [OK > 4.5 / At risk < 1.5]
  - Semantic density: [value] → [OK > 0.5 / At risk < 0.3]
  - Estimated RDS: [value] → [OK > 0.35 / At risk < 0.15]
```

If DARL < 1.5 or DS < 0.3, **block the rewriting** and return to Step 0.5
to request more concrete details.

### Step 2: Identify the Source Model

Before rewriting, identify which LLM probably generated the text.
Corrections differ depending on the origin.

**Signatures by model:**

| Signal | Probably Gemini | Probably ChatGPT/GPT | Probably Claude |
|---|---|---|---|
| Rhythm | Very regular sentences (σ < 2) | Moderately regular sentences | Sentences with em dashes |
| Lexicon | Poetic/literary, "crystallize," "in the background" | Triads, "it is essential," "however" | "constitutes a," "fits within," dashes |
| Structure | Smooth description, no argumentative structure | RLHF hourglass (for/against/therefore) | Bulleted lists with bold |
| Tone | Contemplative, neutral-positive | Neutral-balanced, benevolent | Polite, structured, exhaustive |


### Step 3: Draft Rewriting

First rewriting pass. Apply all 48 surface patterns (Phases 1-6).
Inject soul (Phase 7). Apply statistical countermeasures (Phase 8).
Adapt to document type (cf. table below).

**Distribution rule:** concrete details provided in Step 0.5 must
be distributed across the entire text (not concentrated in 2-3 sentences).
Aim for DARL > 3 per paragraph and at least 1 concrete fact per sentence.

### Step 4: Self-Audit (Double Grid)

Ask yourself: "If I were Compilatio with GPT-5.4, Claude Opus 4.6,
Claude Sonnet 4.6, and Gemini 3.1 Pro, what would make me flag this text?"

**Grid 1 - Surface Patterns:**
- AI tells that may remain (vocabulary, connectors, triads)
- Passages still too smooth
- Transitions still mechanical
- Places where "I" or an opinion is missing (if format allows)

**Grid 2 - Statistical:** sufficient burstiness? Specific names/numbers/dates? Rich vocabulary? Varied sentence starts? Entropy variation?

### Step 5: Mathematical Self-Evaluation (34 formulas)

Calculate metrics on the rewritten text (cf. `references/self-evaluation-formulas.md`):

```
REWRITTEN TEXT METRICS
═══════════════════════════
Burstiness (B): [value] → [human > 0.3 / suspect -0.5 to 0 / AI < -0.5]
TTR variance:   [value] → [human > 0.06 / AI < 0.04]
Connectors Z1:  [%] → [human < 60% / AI > 80%]
Semantic density: [value] → [human > 0.5 / AI < 0.3]
Structural regularity: [value] → [human < 0.70 / AI > 0.85]
AI markers/500 words: [n] → [OK < 4 / strong signal > 4]

SCE_approx: [value] → [HUMAN < 0.25 / LIKELY_HUMAN 0.25-0.40 / NEEDS WORK > 0.40]
```

**If SCE_approx > 0.40:** fix the weakest metrics, loop. **If < 0.25:** human zone, proceed.

### Step 6: Final Rewriting

Second pass correcting the issues identified in steps 4 and 5. This is the
version delivered to the user.

**Mandatory exit checks:**
- DARL > 4.5 per paragraph?
- DS > 0.5?
- RDS > 0.35 (the one-third rule)?
- SCE < 0.35?
If any of these conditions is not met, do not deliver and loop.

### Step 7: Summary of Changes

Concise list of what changed:

```
CHANGES MADE
════════════════════════
- [n] mechanical connectors removed or replaced
- [n] em dashes removed
- [n] empty superlatives replaced with concrete terms
- [n] triads broken up
- [n] filler sentences removed
- [description of major structural changes]
- [description of voice/soul additions]
- Sentence length variance: [before] → [after]
- Diagnostic score: [before] → [after]
```

---

## Adaptation by Document Type

Rewriting is not done the same way in every context. Calibration depends
on the document type.

| Document type | Target register | "I" permitted | Informality margin | Concrete examples |
|---|---|---|---|---|
| Research thesis | Formal, impersonal | No ("we" of modesty) | None | Master's, doctoral thesis |
| Professional thesis | Formal but accessible | Yes, measured | Light, via examples | Professional qualifications |
| Internship report | Current-formal | Yes | Moderate | Undergraduate programs |
| Dissertation | Formal | No | None | Exams, competitions |
| Cover letter | Professional | Yes | Moderate | Job/internship applications |
| Professional email | Current | Yes | Wide | Internal communication |
| Summary note | Formal, factual | No | None | Administrative competitions |
| Reading notes | Formal | Yes (measured) | Light | University exercise |


---

## Complete Example — BEFORE/AFTER

**BEFORE (score 16 — deep rewrite):**

> In a world of constant change, digital transformation has become a major
> challenge for companies. Furthermore, this profound shift - affecting all
> sectors - fits within a global dynamic of modernization. Moreover, it should be noted that
> accounting firms are no exception to this trend. Additionally, the automation of accounting
> processes allows for significantly improving productivity, thereby enabling better allocation
> of human resources. One cannot help but notice that this evolution constitutes a crucial
> lever of competitiveness for small firms. The future looks promising for
> firms that know how to adapt.

---

## Special Cases

### Text Already Short (< 100 words)

Do not lengthen. Humanizing means making natural, not adding text. Sometimes
the humanized version is shorter than the original.

### Technical Text (code, formulas, procedures)

Do not humanize the technical content. Humanize only the explanatory
passages and transitions.


### The User Requests a "Level" of Humanization

If the user requests a "light" or "subtle" humanization:
- Apply Phases 1 to 5 (pattern removal)
- Reduce Phase 7 (soul injection) to a minimum
- Do not change the structure

If the user requests a "total" or "deep" humanization:
- Apply all phases
- Phase 7 at maximum
- Structural reorganization permitted

---

## Essential Reminders

1. **Always start with the diagnostic.** No blind rewriting.

2. **Never mention the humanization process.** The final text must contain no trace of this rewriting.

3. **Concrete beats abstract.** A number, a name, a date: that is what makes a text vivid.

4. **Perfection is suspicious.** Too balanced, too well structured is an AI signal. Real texts have minor imperfections.

5. **Self-audit is mandatory.** Never deliver without running the double grid (Step 4).

6. **LLM detectors are smarter than word lists.** Compilatio uses Claude Opus 4.6, GPT-5.4, Gemini 3.1 Pro. They detect perplexity, burstiness, lexical richness. Phase 8 matters as much as Phases 1-7.

7. **Respect the register.** No informality in dissertations. No stiff tone in internship reports.

8. **Preserve meaning.** Humanization changes form, not content. Flag errors instead of rewriting them neatly.

9. **Never invent facts.** If the text is vague, reformulate as an opinion or ask the user for concrete details (names, numbers, dates).

---

## Internal References

| File | When to consult |
|---|---|
| `references/patterns-by-discipline.md` | AI patterns specific to a discipline (accounting, law, social sciences, computing, health, literature) |
| `references/ai-markers.md` | Comprehensive blacklist of 60+ AI markers in English (words, structures, statistical signals) |
| `references/detection-prompts.md` | Reconstructed detection prompts: formulas, thresholds, weightings, calibrated examples |
| `references/self-evaluation-formulas.md` | Mathematical formulas for self-evaluating a text before delivery + self-evaluation prompt |
| `references/compilatio-detection.md` | In-depth report on Compilatio Studium / Magister / Magister+: detection architecture, published metrics, false positive rates, documented bypass vectors, version history 2024–2026 |
