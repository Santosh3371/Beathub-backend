# BeatHub Design Document

## 1. Data Relationships
*   **Artist:** Parent entity.
*   **Album:** References Artist.
*   **Song:** References Album and Artist.
*   **User:** Independent entity.
*   **Playlist:** References User and contains an array of Song references.

## 2. Design Decisions (Defend Your Code)

**Q: Why did you reference Songs in the Playlist instead of embedding them?**
*   **A:** (Your Answer: Explain that if a Song's details change—like a title update—referencing ensures the Playlist sees the new title automatically. Embedding would require updating every single playlist that has that song.)

**Q: Why did you reference the Artist in the Song model?**
*   **A:** (Your Answer: To allow for faster queries like "Find all songs by Daft Punk" without needing to look up all albums first.)