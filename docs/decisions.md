# musicgessr: decisions log

Last updated: 2026-11-22

## Goal
Homemade version of a music-timeline card game: players take turns placing songs in chronological order by release date. Naming the song title and artist earns tokens that can be spent on bonuses.

## Decisions so far
- **Platform:** Android app (not a web app). Chosen because Spotify's Android SDK can start songs in the Spotify app while our app stays in front.
- **Scope:** private and non-commercial, for the owner and a few friends. Commercialisation is not realistic for now.
- **Music source:** Spotify, via the Android App Remote SDK (Spotify app must be installed on the phone).
- **Song data:** our own curated database of N songs. Each song has title, artist, original release year (checked by us, not taken from Spotify, because Spotify gives the album date) and a Spotify link/URI.
- **Architecture rule:** keep audio playback behind a small interface so another source (30-second previews, etc.) can be swapped in later.

## Spotify constraints (checked Nov 2026)
- Development Mode: app owner needs Premium; max 5 authorized users; 1 Client ID per developer (the migration guide notes a later increase).
- Extended quota (public release) needs a registered business and about 250k monthly users, so out of reach.
- Developer Policy limits commercial use of streaming apps. Not relevant while the project stays non-commercial.
- Players on their own phones need to be added to the allowlist (name and email) in the Spotify developer dashboard.
- Premium is needed for reliable on-demand playback through App Remote.

## Legal notes (only matter if commercialised later)
- HITSTER is a registered trademark of Koninklijke Jumbo B.V. Use a different name and our own design.
- Game mechanics are not copyright-protected, but names and visual style are.

## Open questions
- App framework: React Native/Expo (recommended) or native Kotlin.
- How many friends will play, and whether each plays on their own phone or everyone shares one.
- Exact rules and bonuses for tokens.
- Whether the Android App Remote connection is stable enough in practice (needs a prototype).
