# Docker Markdown Viewer

A Markdown editor focused on comfortable writing and reading — not document management. The primary use case is flexible input with real-time preview: paste, draft, or compose Markdown and see it rendered instantly. Document saving is available as a lightweight snapshot feature, not the main point.

## Design priorities

1. **Editing comfort** — clean editor with auto-save to session state, zen writing mode, caret tracking
2. **Reading comfort** — distraction-free reader zen, synced scroll, rich copy for pasting rendered content elsewhere
3. **Flexible input** — works well for one-off use without ever touching the document panel
4. **Snapshots, not a file manager** — save/load named documents stored in localStorage as a convenience, not a workflow

## Features

### Editor & preview
- **Real-time preview** — live Markdown rendering as you type
- **Syntax highlighting** — code blocks highlighted via Highlight.js with Catppuccin theme (dark/light variants)
- **Copy button on code blocks** — appears on hover
- **Math support** — inline `\(...\)` and block `\[...\]` LaTeX via MathJax
- **Rich copy** — copies rendered preview as HTML+text, preserving formatting when pasting into Notion, Docs, etc.
- **Export to HTML** — copy rendered HTML to clipboard or download as a standalone `.html` file
- **Caret indicator** — highlights the corresponding preview element while editing
- **Scroll controls** — scroll to top or sync to cursor position in either pane

### Modes
- **Writer Zen** — fullscreen editor, preview hidden
- **Reader Zen** — fullscreen preview, editor and chrome hidden (Esc or button to exit)
- **Dual mode** — split editor/preview side by side

### Persistence & documents
- **Auto-save** — editor state saved to browser storage 1s after typing; survives page reload without any action
- **Named snapshots** — save the current content as a named document, load or delete from the documents panel
- **Dark/light theme** — toggle persists to localStorage; respects `prefers-color-scheme` on first visit
- **Collapsible tools drawer** — hides the bottom toolbar to maximize editing space; state persists

### Responsive
- **Mobile** — collapses to single pane at ≤768px with Editor/Preview toggle

## Getting Started

### Prerequisites

- Docker and Docker Compose installed on your system

### Quick Start

1. Clone this repository:
   ```bash
   git clone https://github.com/ucencode/md-viewer.git
   cd md-viewer
   ```

2. Build and start the container:
   ```bash
   docker-compose up -d
   ```

3. Access the Markdown viewer in your browser:
   ```
   http://localhost:3301
   ```

## Development

### Project Structure

- `index.html` — The main application file (editor + preview + all UI)
- `Dockerfile` - Instructions for building the Docker image
- `docker-compose.yml` - Configuration for Docker Compose deployment

## Acknowledgments

- [Marked.js](https://marked.js.org/) for Markdown parsing
- [Highlight.js](https://highlightjs.org/) for code syntax highlighting
- [MathJax](https://www.mathjax.org/) for math rendering
- [Nginx](https://nginx.org/) for serving the static content
