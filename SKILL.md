---
name: book-companion
description: Generates scholarly front matter for a named book — orientation for first-time readers, modeled on the contextual matter in high-quality hardcover editions of classic literature. Use whenever the user asks for a "book companion," "book-companion treatment," "front matter for [book]," a "reader's guide for [book]," "pre-reading context," wants to be "introduced to [book] before reading it," or asks for biographical, historical, publishing, or illustrator context for a specific book they have not yet started. Output: why the book has lasted, a chronology of the author's life beside world events, a select bibliography with translation notes for non-English originals, a note on original illustrations where applicable, and an essay on how the book was read at first publication versus today. Strictly no spoilers. Do NOT use for book reviews, plot summaries, character analysis, post-reading book-club agendas (use podcast-book-club), or any book the user has already finished.
---

# Book Companion

## What this skill produces

Scholarly front matter for a single named book, written for a reader who has not yet started it. The model is the contextual material found in high-quality hardcover editions of classics — the stuff you read before chapter one, designed to load you up with context the original audience had for free.

Worked examples are in the `examples/` directory. Read at least one before writing your own. They set the bar for tone, depth, and the texture of the prose — match them.

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

### Document title (H1)

The document opens with a single `#` heading: the book title in italics, followed by `by [Author Name]`, followed by `— originally in [Language]`. Nothing else. No "Front Matter for...", no "A Reader's Companion to...", no jargon. The reader does not need to be told what they're looking at; they need to be oriented to the book.

```
# *Around the World in Eighty Days* by Jules Verne — originally in French
```

```
# *The Alchemist* by Paulo Coelho — originally in Portuguese
```

### 1. Why This Book Is Worth Reading (or might not be)

Two to four paragraphs structured as follows:

**The case for the book.** One or two paragraphs. Specific, substantive, evidence-based. Explain what about this particular book has actually kept it alive — the texture of the prose, a specific historical moment it captured, a character who continues to puzzle, a structural innovation. Avoid generic praise ("a timeless masterpiece"), avoid hagiography, avoid spoilers. The reader should finish this section understanding why the book is worth their hours, not what happens in it.

**The case against.** One paragraph beginning "It might not be for you if:" followed by honest reasons a reader might put the book down — lack of interiority, dated ideology, functional-rather-than-literary prose, a premise that requires patience, a genre mismatch. Calibrate against comparable books so the reader has a concrete frame. Do not moralize; describe. Not every book needs a long case against — if the honest answer is "most readers will enjoy this," say so briefly and move on.

**Cultural impact** (subsection `###`). Skip this subsection if the book left no notable trace outside itself. Include it when the book demonstrably changed something: coined a word or phrase now in common use, inspired a direct real-world response (a journey undertaken, a law passed, a scientific program launched), produced a widely-seen adaptation that shaped how the story is now remembered, or established a narrative form that spawned a recognizable genre. Be specific — name the film, the journalist, the phrase — and explain the mechanism of influence, not just the fact of it. Two to three paragraphs maximum.

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

### 3. Writing the Book

**Skip this section entirely if the circumstances of composition do not show strong, specific influence on the book's content, tone, or context.** Most books don't need it — a comfortable author writing in normal conditions adds nothing here. Include it only when the where, when, and what of writing visibly shaped what ended up on the page: a specific location whose atmosphere runs through the prose, a period of personal crisis whose pressure is audible in the sentences, a race against illness or deadline that explains the book's intensity or incompleteness.

When the section applies, cover in two to four paragraphs:

- **Where and when.** The physical location and period of composition — specific enough to be visualized, not just "he wrote it in Paris in the 1870s."
- **What the author's life looked like.** What else was happening: health, relationships, finances, other work, political circumstances bearing directly on the author at that moment. Only what's relevant to the book — not a reprise of the full chronology.
- **The connection to the book.** Make the link explicit. Don't leave the reader to infer it; say what the conditions produced: the bleakness, the speed, the optimism, the gaps, the obsessive detail. This is the sentence the section exists to deliver.

