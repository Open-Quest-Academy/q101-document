# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the documentation repository for Q101 token airdrop claim process. It uses Docsify to create a lightweight documentation website from Markdown files, hosted on GitHub Pages.

**Purpose**: Provide comprehensive guides for users to claim their Q101 token airdrops.

## Repository Structure

```
q101-document/
├── index.html              # Docsify configuration file
├── .nojekyll              # Disable Jekyll processing on GitHub Pages
├── docs/
│   ├── _sidebar.md        # Sidebar navigation (minimal)
│   └── manual/
│       └── CLAIM_GUIDE.md # Main airdrop claim guide (~14MB with images)
├── README.md              # Repository introduction
├── README_DOCSIFY.md      # Docsify setup instructions
└── USAGE.md               # Quick usage guide
```

## Technology Stack

- **Docsify**: Lightweight documentation site generator
  - No build process required
  - Real-time Markdown rendering in browser
  - Auto-generates table of contents from document headings
  - Built-in search, code highlighting, and copy functionality

- **GitHub Pages**: Static site hosting
  - Deployed from master branch
  - URL: https://open-quest-academy.github.io/q101-document/

## Key Files

### index.html
Main Docsify configuration file with:
- `loadSidebar: false` - Uses auto-generated TOC instead of custom sidebar
- `subMaxLevel: 4` and `maxLevel: 4` - Shows h1-h4 headings in sidebar
- Custom CSS for sidebar title alignment
- Search, copy-code, and zoom-image plugins enabled

### docs/manual/CLAIM_GUIDE.md
The primary documentation file (~14MB):
- Contains step-by-step airdrop claiming instructions
- Includes base64-encoded images (very large file)
- Uses standard Markdown heading syntax (# ## ###)
- Auto-generates table of contents in sidebar

### docs/_sidebar.md
Minimal sidebar file with single link to CLAIM_GUIDE.md

## Local Development

Test the documentation site locally:

```bash
# Using Python (recommended)
python -m http.server 3000

# Using Docsify CLI
npm i docsify-cli -g
docsify serve .
```

Visit: http://localhost:3000

## Git Workflow

- **Main branch**: `master` (production documentation)
- **Deployment**: Automatic via GitHub Pages
- **Testing**: Always test locally before pushing

## Documentation Guidelines

When updating documentation:

1. **CLAIM_GUIDE.md Format**:
   - Use standard Markdown headings: `#` for h1, `##` for h2, etc.
   - Keep base64 image data intact (don't accidentally corrupt)
   - Test that auto-generated TOC works correctly

2. **Docsify Configuration**:
   - Don't change `loadSidebar: false` (needed for auto-TOC)
   - Keep `subMaxLevel` and `maxLevel` at 4 for good TOC depth
   - Maintain custom CSS for sidebar alignment

3. **File Size Awareness**:
   - CLAIM_GUIDE.md is ~14MB due to embedded images
   - Read tool may fail on this file (use offset/limit or Grep)
   - Consider this when making edits

4. **Testing**:
   - Always test locally before committing
   - Verify sidebar TOC displays correctly
   - Check that all links work
   - Ensure search functionality works

## Common Tasks

### Adding New Documentation

1. Create new .md file in `docs/manual/`
2. Update `docs/_sidebar.md` to include link
3. Test locally
4. Commit and push

### Updating Styles

Edit the `<style>` section in `index.html`:
```css
:root {
  --theme-color: #0EA5E9;        /* Primary color */
  --theme-color-dark: #0284C7;   /* Darker shade */
}
```

### Debugging TOC Issues

If table of contents doesn't appear:
1. Check that `loadSidebar: false` in index.html
2. Verify Markdown uses proper heading syntax (#, ##, ###)
3. Check browser console for Docsify errors
4. Clear browser cache and reload

## Key Terminology

- **Q101 Token**: Utility and governance token for Open Quest Academy
- **Airdrop**: Token distribution to eligible participants
- **Claim Process**: Multi-step process to receive airdrop tokens
- **Vesting Schedule**: Three-phase token release (waiting period, initial release, monthly rewards)
- **MetaMask**: Recommended Web3 wallet for claiming tokens

## Content Focus

The documentation focuses on:

1. **Claim Instructions**: Step-by-step guide with screenshots
2. **Prerequisites**: Wallet setup and security warnings
3. **Release Schedule**: Three-phase airdrop distribution timeline
4. **Troubleshooting**: Common issues and solutions

## Important Notes

- **Large File Warning**: CLAIM_GUIDE.md is ~14MB - handle carefully
- **Image Data**: Contains base64-encoded images - don't corrupt
- **Auto-TOC**: Relies on proper Markdown heading structure
- **GitHub Pages**: Changes go live automatically after push
- **No Build**: Docsify renders client-side, no build step needed

## Related Resources

- Official Website: https://q101.org
- Airdrop Portal: https://claim.q101.com
- Main Q101 Repository: (separate repository with smart contracts and apps)

---

When making updates, prioritize:
1. User clarity and step-by-step guidance
2. Visual aids (screenshots) for complex steps
3. Security warnings where appropriate
4. Consistent formatting and structure
