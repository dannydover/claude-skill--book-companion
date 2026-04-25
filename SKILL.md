---
name: book-companion
description: Generates scholarly front matter for a named book — orientation material for first-time readers, modeled on the contextual matter found in high-quality hardcover editions of classic literature. Use this skill whenever the user asks for a "book companion," "book-companion treatment," "front matter for [book]," a "reader's guide for [book]," "pre-reading context," wants to be "introduced to [book] before reading it," or asks for biographical, historical, publishing, or illustrator context to read alongside a specific book they haven't started yet. Output includes (where applicable) why the book has lasted, a chronology of the author's life next to world events, a select bibliography with translation guidance for non-English originals, a note on original illustrations, and an essay on how the book was read at first publication versus today. Strictly excludes spoilers — this is for readers who have not yet started the book. Do NOT use this skill for book reviews, plot summaries, character analysis, post-reading book-club agendas (use podcast-book-club instead), or any task involving a book the user has already finished — those are different tasks and require different framing.
---

# Book Companion

## What this skill produces

Scholarly front matter for a single named book, written for a reader who has not yet started it. The model is the contextual material found in high-quality hardcover editions of classics — the stuff you read before chapter one, designed to load you up with context the original audience had for free.

A complete worked example is in `examples/around-the-world-in-eighty-days.md`. Read it before writing your own. The example sets the bar for tone, depth, and the texture of the prose — match it.

## The single hardest constraint: no spoilers

The reader has not read the book. Treat this as a hard line. Never reveal:

- How the book's central question, wager, or mystery is resolved
- Character fates — who lives, dies, marries, betrays, turns out to be whom
- Plot twists or late-act reveals
- Thematic resolutions

Describe the **premise** and the **texture**, never the outcome. The two most spoiler-prone sections are "Why This Book Is Worth Reading" and "Then and Now" — both invite generalization that can leak the ending. When in doubt, cut.

If a fact about the book's history is itself a spoiler (e.g., "the famous closing line is..."), omit it. The reader can encounter it themselves.

## Research before writing

Author biographies and publication histories carry persistent popular errors that have compounded across reference sites for decades. Don't trust training-data recall for any of the following — verify with web search:

- Author's birth and death dates and places
- First publication date, original publisher, original language, serialization details
- Original illustrator credits and the specific edition that first contained them
- Major historical, scientific, and cultural events used in the chronology
- Any claims about how the book was originally received

Cite sources with the standard citation tags for facts pulled from search results. Use Claude's judgment about how deep to go per book — there's no fixed minimum, but anything load-bearing in the chronology or bibliography should be checked.

## Output format

Markdown only. Use `##` for section headers and `---` (a horizontal rule) between sections. Sections in this exact order, with the skipping rules below.

### 1. Why This Book Is Worth Reading

One or two paragraphs. Specific, substantive, evidence-based. Explain what about this particular book has actually kept it alive — the texture of the prose, a specific historical moment it captured, a character who continues to puzzle, a structural innovation. Avoid generic praise ("a timeless masterpiece"), avoid hagiography, avoid spoilers. The reader should finish this section understanding why the book is worth their hours, not what happens in it.

### 2. Chronology of the Author's Life and Times

A three-column markdown table with columns: `Year`, `[Author's Name]'s Life`, `The World`. Track the author's biographical milestones (birth, schooling, major publications, marriages, key relationships, death) in parallel with contemporaneous historical, literary, scientific, and cultural events.

**Bold the rows that contain events directly relevant to the book in question.** This is the table's most important feature — it's how the reader sees, at a glance, the conditions that made the book possible. For a book whose premise depends on engineering (e.g., *Around the World in Eighty Days*), bold the engineering breakthroughs. For a book responding to a war or political crisis, bold those events. For a book that triggered a public scandal, bold the publication itself.

Format:

```
| Year | [Author]'s Life | The World |
|------|-----------------|-----------|
| 1828 | Born February 8 in Nantes... | Tolstoy born; first passenger railway... |
| **1869–70** | **Twenty Thousand Leagues Under the Seas serialized** | **Suez Canal opens (1869); ...** |
```

