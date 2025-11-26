# GitBook Setup Guide

This guide explains how to use this documentation with GitBook.

## What is GitBook?

GitBook is a modern documentation platform that turns your markdown files into beautiful, searchable documentation websites.

## Documentation Structure

The documentation is organized with:
- **SUMMARY.md** - Table of contents (navigation structure)
- **README.md** - Homepage/introduction
- **.gitbook.yaml** - GitBook configuration
- **Folders** - Organized by topic

## Using with GitBook

### Option 1: GitBook Cloud (Recommended)

1. **Sign up for GitBook**
   - Go to https://www.gitbook.com
   - Create a free account

2. **Import from Git**
   - Click "New Space"
   - Select "Import from Git"
   - Connect your GitHub repository
   - Select the `docs` folder as root

3. **Configure**
   - GitBook will automatically detect `.gitbook.yaml`
   - It will use `SUMMARY.md` for navigation
   - Documentation will be live immediately

4. **Auto-sync**
   - Every push to your repository will update the docs
   - Changes are published automatically

### Option 2: GitBook CLI (Local)

1. **Install GitBook CLI**
   ```bash
   npm install -g gitbook-cli
   ```

2. **Navigate to docs folder**
   ```bash
   cd g:/Code/rc/docs
   ```

3. **Install GitBook**
   ```bash
   gitbook install
   ```

4. **Serve locally**
   ```bash
   gitbook serve
   ```
   
   Visit: http://localhost:4000

5. **Build static site**
   ```bash
   gitbook build
   ```
   
   Output in `_book` folder

### Option 3: Other Documentation Tools

This structure also works with:

**VuePress**
```bash
npm install -g vuepress
vuepress dev docs
```

**Docsify**
```bash
npm install -g docsify-cli
docsify serve docs
```

**MkDocs**
- Convert SUMMARY.md to mkdocs.yml
- Use mkdocs-material theme

## File Structure

```
docs/
├── .gitbook.yaml          # GitBook configuration
├── SUMMARY.md             # Table of contents
├── README.md              # Homepage
├── getting-started/       # Getting started guides
├── core-concepts/         # Core concepts
├── features/              # Feature documentation
├── development/           # Developer guides
├── deployment/            # Deployment guides
├── troubleshooting/       # Troubleshooting
├── recipes/               # Examples and recipes
├── reference/             # Reference documentation
├── contributing/          # Contribution guidelines
└── appendix/              # Additional resources
```

## Adding Content

### 1. Edit Existing Files

Simply edit the markdown files and add content:

```markdown
# Page Title

## Section

Content here...

### Subsection

More content...
```

### 2. Add New Pages

1. Create new `.md` file in appropriate folder
2. Add entry to `SUMMARY.md`:
   ```markdown
   * [New Page](folder/new-page.md)
   ```

### 3. Add Images

1. Create `images` folder in docs
2. Add images
3. Reference in markdown:
   ```markdown
   ![Alt text](images/screenshot.png)
   ```

## Markdown Features

### Basic Formatting

```markdown
**Bold text**
*Italic text*
`Code inline`
[Link text](url)
```

### Code Blocks

```markdown
```php
<?php
echo "Hello World";
```
\```

### Tables

```markdown
| Column 1 | Column 2 |
|----------|----------|
| Data 1   | Data 2   |
```

### Alerts/Callouts

```markdown
> ⚠️ **Warning:** Important information
> 
> 📝 **Note:** Additional information
> 
> ✅ **Tip:** Helpful tip
```

## Best Practices

### 1. Keep Files Organized
- One topic per file
- Use descriptive filenames
- Group related files in folders

### 2. Use Clear Headings
- H1 (`#`) for page title (one per page)
- H2 (`##`) for main sections
- H3 (`###`) for subsections

### 3. Add Navigation
- Link to related pages
- Use "Next:" links at bottom
- Keep SUMMARY.md updated

### 4. Include Examples
- Code examples
- Screenshots
- Step-by-step guides

### 5. Keep Content Current
- Update when features change
- Mark deprecated features
- Version documentation

## Publishing

### GitHub Pages

1. Build static site:
   ```bash
   gitbook build
   ```

2. Push `_book` folder to `gh-pages` branch

3. Enable GitHub Pages in repository settings

### Netlify

1. Connect repository to Netlify
2. Build command: `gitbook build`
3. Publish directory: `_book`

### Custom Domain

Configure in `.gitbook.yaml`:
```yaml
root: ./
structure:
  readme: README.md
  summary: SUMMARY.md
```

## Maintenance

### Regular Tasks

- [ ] Review and update content monthly
- [ ] Check for broken links
- [ ] Update screenshots
- [ ] Add new features documentation
- [ ] Review TODO.md for pending content

### Quality Checks

- [ ] All links work
- [ ] Code examples are correct
- [ ] Screenshots are current
- [ ] Navigation is logical
- [ ] Search works properly

## Support

For GitBook-specific help:
- Documentation: https://docs.gitbook.com
- Community: https://github.com/GitbookIO/gitbook
- Support: support@gitbook.com

---

**Ready to start?** Begin by filling in content for the placeholder files listed in `TODO.md`!
