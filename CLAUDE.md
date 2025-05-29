# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

SimpleMarkdownViewer is a single-file HTML application that provides a markdown viewer with drag-and-drop functionality. The entire application is contained within `SimpleMarkdownViewer.html` and requires no build process or dependencies.

## Architecture

- **Single HTML File**: All HTML, CSS, and JavaScript is contained in `SimpleMarkdownViewer.html`
- **External Dependencies**: Uses Marked.js (CDN) for markdown parsing and Mermaid.js (CDN) for diagram rendering
- **Core Features**:
  - Drag & drop markdown file support (.md, .markdown, .txt)
  - Real-time markdown rendering
  - Mermaid diagram support (flowcharts, sequence diagrams, class diagrams, etc.)
  - Dark/light theme toggle with automatic Mermaid theme switching
  - oEmbed support for Twitter and YouTube
  - Debug logging system
  - File size display

## Development Commands

No build process required. Simply open `SimpleMarkdownViewer.html` in a browser to test.

**Testing locally:**
```bash
# Open in browser (any of these methods)
open SimpleMarkdownViewer.html
firefox SimpleMarkdownViewer.html
python -m http.server 8000  # Then visit localhost:8000
```

## Code Structure

The application follows a modular JavaScript structure within the single HTML file:

- **DOM Elements**: All UI elements referenced at top of script
- **Debug System**: Logging functionality with toggle display
- **File Handling**: Drag & drop and file input processing
- **Markdown Processing**: Multi-stage process (Mermaid preprocessing → oEmbed preprocessing → rendering)
- **Mermaid Support**: Custom preprocessing with code block protection and diagram rendering
- **oEmbed Support**: Custom preprocessing for Twitter/YouTube embeds
- **Theme Management**: CSS class-based dark mode toggle with Mermaid re-rendering

## Key Implementation Details

- **Mermaid Processing**: 
  - Protected code block system: 4-backtick blocks (````mermaid) are preserved as code examples
  - Only 3-backtick blocks (```mermaid) are converted to diagrams
  - Asynchronous library loading with timeout handling
  - Theme-aware rendering that updates on dark mode toggle
  - Comprehensive error handling with fallback display
- **oEmbed Processing**: Uses placeholder replacement strategy to handle embeds before markdown parsing
- **Twitter Embeds**: Dynamically loads Twitter widgets script and processes tweets
- **YouTube Embeds**: Extracts video IDs from various YouTube URL formats
- **Debug Logging**: Maintains a 50-entry rolling log with timestamps
- **File Validation**: Checks file extensions before processing

## Styling Approach

- Uses CSS variables for theming
- GitHub-style markdown rendering
- Responsive design with flexbox layout
- Smooth transitions for UI state changes
- Mermaid diagram styling with automatic dark mode adaptation

## Mermaid Integration

**Supported Diagram Types:**
- Flowcharts (`graph TD`, `graph LR`, `flowchart`)
- Sequence diagrams (`sequenceDiagram`)
- Class diagrams (`classDiagram`)
- State diagrams (`stateDiagram`)
- Gantt charts (`gantt`)
- Pie charts (`pie`)
- ER diagrams (`erDiagram`)
- User journey maps (`journey`)
- Git graphs (`gitgraph`)
- All other Mermaid-supported diagram types

**Processing Pipeline:**
1. **Code Block Protection**: 4-backtick markdown code examples are temporarily protected
2. **Mermaid Detection**: 3-backtick ```mermaid blocks are identified and converted to HTML divs
3. **Library Loading**: Mermaid.js loads asynchronously with timeout handling
4. **Rendering**: SVG diagrams are generated and inserted into the DOM
5. **Theme Integration**: Diagrams automatically re-render when switching dark/light modes