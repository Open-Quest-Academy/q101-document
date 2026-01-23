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
├── CNAME                  # Custom domain: docs.q101.org
├── public/                # Favicon and manifest files
│   ├── favicon.ico
│   ├── logo.svg
│   └── manifest.json
├── docs/
│   ├── _sidebar.md        # Sidebar navigation (minimal)
│   └── manual/
│       └── CLAIM_GUIDE.md # Main airdrop claim guide (~14MB with images)
├── package.json           # docsify-cli dependency
├── README.md              # Repository introduction
├── README_DOCSIFY.md      # Docsify setup instructions (Chinese)
└── USAGE.md               # Quick usage guide (Chinese)
```

## Technology Stack

- **Docsify**: Lightweight documentation site generator
  - No build process required
  - Real-time Markdown rendering in browser
  - Auto-generates table of contents from document headings
  - Plugins: copy-code, zoom-image, syntax highlighting

- **GitHub Pages**: Static site hosting
  - Deployed from master branch
  - Custom domain: https://docs.q101.org
  - Fallback URL: https://open-quest-academy.github.io/q101-document/

## Key Files

### index.html
Main Docsify configuration file (index.html:64-83):
- `loadSidebar: false` - Uses auto-generated TOC instead of custom sidebar
- `subMaxLevel: 4` and `maxLevel: 4` - Shows h1-h4 headings in sidebar TOC
- `homepage: 'docs/manual/CLAIM_GUIDE.md'` - Direct homepage to main guide
- Custom CSS for sidebar title alignment (index.html:22-59)
- Plugins enabled: copy-code, zoom-image, Prism syntax highlighting
- **Note**: Search plugin is intentionally disabled for auto-TOC compatibility

### docs/manual/CLAIM_GUIDE.md
The primary documentation file (~14MB):
- Contains step-by-step airdrop claiming instructions with embedded screenshots
- Includes base64-encoded images (causes large file size)
- Uses standard Markdown heading syntax (# ## ### ####)
- Auto-generates table of contents in sidebar based on heading structure
- **CRITICAL**: Use `Grep` with `head_limit` or `Read` with `offset`/`limit` when accessing this file - full reads may timeout

### docs/_sidebar.md
Minimal sidebar file with single emoji link to CLAIM_GUIDE.md (currently not used due to `loadSidebar: false`)

## Local Development

Test the documentation site locally:

```bash
# Method 1: Using Python (recommended - most reliable)
python -m http.server 3000

# Method 2: Using Docsify CLI (if installed)
npm install
npx docsify serve . -p 3000

# Method 3: Global Docsify CLI
npm i docsify-cli -g
docsify serve . -p 3000
```

Visit: http://localhost:3000

**Always test locally before pushing** to verify TOC generation and page rendering.

## Git Workflow

- **Main branch**: `master` (production documentation)
- **Deployment**: Automatic via GitHub Pages (pushes go live immediately)
- **Custom domain**: Configured via CNAME file (docs.q101.org)
- **Testing**: Always test locally before pushing to avoid broken production state

## Editing CLAIM_GUIDE.md (Large File Handling)

The main documentation file is ~14MB with base64-encoded images. Special care required:

### Reading the File
```bash
# BAD - Will timeout
Read(file_path="docs/manual/CLAIM_GUIDE.md")

# GOOD - Use Grep with head_limit for searching
Grep(pattern="^#{1,3} ", path="docs/manual/CLAIM_GUIDE.md", output_mode="content", head_limit=50)

# GOOD - Use Read with offset/limit for specific sections
Read(file_path="docs/manual/CLAIM_GUIDE.md", offset=1, limit=100)
```

### Editing Guidelines
1. **Preserve base64 image data**: Don't accidentally corrupt long base64 strings
2. **Use standard Markdown headings**: `#` for h1, `##` for h2, etc. (required for auto-TOC)
3. **Test TOC generation**: Ensure heading structure creates logical sidebar navigation
4. **Watch for encoding issues**: Base64 data can be corrupted by careless edits

## Docsify Configuration Rules

