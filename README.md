# Docker Markdown Viewer

An over-engineered Markdown viewer packaged as a Docker container.

## Features

- Real-time Markdown preview with syntax highlighting
- MathJax support for inline `\(...\)` and block `\[...\]` math
- Dark mode toggle
- Auto-save with unsaved-changes indicator
- Multiple document management with named saves
- Export to HTML (copy or download)
- Writer Zen and Reader Zen distraction-free modes
- Scroll navigation buttons in each pane label:
  - **Editor**: scroll to top, scroll to text cursor
  - **Preview**: scroll to top, sync to editor cursor (dual mode only)

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
