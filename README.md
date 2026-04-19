# Obsidian CV

A CSS snippet that turns any Obsidian note into a clean, ATS-friendly resume - no plugins required.

Switch to Reading View to preview or export to PDF.

<img src="CV%20example.jpg" width="500">

## Install
### Option 1 - Quick
1. Download Zip from release
2. Unzip and paste its content into your vault
3. Toggle the snippet on in **Settings → Appearance → CSS snippets**
### Option 2 - Manual
1. Download [CV.css](.obsidian/snippets/CV.css) and [CV.md](CV.md)
2. Drop `CV.md` anywhere in your vault
3. Move `CV.css` into your vault's `.obsidian/snippets/` folder
4. In Obsidian: **Settings → Appearance → CSS snippets** → toggle `CV` on
## Usage
Open `CV.md` and replace the mock data with your own. The template uses standard Markdown — no special syntax beyond what's described below.
### Frontmatter
The snippet only activates on notes with this cssclass:
```yaml
---
cssclasses:
  - reading-mode
---
```
### Spacers
Use `<span class="spacer"></span>` inside headings to push content to the right edge. This is how job titles and dates sit on opposite sides:
```markdown
### Job Title | Company <span class="spacer"></span> Remote | 2024 - Present
```
### Contact links with icons

Use `<img>` tags with the `contact-icon` class to add favicons next to links. This works with any domain:

```markdown
<img src="https://www.google.com/s2/favicons?sz=32&domain=gmail.com" height="16" class="contact-icon"> [Email](mailto:you@example.com) <img src="https://www.google.com/s2/favicons?sz=32&domain=linkedin.com" height="16" class="contact-icon"> [LinkedIn](https://linkedin.com/in/you)
```

The favicon URL format is: `https://www.google.com/s2/favicons?sz=32&domain=DOMAIN.com`
### Structure
| Markdown                    | Renders as                              |
| --------------------------- | --------------------------------------- |
| `# Name`                    | Large centered name                     |
| `> Subtitle`                | Centered subtitle (blockquote)          |
| Contact line with `<img>`    | Inline links with favicons              |
| `## Section`                | Uppercase section header with underline |
| `### Title`                 | Job/education entry title               |
| `h3` or `h4` with `.spacer` | Left-right layout (title \| details)    |
| `#### Subtitle`             | Muted sub-heading                       |
| Bullet lists (`•`)          | Achievement/-detail bullets             |
### Bullet points
Use `•` (Unicode bullet) instead of `-` for lists. PDF-to-MD converters often reorder standard Markdown lists, pushing them all to the bottom and breaking the CV layout. `•` avoids this because it's treated as plain text, not a list item.

```markdown
• Achievement description here
• Another achievement
```
### Export to PDF
Options -> Export to PDF to export. The CSS includes print styles - margins, page breaks, and colors are handled automatically.
## Customization
All visual tweaks are CSS variables at the top of [CV.css](.obsidian/snippets/CV.css):
```css
--cv-accent: #2e5c94;
--cv-text: #222;
--cv-bg: #fff;
--cv-border: #dae3ea;
--cv-font: 'Segoe UI', 'Roboto', sans-serif;
```
Change accent color, fonts, or text color to match your style.
## How it works
The snippet is scoped to `.markdown-preview-view.reading-mode` - it only affects the reading view of notes with the `reading-mode` cssclass. Your editing experience, other notes, and the rest of your vault are untouched.
## License
MIT
