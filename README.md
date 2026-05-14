# book-companion

A Claude skill that generates scholarly front matter for any book — the kind of orientation material found in high-quality hardcover editions of classic literature.

Perfect for first-time readers who want historical context, author chronology, reading guidance, and original illustrations before diving into a new book.

## What It Does

Generates up to seven sections for any book you name:

1. **Why This Book Is Worth Reading (or might not be)** — the honest case for and against, plus cultural impact if the book left a notable trace
2. **Then and Now** — how the book was read at first publication vs. today; what the original audience had for free that modern readers have to reconstruct
3. **Writing the Book** *(optional)* — where, when, and under what conditions the author wrote it, when those circumstances visibly shaped the work
4. **Chronology of the Author's Life and Times** — parallel columns tracking biography alongside world events
5. **Select Bibliography** — major works and recommended translations for non-English originals
6. **A Note on the Illustrations** *(optional)* — inline original plates and engravings, when they were part of the book's first presentation

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
