# QuickVoice Notes

A zero-dependency, single-file mobile web application for recording, reordering, and transcribing voice memos directly in the browser. Optimized for iOS Safari standalone PWA execution.

## Features

- **In-Browser Audio Recording:** Captures audio using `MediaRecorder` targeting iOS-compatible codecs (`audio/mp4` / AAC fallback).
- **Speech-to-Text Transcription:** Real-time speech transcription via the Web Speech API (`SpeechRecognition` / `webkitSpeechRecognition`).
- **Inline Editing & Reordering:** Live-edit transcripts directly on cards; adjust stack priority with one-tap shift buttons.
- **PWA Ready:** Configured with iOS-specific meta tags (`apple-mobile-web-app-capable`) for standalone full-screen execution.
- **Single File:** Pure HTML5, vanilla JavaScript, and Tailwind CSS (CDN). No build step or bundler required.

## Installation & Deployment

iOS blocks microphone access (`getUserMedia`) and the Web Speech API on insecure origins. The file must be served over HTTPS.

### 1. Host via GitHub Pages

1. Push `index.html` to a GitHub repository.
2. Go to **Settings** > **Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Set the branch to `main` (or `master`) and directory to `/ (root)`.
5. Click **Save**. GitHub Pages will provision an HTTPS endpoint: `https://<username>.github.io/<repo>/`.

### 2. Local Development (HTTPS)

To test locally from a machine to an iPhone on the same network:

```bash
# Using mkcert + local-web-server or caddy
caddy file-server --listen :8443 --tls internal
