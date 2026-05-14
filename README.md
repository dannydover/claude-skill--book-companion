# book-companion

Before you read a book, Book Companion tells you what you need to know so you can get the most out of reading. It will teach you: the practical shape of the book and how to pace it, why the given book is worth reading (or might not be), what modern audiences might miss that would have been obvious to the original audience, the context around the author when they wrote it, and tips on what illustrations to view and which translations to read.

## What It Does

Generates up to seven sections for any book you name:

1. **At a Glance** — length, structure, difficulty, and pacing advice, so you know what you're committing to before you start
2. **Why This Book Is Worth Reading (or might not be)** — the honest case for and against, plus cultural impact if the book left a notable trace
3. **Then and Now** — how the book was read at first publication vs. today; what the original audience had for free that modern readers have to reconstruct
4. **Writing the Book** *(optional)* — where, when, and under what conditions the author wrote it, when those circumstances visibly shaped the work
5. **Chronology of the Author's Life and Times** — parallel columns tracking biography alongside world events
6. **Select Bibliography** — major works and recommended translations for non-English originals
7. **A Note on the Illustrations** *(optional)* — inline original plates and engravings, when they were part of the book's first presentation

No spoilers. Evidence-based. Cites sources.

## Example Output

See [*Around the World in Eighty Days* by Jules Verne](examples/verne-jules-around-the-world-in-eighty-days.md) for a complete worked example.

## Installation

### Claude.ai
Upload the `SKILL.md` file via Settings → Skills

### Claude Code
```bash
# Clone into your skills directory
git clone https://github.com/dannydover/claude-skill--book-companion ~/.claude/skills/book-companion
```

## Usage

Just ask Claude for front matter:
- "Give me the book-companion treatment for *Moby-Dick*"
- "I want to read *Pride and Prejudice* — can you orient me first?"
- "Create front matter for *One Hundred Years of Solitude*"

## License

Apache 2.0
