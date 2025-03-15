# taskmcp

Spotify MCP Server

This project is a FastAPI-based server implementing the Model Context Protocol (MCP) to interact with Spotify's Web API. It enables actions like searching for tracks and fetching playlist details.

Features

Search for tracks on Spotify

Retrieve playlist details

MCP interaction endpoint for structured requests

Prerequisites

Python 3.9+

Spotify Developer Account (https://developer.spotify.com/)

Client ID and Client Secret from a Spotify app

Setup

Clone the repository:

git clone https://github.com/yourusername/spotify-mcp-server.git
cd spotify-mcp-server

Create a virtual environment and activate it:

python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

Install dependencies:

pip install fastapi uvicorn requests python-dotenv

Create a .env file in the project root and add your Spotify credentials:

SPOTIFY_CLIENT_ID=your_spotify_client_id
SPOTIFY_CLIENT_SECRET=your_spotify_client_secret

Running the Server

Start the server with:

uvicorn main:app --reload

The server will run at http://127.0.0.1:8000/.

Endpoints

1. Search Tracks

GET /search?query=<track_name>

Example:

curl "http://127.0.0.1:8000/search?query=Imagine"

2. Get Playlist

GET /playlist/{playlist_id}

Example:

curl "http://127.0.0.1:8000/playlist/37i9dQZF1DXcBWIGoYBM5M"

3. MCP Interaction

GET /mcp?action=<action>&query=<query>

Actions:

search: Search tracks

get_playlist: Get playlist details

Example:
