# Dev Log

## [2026-11-03 14:13] - Task Initialization: Media Gallery & Browser on PC
- User verified NearDrop 1.0.0 is working as expected.
- Received request to plan feature: Access and browse phone media from the PC's web browser in a Gallery view with sorting, specific date/month/year filtering, and on-demand selective downloading.
- Initialized project tracking docs: `context.md`, `CHANGELOG.md`, `dev-log.md`.
- Entering planning phase (`/plan`) to explore architectural patterns and present implementation plan.

## [2026-11-03 14:26] - Implementation & Verification: Media Gallery, Date Filtering, and On-Demand Streaming
- Implemented inline media streaming endpoint `/view/<id>` with Range 206 support for photos and videos.
- Created `staged_media` and `download_requests` schema in SQLite to coordinate zero-cloud on-demand media transfers.
- Added `/api/gallery`, `/api/gallery/stage`, `/api/gallery/unstage`, `/api/gallery/request`, and `/api/gallery/requests` endpoints in `app/server.py`.
- Built rich frontend Media Gallery in `app/index.html` with:
  - Tab strip switching between "Shared Files" and "Media Gallery".
  - Multi-parameter filter toolbar: Year dropdown, Month dropdown, Exact Date calendar input, Media Type (Photos/Videos), Sorting (Date Newest/Oldest, Size Largest/Smallest, Name A-Z/Z-A), and instant search.
  - Chronological timeline grouping by Month and Year headers.
  - Multi-select batch downloading (`Download Selected (N)`).
  - Full-screen Lightbox dialog with keyboard navigation (`ArrowLeft`, `ArrowRight`, `Escape`), metadata drawer, and direct download actions.
  - Mobile photo/video staging workflow (`Browse Phone Media on Laptop`) with client-side canvas thumbnail generation.
- Styled responsive cards, video badges, staging chips, and dark backdrop lightbox in `app/style.css`.
- Added unit and integration tests in `tests/test_server.py` covering inline streaming, gallery discovery, staging, request negotiation, and download verification.
- Verification: Ran `python -m unittest discover -s tests -v` — 8/8 tests passed successfully in 4.96s.

