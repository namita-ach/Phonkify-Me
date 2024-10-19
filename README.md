# Phonkify-Me
---
## Why tho
Well, I love all music, but my favorite is the kind without lyrics, so naturally, I was a pretty big classical music nerd. Fun, right? I thought that was the only kind of music I'd listen to, but then I found EDM. From EDM, I moved to Dubstep, then to Trap, even Latin Pop- and somewhere along the line, listening to all these and a whole bunch of other genres too, I realised that I like music that has *depth* and not just the same beat over and over. 

I pay more attention to the accompaniments, I feel more moved by the layers the music has- the bass that changes, the seemingly repetitive patterns that shift chords ever so slightly- and when I found phonk, I was hooked. 

Problem, though. Some tracks genuinely gave me a headache- the music was complex, exactly as I like it, but the chord progesssions threw me off and it wasn't very fun. On the brighter side, certain tracks (Read: X-Tali, Glory, DNA) made me feel this... primal sense of joy. I could feel it resonate in my soul and I promise I'm not being dramatic. I got bored of keeping two hours a week to look for songs like those and give myself headaches from the icky tracks I'd have to listen to before I found the ones I love, and made this. 

I just wanted a way to find songs that are most similar to the ones I love, without considering the artist, producer, or anything else. 

---

## Prototype 0: Short-Time Fourier Transform (STFT) and Mel-Frequency Cepstral Coefficients (MFCC)

### What Was Done
- The first prototype focused on analyzing **three audio tracks** using two feature extraction techniques: **STFT** and **MFCC**.

### Technical Concepts
- **STFT**: This method helps analyze the frequency content of a signal over time. It breaks down a song into smaller segments to see how its sound changes. This is useful for understanding how different sounds come together in music.
  
- **MFCC**: This stands for Mel-Frequency Cepstral Coefficients. It captures the timbral characteristics of audio signals and helps understand how humans perceive sound by focusing on the frequencies that matter most to our ears.

### Challenges Faced
- **Limited Data**: Analyzing just three tracks didn’t provide much variety for meaningful comparisons, they did serve as my benchmark, though. 
  
- **Lack of Advanced Features**: There was a realization that more complex features could enhance understanding.

### Solutions Implemented
- Both STFT and MFCC were implemented to provide a comprehensive view of audio characteristics.
  
- A comparison between the two methods helped reveal their strengths and weaknesses, setting the stage for future work.

---

## Prototype 1: Full Playlist with MFCC and Levenshtein Distance

### What Was Done
- The second prototype expanded the analysis to a **full playlist**, utilizing MFCC for feature extraction and incorporating **Levenshtein distance** to correct user input errors.

### Technical Concepts
- **Levenshtein Distance**: This metric measures how different two sequences are by counting the minimum number of single-character edits required to change one word into another. It’s useful for correcting typos in song titles.

### Challenges Faced
- **User Input Errors**: Common misspellings or incorrect song titles made it difficult to find matches.

### Solutions Implemented
- Levenshtein distance was integrated into the search function to suggest corrections for user input, improving overall user experience.
  
- Expanding from three tracks to a full playlist allowed for more robust analysis and comparisons between songs.

---

## Prototype 2: Spotify API with High-Level Feature Comparison

### What Was Done
- This prototype utilized the **Spotify API** to search for songs based on user input while retrieving high-level audio features for comparison.

### Technical Concepts
- **Spotify API**: A web service that provides access to Spotify’s massive music library, allowing searches for songs and retrieval of metadata.
  
- **Cosine Similarity**: A metric that measures how similar two vectors are regardless of their size. It calculates the cosine of the angle between them, which is useful for comparing feature vectors.

### Challenges Faced
- **Authentication Issues**: Setting up OAuth tokens to access Spotify’s data was initially tricky.

### Solutions Implemented
- Authentication was successfully implemented using Bearer tokens, enabling secure access to Spotify's data.
  
- High-level features such as energy, danceability, and valence were pulled from Spotify’s audio features endpoint for effective comparisons.

---

## Prototype 3: Spotify API with Removed Repetition and Two List Split

### What Was Done
- In this prototype, the focus was on refining earlier implementations by removing repetitive tracks from search results and categorizing similar tracks into two distinct lists: slowed/sped versions and different songs.

### Challenges Faced
- **Redundant Results**: Initial searches often returned multiple versions of the same song (like remixes), cluttering output.

### Solutions Implemented
- Duplicates were filtered out based on track IDs so each song appeared only once in results.
  
- Creating two separate lists helped clarify which tracks were variations versus entirely different songs, making it easier for users to find what they wanted!

---

## Prototype 4: Higher Priority Given to Bass Characteristics

### What Was Done
- The final prototype focused on analyzing audio features with an emphasis on bass characteristics while still considering all available features from Spotify.

### Technical Concepts
- **Bass Characteristics**: Features like energy, loudness, danceability, and acousticness can indicate how pronounced bass is in a track. 

### Challenges Faced
- **Balancing Feature Importance**: It was crucial to ensure that while prioritizing certain features like energy and danceability, other relevant characteristics weren’t neglected.

### Solutions Implemented
- The feature extraction logic was adjusted by scaling prioritized features (energy, danceability, valence) while still including all available features in similarity calculations.
  
- Enhanced similarity calculations using cosine similarity based on these prioritized features helped identify tracks that matched user preferences effectively!

---
