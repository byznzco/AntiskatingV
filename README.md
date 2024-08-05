# AntiskatingV
A letterboxd equailivant of songs

Data Model
![output (1)](https://github.com/user-attachments/assets/20266719-59bb-4291-8376-121f325af447)

There is no relationship between many to many songs and so we should add association between them
![output (3)](https://github.com/user-attachments/assets/65f53d73-edb1-4c51-861c-cf76d0144052)

UML -class diagram can be like:


![output (5)](https://github.com/user-attachments/assets/9c97ae65-3558-4759-bb68-4d97f310764c)


## Class Diagram Overview

### User
Represents a user of the application. Users can write reviews, create playlists, and follow other users.

**Attributes:**
- `id`: int
- `username`: str
- `email`: str
- `password`: str
- `profile_picture`: str
- `bio`: str

**Methods:**
- `write_review(song, rating, comment)`
- `create_playlist(title, description, privacy)`
- `follow_user(user)`

### Song
Represents a song in the application.

**Attributes:**
- `id`: int
- `title`: str
- `artist`: str
- `album`: str
- `year`: int
- `genre`: str
- `link`: str
- `cover_image`: str

### Review
Represents a review written by a user about a song.

**Attributes:**
- `id`: int
- `song`: Song
- `user`: User
- `rating`: int
- `comment`: str
- `date`: date

### Playlist
Represents a playlist created by a user, which can be public or private.

**Attributes:**
- `id`: int
- `user`: User
- `title`: str
- `description`: str
- `privacy`: str
- `creation_date`: date

**Methods:**
- `add_song(song, order)`
- `remove_song(song)`

### PlaylistSong (Association Class)
Manages the many-to-many relationship between playlists and songs.

**Attributes:**
- `id`: int
- `playlist`: Playlist
- `song`: Song
- `order`: int

### Follower
Represents the follower relationship between users.

**Attributes:**
- `id`: int
- `follower`: User
- `following`: User
- `follow_date`: date

**Methods:**
- `unfollow()`

## Relationships

- **User** can write **Reviews** and create **Playlists**.
- **User**



