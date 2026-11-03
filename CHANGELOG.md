# Changelog

All notable changes to NearDrop will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Added
- **Media Gallery View**: Dedicated gallery tab displaying photos and videos organized into chronological timeline groups by month and year.
- **Date, Month & Year Filtering**: Interactive toolbar with Year selector, Month selector, Exact Date calendar picker, and Media Type filters (Photos/Videos).
- **Multi-Criteria Sorting**: Sort media by Date (Newest/Oldest), Size (Largest/Smallest), or Name (A-Z/Z-A).
- **Selective On-Demand Download & Staging**: Browse phone photos from PC without transferring gigabytes upfront. Phone generates lightweight local thumbnails; PC can browse and download only the selected original copies.
- **Full-Screen Lightbox**: High-resolution image preview and video player with keyboard navigation, metadata inspector, and direct download buttons.
- **Inline Media Streaming**: New `/view/<id>` endpoint supporting native MIME rendering and HTTP 206 Partial Content range requests for seekable video playback.

## [1.0.0] - 2026-11-03
### Added
- Local Wi-Fi file and text transfer between PC and mobile devices.
- One-time QR code pairing with 5-minute expiry.
- Chunked 1 MiB uploads with resume and pause capabilities.
- Windows launcher and portable packaging.
- SQLite persistence for shared notes and files.

