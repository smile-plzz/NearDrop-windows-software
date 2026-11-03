# Context: NearDrop

## Goals
- Provide zero-cloud, direct local-network media and file transfer between PC and mobile devices.
- Enable PC web browser access to browse media (photos/videos) from the phone in a rich Gallery view.
- Support sorting, date/month/year filtering, instant previews/thumbnails, and downloading selected original files on demand without needing to transfer the entire phone library upfront.

## Tech Stack
- **Backend**: Python 3.11+ built-in libraries (`http.server.ThreadingHTTPServer`, `sqlite3`, `hashlib`, `mimetypes`, `socket`, `threading`, `secrets`). No external heavy dependencies. Vendored `segno` for QR generation.
- **Frontend**: Vanilla HTML5, CSS3, ES2022 JavaScript (single-page app: `index.html`, `app.js`, `style.css`).
- **Packaging & Tools**: Windows x64 embeddable Python runtime, native launcher in Zig/C (`tools/launcher.c`), `NearDrop.cmd`.
- **Testing**: Python `unittest`, Playwright browser tests (`tests/browser.cjs`).

## Constraints
- **Security & Privacy**: Trusted Wi-Fi / LAN only, zero cloud relays, strict session token authentication via HttpOnly cookies, CSRF protection via custom `X-NearDrop` headers and host matching.
- **Client Sandbox Constraints**: Mobile browsers (iOS Safari, Android Chrome) operate within strict OS sandboxes and cannot silently scan or access the phone file system or photo library in the background without explicit user selection/permission.
- **Resource Efficiency**: Low memory footprint, chunked streaming for uploads and downloads, graceful thumbnail/preview caching without exhausting disk or memory.

