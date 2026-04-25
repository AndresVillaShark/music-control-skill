# music-control - YouTube Music CLI

Control YouTube Music playback from the terminal using the unauthenticated `ytmusicapi` library.

## Overview

This skill provides a simple CLI for searching YouTube Music and opening songs in your browser. Ideal for quick music playback without authentication complexity.

## Installation

### Prerequisites

```bash
# Install the Python library
pip install ytmusicapi
```

### Verify Setup

```bash
# Test that the library works
python3 -c "from ytmusicapi import YouTubeMusic; ytm = YouTubeMusic(); print(ytm.search('Pitbull', filter='songs', limit=1))"
```

## Usage

### Search for Songs

```bash
# Basic search
ytmusic-search "artist name or song title"

# Examples
ytmusic-search "Pitbull Feel This Moment"
ytmusic-search "Frank Sinatra Fly Me to the Moon"
ytmusic-search "Dua Lipa Levitating"
```

The search returns video IDs and basic info. Use the video ID to construct a YouTube URL:
```
https://www.youtube.com/watch?v=VIDEO_ID&autoplay=1
```

### Open in Browser

**On the same machine (if GUI available):**
```bash
ytmusic-play "song query"
```

**On a remote machine via SSH:**
```bash
# Open on remote Mac/Linux machine
ytmusic-play-remote user@host "song query"

# Example for Odysseus
ytmusic-play-remote mariovillalpando@100.82.138.125 "Billie Eilish bad guy"
```

## How It Works

1. **Search Phase**: Uses `ytmusicapi.search()` to find matching songs
2. **Playback Phase**: Opens `https://www.youtube.com/watch?v=VIDEO_ID&autoplay=1` in the browser

## Important Notes

- **Autoplay Limitation**: Modern browsers may block autoplay. You might need to click play once.
- **Volume Control**: Volume must be adjusted on the playback machine, cannot be controlled remotely.
- **Unauthenticated**: Works without OAuth setup - perfect for search and manual playback.

## Files

- `ytmusic-search` - Search for songs
- `ytmusic-play` - Search and open in local browser
- `ytmusic-play-remote` - SSH to remote machine and open Safari/Chrome

## Customization

Edit the scripts in `scripts/` to add your own presets or modify behavior.
