# Qualitative Moderator Co-Pilot

A production-ready, client-side, 100% offline-first web application designed to help user researchers moderate interviews (IDIs). It serves as a smart teleprompter, real-time pacing engine, and time-management tool optimized for running side-by-side with video conferencing software (like Zoom).

## Features

- **100% Offline & Local**: Respects strict NDAs by working fully client-side. Zero external API calls or network requirements.
- **Named Stimuli Library**: Organize prototype links, images, or documents in a central project directory, then link them directly to interview questions.
- **Screen Share Reminders**: Schedule animated action alerts (e.g., "📺 Action: Ask participant to share screen" or "💻 Action: Share your screen") to trigger on relevant questions.
- **Visual Pacing Roadmap**: A visual session timeline that breaks down the guide duration by section, automatically updating as you add time or priority tags.
- **Dynamic Pacing Engine**: Recalculates remaining session time and question pacing in real-time. Sections marked as **Strict Priority** keep their full nominal durations, while non-priority sections compress proportionally if you run over time.
- **Document Extractors**: Built-in offline Word document (`.docx`) and PDF (`.pdf`) parsers to extract raw interview questions and convert them into structured moderation guides.
- **Portability**: Quick CSV project export/import alongside full JSON workspace backups.
- **Responsive Layout**: Designed to reflow elegantly when snapped to half of the browser screen next to Zoom, Google Meet, or Microsoft Teams.
- **Keyboard Shortcuts**:
  - `Right Arrow`: Next Question
  - `Left Arrow`: Previous Question
  - `Spacebar`: Play/Pause Session Timer
- **Parked Topics**: Floating quick topic parking with custom Toast notifications, compiling a review checklist for the post-session wrap-up.

## Getting Started

1. **Setup Libraries**: All the required JavaScript libraries are stored locally in the `lib/` directory for true offline compatibility. If you ever need to redownload them, run:
   ```bash
   ./setup_libs.sh
   ```

2. **Run the App**: 
   - Simply double-click `index.html` to open it in your browser (via `file://` protocol).
   - Alternatively, serve it locally using Python:
     ```bash
     python3 -m http.server 8000
     ```
     Then navigate to `http://localhost:8000`.

## Architecture & Tech Stack

- **Framework**: [React](https://react.dev) (v18.2.0) with [Babel Standalone](https://babeljs.io) for inline compile-free browser rendering.
- **Styling**: [Tailwind CSS Play CDN](https://tailwindcss.com) (v3.4.1) configured for in-browser compile-free utility classes and full Dark Mode customization.
- **Document Extractors**: [Mammoth.js](https://github.com/mikeshadbolt/mammoth.js) (v1.6.0) for Word documents and [PDF.js](https://mozilla.github.io/pdf.js/) (v3.11.174) for PDF documents.
- **Storage**: Browser `localStorage` to save guides, settings, and active session states securely and privately on your machine.
- **Icons**: Inline hand-crafted SVGs.