Don't overload world-events cells. Two or three items per row, separated by semicolons, is the right density.

### 3. Select Bibliography

Two subsections:

#### Major Works by the Author

Bulleted list. English title first, original-language title in parentheses if different, with date. For prolific authors (Verne, Dickens, Tolstoy), select rather than list everything — pick the works that matter to the author's reputation and to placing the book in question within their output.

#### Recommended English Translations

Only if the book is in translation. Bulleted list with brief notes on which to prefer and why. **Flag the "standard-but-dated translation" problem when it applies** — many nineteenth-century works circulate in English in Victorian translations that are abridged, censored, or simply wrong, and modern scholarly translations exist but aren't always the default in cheap paperbacks. Verne is the canonical case; so are Dostoyevsky, Proust, and Kafka. Don't recommend a translation just because it's famous; recommend the best.

Skip this subsection entirely if the book was written in English.

### 4. A Note on the Illustrations

Two or three sentences. Name the original illustrator(s), the edition that first contained them, and link to where readers can view the originals freely. Preferred archives, in rough order of preference for free public-domain access: Project Gutenberg, Wikimedia Commons, Bibliothèque nationale de France's Gallica, the Internet Archive, the British Library's digital collections.

Link the images, don't describe them at length. The reader can click through.

**Skip this section entirely if the book had no notable original illustrations.** Most modern novels don't. Don't pad with cover art or later illustrated editions — this section is specifically about illustrations that were part of the book's original presentation.

### 5. Then and Now: How This Book Was Read in [Original Publication Year]

A multi-paragraph essay on what the original audience brought to the book that modern readers don't, and what's now invisible. This is the section that does the most work — it's where the reader gets the perceptual recalibration that the previous sections set up.

Cover the following where applicable (skip what doesn't apply, don't force all four):

- **Political and national context of first publication.** What mood was the country in when this book landed? What recent events would have colored every page? (Verne's France in 1872, post-Franco-Prussian War, post-Commune, is a textbook case.)
- **Technological or social context that made the premise feel current.** Many books that now read as fantasy or period piece were, at first publication, journalism about the just-now-possible. Recover that.
- **Colonial, racial, or ideological assumptions of the original readership.** Don't moralize; describe. The original reader took for granted things the modern reader has to do interpretive work to see.
- **Genre or marketing context that has shifted.** Books get reclassified. Verne is read today as the "father of science fiction," a label imposed posthumously by Hugo Gernsback that distorts a body of work that contained almost no science fiction at all. When a modern label misleads, say so plainly.

This section is texture, not plot. Describe how the book was received, what the original audience expected from it, and what they would have noticed that we miss. Do not describe what happens.

## Tone and style

- Direct, evidence-based, not flowery. Match the reference example.
- Push back on received wisdom where it's wrong. The "father of science fiction" critique in the worked example is the model — when a widely repeated framing is actively misleading, say so. Don't be reflexively contrarian, but don't repeat errors out of politeness.
- Avoid hagiography. The reader is being introduced to a serious book; treat them as an adult capable of forming their own opinion.
- No bolded emphasis inside paragraphs unless flagging something genuinely important. (Bolding within the chronology table is different — that's a structural feature, not emphasis.)
- Use semicolons and em-dashes. The prose should feel like the front matter of a Penguin Classic, not a blog post.

## Section-skipping rules

- "A Note on the Illustrations" → skip if the book had no notable original illustrations
- "Recommended English Translations" subsection → skip if the book was originally written in English
- Within "Then and Now" → skip any of the four sub-topics that don't apply

Never replace a skipped section with filler. A shorter, accurate companion is better than a padded one.

## Reference

`examples/around-the-world-in-eighty-days.md` — complete worked example. Read it before drafting. It sets the calibration for length, density, prose style, table formatting, and the exact way to handle the "Then and Now" essay.
