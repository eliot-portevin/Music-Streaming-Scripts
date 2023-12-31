# YouTube Music to Spotify Synchronisation Script

This Python script allows you to synchronise your liked songs between YouTube Music and Spotify. It leverages the `ytmusicapi` library for YouTube Music interaction and the `spotipy` library for Spotify interaction. By using this script, you can keep your favorite songs up-to-date across both platforms.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Authentication](#authentication)
- [Results](#results)

## Prerequisites

Before using this script, you'll need the following:

- Python 3.x installed on your computer.
- A Google account for YouTube Music.
- A Spotify account.

## Getting Started

1. Clone this repository or download the script to your local machine.

2. Install the required Python packages using pip:

   ```bash
   pip install ytmusicapi spotipy
   ```

3. Ensure you have the necessary API keys and tokens for YouTube Music and Spotify. Refer to the [Authentication](#authentication) section for instructions on setting up authentication.

## Usage

### Command Line Arguments

The script uses command line arguments to determine the synchronisation direction. You can use the following flags:

- `--yt_to_sp`: Synchronise liked songs from YouTube Music to Spotify.
- `--sp_to_yt`: Synchronise liked songs from Spotify to YouTube Music.
- `--all`: Synchronise liked songs in both directions (YouTube Music to Spotify and Spotify to YouTube Music)
- `--help`: Display explanation of command line arguments.

### Example Usage

Sync liked songs from YouTube Music to Spotify:

```
python3 main.py --yt_to_sp
```

## Authentication

### YouTube Music Authentication

The script uses the `ytmusicapi` library for YouTube Music. To authenticate:

1. Run the script for the first time.

2. You will be prompted to follow the instructions for authenticating your Google account. This will generate an `oauth.json` file containing authentication tokens.

### Spotify Authentication

The script uses the `spotipy` library for Spotify. To authenticate:

1. Create a Spotify application in the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/applications). Set the redirect URI to `https://localhost:8888/callback`.

2. After creating the application, copy the client ID and client secret. Note these down for later.

3. Run the script for the first time.

4. When prompted to do so, enter your Spotify client ID, client secret, and username. These details will be saved in a `spotify_oauth.json` file for future use.

5. The script will guide you through the Spotify authentication process, including opening a browser window for authorization. Follow the instructions.

## Results

After synchronisation, you can check the log files for the results:

- `yt_to_sp.log`: Contains information about songs successfully added to Spotify, songs already added, and songs not found on Spotify.

- `sp_to_yt.log`: Contains information about songs successfully added to YouTube Music and songs not found on YouTube Music.