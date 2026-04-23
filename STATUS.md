# Plotify — shelved 2026-04-22

Bootcamp final project from University of Denver Data Analytics cohort `du-den-data-pt-08-2020-u-c` (2020-2021). Preserved for historical/portfolio reference.

## Why it's shelved

The app's core dimensions — danceability, energy, tempo, acousticness, etc. — come from Spotify's `audio-features` endpoint. Spotify restricted that endpoint (and `audio-analysis`, `recommendations`, related-artists, 30-second previews) to grandfathered developer apps in late 2024. A freshly-created app in 2026 gets `403 Forbidden` calling it.

The ML extension (Keras sequential NN for genre prediction) used the same endpoint for training data, so it's also dead.

Verified on 2026-04-22 with a freshly-registered Spotify app: `GET /v1/audio-features/{id}` → 403.

## What's preserved

- Full Flask + MongoDB + Vue + D3 app structure (from `paulywog13/spotify-project` upstream)
- ML extension for genre prediction
- Deployment scaffold (Pipenv, Procfile, Libsass middleware, Fixie Socks for Heroku static IP)

## What still works on a new Spotify app

User OAuth endpoints: top artists/tracks, recently-played, playlist contents with `added_by`/`added_at`/`snapshot_id`, artist genres (too granular to be useful), track popularity and metadata. Not enough to rebuild this project meaningfully.

## Architecture lessons worth reusing elsewhere

See `04 Resources/Cool References & Future Iterations.md` in the Obsidian vault — the `snapshot_id` cache-invalidation pattern and the Vue+D3 integration notes are the transferable bits.
