# Brand Snapshot

Get a brand's visual and verbal basics onto two pages in minutes: colors you can use with confidence, the type and its free stand-ins, how the logo and UI behave, how the brand sounds, and links to the official files. It's the quick version of the brand section in the Company Brief skill.

**What you get:** Reads any brand's live website and returns a two-page brand snapshot PDF plus design tokens (JSON and CSS) - the color palette with hex, RGB and contrast checks, typefaces with free stand-ins, the logo described in words with links to official files, UI patterns like corner radius and buttons, voice samples, imagery style, and where the official guidelines live.

Made by Beautiful Engine · [beautifulengine.com](https://www.beautifulengine.com) · [Questions or ideas? Open an issue](https://github.com/BeautifulEngine/brand-snapshot/issues/new)

## Install

### Claude app (web or desktop)

1. Download **[brand-snapshot.zip](brand-snapshot.zip)** from this repo (open the file, then use the download button). Don't unzip it.
2. Turn on **Settings > Capabilities > "Code execution and file creation"**.
3. Go to **Customize > Skills**, click **+**, then **+ Create skill > Upload a skill**, and upload the zip.
4. Start a new chat and ask in plain words. Claude picks the skill up on its own.

> GitHub's green "Code > Download ZIP" button won't work for this; it wraps everything in an extra folder. Use `brand-snapshot.zip`.

### Claude Code

As part of the Beautiful Engine collection (you get updates and the other skills):

```bash
claude plugin marketplace add BeautifulEngine/skills
claude plugin install beautiful-engine@beautiful-engine
```

Then use `/beautiful-engine:brand-snapshot`, or ask in plain words. Or install just this one:

```bash
git clone https://github.com/BeautifulEngine/brand-snapshot.git
mkdir -p ~/.claude/skills && cp -r brand-snapshot/brand-snapshot ~/.claude/skills/
```

Then use `/brand-snapshot`.

## Usage

```
/brand-snapshot <url or brand name> [tokens only]
```

Plain requests work too:

- "Brand snapshot for linear.app."
- "What colors and fonts does Patagonia use?"
- "Pull design tokens from stripe.com for a pitch mockup."
- "Snapshot of Oatly and Liquid Death, side by side." (makes one snapshot each)

"tokens only" skips the PDF and returns `tokens.json` and `tokens.css`.

**Files.** `<skill-dir>` means this skill's folder, the one holding this SKILL.md. Templates are in `assets/`, scripts in `scripts/`, and the shared PDF steps (fonts, colors, render, check) are in `references/rendering.md`.

## When Claude uses it

Someone asks for a brand's colors, fonts, style, brand guidelines summary, design tokens, or a quick brand reference before starting design work.

## How it works

```
brand-snapshot/
├── SKILL.md
├── assets/  base.css, deck.css, snapshot-template.html
├── scripts/  audit.js, contact_sheet.py, fonts.py, palette.py, render.cjs, render.py, tokens.py
├── references/  brand-extraction.md, rendering.md
```

PDFs are built from HTML templates, colored and typeset with the right brand, rendered by headless Chrome, then checked for fonts, text contrast and leftover blanks before delivery. Anything with numbers in it is calculated by a script, not estimated.

## Works well with

- [Company Brief](https://github.com/BeautifulEngine/company-brief)
- [Sponsorship Pitch](https://github.com/BeautifulEngine/sponsorship-pitch)
- [All Beautiful Engine skills](https://github.com/BeautifulEngine/skills)

## Made by Beautiful Engine

Brand Snapshot is made by [Beautiful Engine](https://www.beautifulengine.com), a creative studio in Los Angeles working across brand, experiential and interactive design.

- **Website:** [beautifulengine.com](https://www.beautifulengine.com)
- **Questions, ideas, or something broke?** [Open an issue](https://github.com/BeautifulEngine/brand-snapshot/issues/new) and describe what you asked for and what happened.

This repo is published from [BeautifulEngine/skills](https://github.com/BeautifulEngine/skills); changes are made there and copied here.

## License

MIT. See [LICENSE](LICENSE).

