# Spotify Streaming Data: Domain Document

This document outlines the key fields in the Spotify track-level streaming dataset, describing each attribute's purpose, format, and analytical value.

---

## 1. `spotify_track_uri`
- **Description:**  
  A globally unique identifier for each track in Spotify’s ecosystem.
- **Format:**  
  `spotify:track:<base-62 string>`  
  _Example:_ `spotify:track:3n3Ppam7vgaVa1iaRUc9Lp`
- **Analytical Use:**  
  Facilitates cross-referencing with Spotify's catalog and metadata repositories. Essential for track-level analysis and linking external datasets.

---

## 2. `ts` (Timestamp)
- **Description:**  
  The UTC timestamp marking the moment the track stopped playing.
- **Format:**  
  ISO 8601 datetime format  
  _Example:_ `2024-02-07T14:30:45Z`
- **Analytical Use:**  
  Critical for time series analysis, session tracking, hourly trends, and listening behavior over time.

---

## 3. `platform`
- **Description:**  
  The playback platform used to stream the track.
- **Possible Values:**
  - `desktop` – Spotify desktop app (Windows/macOS)  
  - `mobile` – Mobile app (iOS/Android)  
  - `web` – Spotify Web Player  
  - `smart_speaker` – Devices like Amazon Echo, Google Home
- **Analytical Use:**  
  Helps in understanding user preferences by platform and targeting optimizations for device-specific experiences.

---

## 4. `ms_played`
- **Description:**  
  Duration (in milliseconds) the track was played.
- **Format:**  
  Integer  
  _Example:_ `215000` (equivalent to 3 minutes 35 seconds)
- **Analytical Use:**  
  Used for calculating listening time, engagement levels, completion rates, and monetization analytics.

---

## 5. `track_name`
- **Description:**  
  Title of the song that was streamed.
- _Example:_ `"Shape of You"`
- **Analytical Use:**  
  Enables identification of trending songs and ranking based on play counts.

---

## 6. `artist_name`
- **Description:**  
  Name of the performer or music group.
- _Example:_ `"Ed Sheeran"`
- **Analytical Use:**  
  Supports artist popularity tracking, fan engagement measurement, and genre-based analysis.

---

## 7. `album_name`
- **Description:**  
  Album to which the streamed track belongs.
- _Example:_ `"÷ (Divide)"`
- **Analytical Use:**  
  Helps in album-level popularity analysis, understanding listening trends over releases.

---

## 8. `reason_start`
- **Description:**  
  Trigger that initiated track playback.
- **Possible Values:**
  - `trackdone` – Auto-play after previous track  
  - `clickrow` – Manual selection by user  
  - `backbtn` – Previous track replayed  
  - `fwdbtn` – User skipped forward  
  - `playbtn` – User initiated playback  
  - `autoplay` – System-generated recommendation
- **Analytical Use:**  
  Offers insight into user interaction patterns and how often users actively engage with content vs. passive listening.

---

## 9. `reason_end`
- **Description:**  
  Event or action that caused the track to stop playing.
- **Possible Values:**
  - `trackdone` – Track finished  
  - `endplay` – User paused/stopped  
  - `fwdbtn` – User skipped forward  
  - `backbtn` – User skipped backward  
  - `logout` – Session ended
- **Analytical Use:**  
  Vital for understanding listening drop-off, skip behavior, and session termination patterns.

---

## 10. `shuffle`
- **Description:**  
  Indicates if shuffle mode was active during playback.
- **Possible Values:**
  - `TRUE` – Shuffle was enabled  
  - `FALSE` – Sequential playback
- **Analytical Use:**  
  Helps in understanding user listening preferences and impacts on track/artist discovery.

---

## 11. `skipped`
- **Description:**  
  Denotes whether the track was skipped before completion.
- **Possible Values:**
  - `TRUE` – User skipped  
  - `FALSE` – Track played completely
- **Analytical Use:**  
  Critical for engagement scoring, determining track appeal, and refining recommendation algorithms.
