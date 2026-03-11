Beathub Backend
A robust Node.js and MongoDB backend API for a music streaming platform. This project manages users, artists, albums, songs, and custom user playlists using Mongoose for database modeling.

Technologies Used
Node.js

MongoDB Atlas

Mongoose (ODM)

dotenv (Environment variable management)

Security Note
Database credentials are strictly protected. The connection string is managed using environment variables via the dotenv package. The .env file is explicitly excluded from version control using .gitignore to prevent sensitive data leaks.

Local Setup & Installation
Clone the repository:
git clone 

Install dependencies:
npm install

Set up Environment Variables:
Create a .env file in the root directory and add your MongoDB connection string.

Run the Database Seed Script:
node scripts/seed.js