### Critical Settings (Do Not Change)
- `loadSidebar: false` - Required for auto-generated TOC from page headings
- `subMaxLevel: 4` and `maxLevel: 4` - Controls TOC depth (h1-h4 headings)
- `homepage: 'docs/manual/CLAIM_GUIDE.md'` - Direct route to main guide

### Why Search Plugin is Disabled
The search plugin is intentionally commented out in index.html:56-58 because it conflicts with the auto-generated TOC feature. Do not re-enable unless switching to manual sidebar mode.

### Customizing Theme Colors
Edit CSS variables in index.html:23-26:
```css
:root {
  --theme-color: #0EA5E9;        /* Primary color (links, active states) */
  --theme-color-dark: #0284C7;   /* Hover/darker shade */
}
```

## Adding New Documentation Pages

1. Create new `.md` file in `docs/manual/`
2. Use proper Markdown heading structure for auto-TOC
3. If adding multiple pages, consider switching to manual sidebar:
   - Change `loadSidebar: false` to `loadSidebar: true` in index.html
   - Update `docs/_sidebar.md` with navigation links
4. Test locally before pushing
5. Verify TOC/sidebar displays correctly

## Debugging TOC Issues

If table of contents doesn't appear correctly:

1. **Check Docsify config**: Verify `loadSidebar: false` in index.html:68
2. **Verify heading syntax**: Must use standard Markdown (`#`, `##`, `###`, `####`)
   - ❌ Bad: `## <a id="section">Section</a>`
   - ✅ Good: `## Section`
3. **Inspect browser console**: Look for Docsify JavaScript errors
4. **Clear cache**: Hard refresh (Ctrl+Shift+R / Cmd+Shift+R)
5. **Test with simple file**: If issue persists, test with a minimal .md file to isolate problem

## Key Terminology

- **Q101 Token**: Utility and governance token for Open Quest Academy's global education ecosystem
- **Airdrop**: Token distribution to eligible participants (community members, contributors)
- **Claim Process**: Multi-step verification and token receipt process
- **Vesting Schedule**: Three-phase token release structure:
  - Phase 1: 6-month waiting period (tokens locked)
  - Phase 2: Initial release (percentage of total allocation)
  - Phase 3: Monthly reward distributions
- **Web3 Wallet**: Cryptocurrency wallet (MetaMask, Coinbase, WalletConnect) required for claiming
- **Registration & Activation**: Process of connecting wallet and claiming eligibility

## Documentation Content Structure

CLAIM_GUIDE.md follows this organization:

1. **Airdrop Release Schedule** - Three-phase timeline explanation
2. **Prerequisites** - Web3 wallet installation and setup
3. **Registration & Activation** - Step-by-step claim instructions with screenshots
   - MetaMask connection method
   - Coinbase Wallet connection method
   - WalletConnect connection method
4. **Visual guides** - Embedded screenshots (base64-encoded) for each step

## Important Constraints & Warnings

### File Size Limitations
- **CLAIM_GUIDE.md is ~14MB** due to embedded base64 image data
- Standard Read operations may timeout - always use `offset`/`limit` or `Grep`
- Be extremely careful when editing to avoid corrupting base64 strings
- Consider file size when planning new image additions

### Production Deployment
- **Changes go live immediately** after pushing to master branch
- **Custom domain** (docs.q101.org) serves the site, not just GitHub Pages URL
- No build process means broken Markdown = broken production site
- Always test locally first - no staging environment

### Critical Docsify Configuration
- **Do not enable search plugin** - conflicts with auto-TOC
- **Do not change `loadSidebar: false`** - breaks automatic table of contents
- **Maintain heading hierarchy** - Docsify generates TOC from h1-h4 headings only

## Related Resources

- **Official Website**: https://q101.org
- **Airdrop Claim Portal**: https://claim.q101.com
- **Documentation Site**: https://docs.q101.org
- **GitHub Repository**: https://github.com/Open-Quest-Academy/q101-document
- **Main Q101 Repository**: Separate repository containing smart contracts and dApps

---

**When making updates, prioritize:**
1. Accuracy of claim instructions (errors could prevent users from accessing tokens)
2. Visual clarity (screenshots must match current UI)
3. Security warnings (wallet safety, scam prevention)
4. Consistent heading structure (required for auto-TOC functionality)
