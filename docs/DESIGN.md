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

Database Design & Architecture
The Beathub backend utilizes a NoSQL relational structure via MongoDB and Mongoose. The database is normalized by separating distinct entities into their own collections and linking them using Mongoose ObjectId references.

Schema Relationships
User (models/User.js)
Stores authentication data. Contains arrays of ObjectIds referencing the Song and Artist collections.

Artist (models/Artist.js)
The core entity for music creators.

Album (models/Album.js)
Has a 1-to-1 reference to the Artist who created it. Has a 1-to-Many relationship with Song.

Song (models/Song.js)
Requires a direct ObjectId reference to both its parent Album and its creator Artist.

Playlist (models/Playlist.js)
Requires an owner field referencing a specific User ObjectId. Contains an array of Song ObjectIds.

Design Decisions
Timestamps: Every schema utilizes { timestamps: true } to automatically track document creation and update times.
Validations: Strict required and unique constraints are applied at the schema level.