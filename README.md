# Music Control CLI

A simple command-line tool for searching and playing YouTube Music songs.

## Quick Start

```bash
# Search for a song
music-search "Pitbull Feel This Moment"

# Open a song directly
music-play "Frank Sinatra Fly Me to the Moon"

# Open on a remote Mac via SSH
music-play-remote mariovillalpando@100.82.138.125 "Billie Eilish bad guy"
```

## Installation

1. Install the Python dependency:
```bash
pip install ytmusicapi
```

2. Add the scripts to your PATH (or use full paths):
```bash
# Option 1: symlink to /usr/local/bin
sudo ln -s ~/.openclaw/workspace/skills/music-control/scripts/* /usr/local/bin/

# Option 2: add to PATH
export PATH="$HOME/.openclaw/workspace/skills/music-control/scripts:$PATH"
```

## Features

- ✅ Search YouTube Music without authentication
- ✅ Get video IDs and URLs instantly
- ✅ Open songs in local or remote browsers
- ✅ Simple CLI interface
- ✅ No OAuth setup required

## Usage Examples

### Search for songs
```bash
music-search "Dua Lipa Levitating"
# Returns: video ID, title, artist, duration, and YouTube URL
```

### Play locally (on machine with browser)
```bash
music-play "The Weeknd Blinding Lights"
# Opens YouTube in your default browser
```

### Play on remote Mac
```bash
music-play-remote mariovillalpando@odysseus "Queen Bohemian Rhapsody"
# SSHes to remote machine and opens in Safari
```

## Important Notes

- **Autoplay**: Modern browsers may block autoplay. You might need to click play once.
- **Volume**: Must be adjusted manually on the playback machine.
- **Remote playback**: Requires SSH access and Safari running on the target machine.

## Troubleshooting

**"No results found"**: Try a more specific search query or check your internet connection.

**"Couldn't open browser"**: The script couldn't detect a browser command. Copy the URL and open manually.

**"SSH command failed"**: Make sure SSH keys are set up for the remote machine and Safari is running.

## License

MIT - Feel free to use and modify!
