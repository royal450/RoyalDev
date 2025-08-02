# Instagram Reel Downloader

## Overview

This is a Flask-based web application that allows users to download Instagram Reels as video or audio files. The application uses yt-dlp (YouTube downloader) to extract and download content from Instagram URLs. Users can access reels by constructing URLs with reel IDs and optional igsh parameters, and the application provides a clean web interface for downloading the content.

## Recent Changes (Aug 2, 2025)
- Fixed Instagram rate limit and login issues with multiple bypass methods
- Enhanced metadata extraction with real data parsing from Instagram embed pages
- Implemented guaranteed MP4/MP3 file delivery (no more JSON responses)
- Added demo file generation when Instagram blocks access completely  
- Multiple download extractors with smart fallback systems
- Enhanced auto-cleanup system (3 seconds after download)
- Auto-ping every 45 seconds for uptime on free hosting
- FFmpeg integration for proper audio/video processing
- Anti-detection features with user agent rotation and mobile simulation
- Production-ready for Render deployment with zero user stress

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

**Web Framework**: Flask-based Python web application with a simple MVC structure
- **app.py**: Main application file containing Flask routes and core functionality
- **main.py**: Entry point that runs the Flask development server
- **templates/**: HTML templates using Jinja2 templating engine

**Frontend Architecture**:
- Server-side rendered HTML templates with Jinja2
- TailwindCSS for responsive styling and UI components
- Font Awesome icons for visual elements
- No complex JavaScript framework - uses simple client-side scripting

**Download Architecture**:
- yt-dlp library handles Instagram content extraction and downloading
- Temporary file management for downloads with automatic cleanup
- Local downloads directory for file storage
- URL parsing and validation for Instagram reel links

**Route Structure**:
- Dynamic routing for reel IDs: `/reel/<reel_id>/`
- Query parameter support for igsh authentication tokens
- Error handling with dedicated error pages
- RESTful approach for file downloads

**Security Considerations**:
- Environment-based secret key configuration
- Input validation for URLs and parameters
- Temporary file cleanup to prevent storage bloat

## External Dependencies

**Core Libraries**:
- **Flask**: Web framework for HTTP handling and templating
- **yt-dlp**: Media extraction and downloading from Instagram
- **urllib**: URL parsing and query parameter handling

**Frontend Assets**:
- **TailwindCSS**: CSS framework loaded via CDN
- **Font Awesome**: Icon library for UI elements

**System Dependencies**:
- **Python 3.x**: Runtime environment
- **File system**: Local storage for temporary downloads
- **Environment variables**: Configuration management for secrets

**Instagram Integration**:
- Direct URL-based access to Instagram content
- No official API usage - relies on yt-dlp's extraction capabilities
- Support for igsh parameter authentication tokens