# Docker Markdown Viewer

An over-engineered Markdown viewer packaged as a Docker container.

## Features

- **Real-time preview** — live Markdown rendering as you type
- **Syntax highlighting** — code blocks highlighted via Highlight.js with Catppuccin theme (dark/light variants)
- **Copy button on code blocks** — appears on hover, copies code to clipboard
- **Math support** — inline `\(...\)` and block `\[...\]` LaTeX via MathJax
- **Dark/light theme** — toggle persists to localStorage; respects `prefers-color-scheme` on first visit
- **Auto-save** — debounced 1s after typing, with unsaved-changes indicator
- **Multiple documents** — save, load, and delete named documents stored in localStorage, shown as chips
- **Export to HTML** — copy rendered HTML to clipboard or download as a standalone `.html` file
- **Dual mode** — split editor/preview side by side
- **Writer Zen** — fullscreen editor, preview hidden
- **Reader Zen** — fullscreen preview, editor and topbar hidden (Esc or button to exit)
- **Caret indicator** — highlights the corresponding preview element while editing
- **Scroll controls** — in each pane label:
  - **Editor**: scroll to top, scroll to text cursor
  - **Preview**: scroll to top, sync scroll to editor cursor position
- **Collapsible tools drawer** — hides the bottom toolbar to maximize editing space; state persists
- **Mobile responsive** — collapses to single pane at ≤768px with Editor/Preview toggle buttons

## Getting Started

### Prerequisites

- Docker and Docker Compose installed on your system

### Quick Start

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/docker-markdown-viewer.git
   cd docker-markdown-viewer
   ```

2. Build and start the container:
   ```bash
   docker-compose up -d
   ```

3. Access the Markdown viewer in your browser:
   ```
   http://localhost:8080
   ```

### Manual Docker Build

If you prefer not to use Docker Compose:

1. Build the Docker image:
   ```bash
   docker build -t markdown-viewer .
   ```

2. Run the container:
   ```bash
   docker run -d -p 8080:80 markdown-viewer
   ```

## Development

### Project Structure

- `index.html` - The main HTML file containing the Markdown viewer application
- `Dockerfile` - Instructions for building the Docker image
- `docker-compose.yml` - Configuration for Docker Compose deployment

### Customization

To modify the application:

1. Make changes to `markdown-viewer.html`
2. Rebuild the Docker image:
   ```bash
   docker-compose build
   # or
   docker build -t markdown-viewer .
   ```

3. Restart the container:
   ```bash
   docker-compose up -d
   # or
   docker run -d -p 8080:80 markdown-viewer
   ```

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- [Marked.js](https://marked.js.org/) for Markdown parsing
- [Highlight.js](https://highlightjs.org/) for code syntax highlighting
- [MathJax](https://www.mathjax.org/) for math rendering
- [Nginx](https://nginx.org/) for serving the static content