Do not use this section to repeat material already covered in the chronology or "Then and Now." If the political context of composition belongs in "Then and Now," put it there. This section is specifically about the author's personal circumstances during the act of writing.

### 4. Select Bibliography

Two subsections:

#### Major Works by the Author

Bulleted list. English title first, original-language title in parentheses if different, with date. For prolific authors (Verne, Dickens, Tolstoy), select rather than list everything — pick the works that matter to the author's reputation and to placing the book in question within their output.

#### Recommended English Translations

Only if the book is in translation. Bulleted list with brief notes on which to prefer and why. **Flag the "standard-but-dated translation" problem when it applies** — many nineteenth-century works circulate in English in Victorian translations that are abridged, censored, or simply wrong, and modern scholarly translations exist but aren't always the default in cheap paperbacks. Verne is the canonical case; so are Dostoyevsky, Proust, and Kafka. Don't recommend a translation just because it's famous; recommend the best.

Skip this subsection entirely if the book was written in English.

### 5. A Note on the Illustrations

Two or three sentences naming the original illustrator(s) and the edition that first contained them. Then embed a small selection (two to four) of the original illustrations inline using markdown image syntax, sourcing direct image file URLs from public-domain archives. Preferred archives, in rough order of preference: Wikimedia Commons (use the direct `https://upload.wikimedia.org/...` file URL, not the page URL), Project Gutenberg, Bibliothèque nationale de France's Gallica, the Internet Archive, the British Library's digital collections.

```
![Brief descriptive caption](https://upload.wikimedia.org/wikipedia/commons/...)
```

Include a caption (the `alt` text) for each image that identifies the scene or subject. Do not describe the images in prose — let them speak for themselves. After the inline images, add a single line linking to the full archive for readers who want to browse the complete set.

**Skip this section entirely if the book had no notable original illustrations.** Most modern novels don't. Don't pad with cover art or later illustrated editions — this section is specifically about illustrations that were part of the book's original presentation.

### 6. Then and Now: How This Book Was Read in [Original Publication Year]

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

- "Cultural Impact" subsection → skip if the book left no notable trace outside itself (no widely-used phrase coined, no significant adaptation, no direct real-world response, no genre it founded)
- "Writing the Book" → skip if the circumstances of composition do not show strong, specific influence on the book's content, tone, or context
- "A Note on the Illustrations" → skip if the book had no notable original illustrations
- "Recommended English Translations" subsection → skip if the book was originally written in English
- Within "Then and Now" → skip any of the four sub-topics that don't apply

Never replace a skipped section with filler. A shorter, accurate companion is better than a padded one.

## Reference Examples

Two complete worked examples are in the `examples/` directory. Read at least one before drafting — they set the calibration for length, density, prose style, and table formatting. Read both if the book in question is unusual (translated, contested, late-discovered, etc.).

- **`examples/verne-jules-around-the-world-in-eighty-days.md`** — the canonical case. An English-language reader's classic (originally French), with notable original illustrations, a sharply defined original publication moment, a clear example of pushing back on a misleading posthumous label ("father of science fiction"), a strong Cultural Impact subsection (Nellie Bly, the 1956 film, the title entering the language), and a Writing the Book section that connects post-Commune France to the novel's conspicuous optimism. Use this to calibrate the standard structure with all sections present.

- **`examples/coelho-paulo-the-alchemist.md`** — the harder cases. Demonstrates: (1) skipping the illustrations section entirely, (2) handling a book whose meaningful reception window is not its original publication year (the 1988 first edition flopped; the relevant "then" is 1988–1995), (3) writing about a contested or critically-dismissed book without either fawning or sneering, (4) handling a living author whose chronology runs to the present, and (5) a Writing the Book section for a novel composed in a concentrated two-week burst — model for when speed and emotional state of composition are the relevant facts. The translation subsection is also unusually short here because there is essentially one English translation — model for not padding.

Example filenames follow the convention `lastname-firstname-title-slug.md`. Future examples added to this directory should match.
