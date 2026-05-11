# ALBUMS_DATABASES

**Course:** NoSQL Databases  
**Team:** Eilin Palomo, Jorge Zainea, Laura Saenz  
**Database:** Album — MongoDB Atlas  
**Cluster:** cluster0.h63ud7p.mongodb.net  

---

## Project Overview

This project simulates a Data Lake environment for Universal Studios Colombia using MongoDB. The database `Album` contains music data organized in collections by artist, where each document represents a song with its metadata and cover image reference.

---

## Repository Structure

- **main** — images, csv, bson (Task 1 initial state)
- **actualizaciones** — images new, csv, bson (Task 2 after adding songs)
- **eliminaciones** — csv, bson (Task 3 after deletions)

---

## Task 1 — Database Creation

One collection was created per artist, each with 3 documents representing their most popular songs. Each document includes title, release year, artist, genre, duration, track number, popularity description, and a reference to its cover image.

| Artist | Songs |
|---|---|
| Billie Eilish | 8, Goodbye, Wish You Were Gay |
| BTS | Spring Day, 2.0, Body to Body |
| Diomedes Diaz | Titulo de Amor, Dejala, Mi Primera Cana |
| Ivy Queen | Pólvora, Llego la Queen, Y Tú |
| Lady Gaga | Poker Face, LoveGame, Paparazzi |
| Michael Jackson | Billie Jean, Beat It, Thriller |
| Queen | Father to Son, Some Day One Day, Procession |

---

## Task 2 — Data Expansion

Three additional songs were added to each collection, selecting lesser-known tracks with fewer streams. New cover images were added to the images/ folder to match the new documents.

| Artist | New Songs Added |
|---|---|
| Billie Eilish | Bury a Friend, Xanny, My Strange Addiction |
| BTS | Begin, Awake, Reflection |
| Diomedes Diaz | Mi Muchacho, A Fuego Lento, La Distancia |
| Ivy Queen | Representa, Mi Vida Eres Tú, Pon Atención |
| Lady Gaga | Money Honey, Starstruck, I Like It Rough |
| Michael Jackson | Human Nature, Wanna Be Startin' Somethin', Baby Be Mine |
| Queen | Nevermore, Funny How Love Is, The Fairy Feller's Master-Stroke |

---

## Task 3 — Deletions

The complete **Billie Eilish** collection was dropped from the database. Additionally, at least 2 songs were deleted from each remaining collection.

| Artist | Remaining Songs |
|---|---|
| BTS | Body to Body, Begin, Awake, Reflection |
| Diomedes Diaz | Titulo de Amor, Mi Muchacho, La Distancia |
| Ivy Queen | Y Tú, Representa, Pon Atención |
| Lady Gaga | Poker Face, LoveGame, I Like It Rough |
| Michael Jackson | Billie Jean, Thriller, Baby Be Mine |
| Queen | Some Day One Day, Procession, Funny How Love Is |

---

## Document Structure

```json
{
  "_id": { "$oid": "..." },
  "titulo": "Song title",
  "año_salida": 2019,
  "autor": "Artist name",
  "id_imagen_portada": "artist_songname.jpg",
  "Género_musical": "Genre",
  "Duración": "00:03:30",
  "Número_Pista": "1",
  "Popularidad": "Popularity description."
}
```

---

## How to Replicate

**Prerequisites:** MongoDB Atlas account, MongoDB Compass, MongoDB Database Tools

**Import BSON:**
```bash
mongorestore --uri "mongodb+srv://USER:PASSWORD@your-cluster.mongodb.net" "Tarea 1/bson/"
```

**Export BSON:**
```bash
mongodump --uri "mongodb+srv://USER:PASSWORD@your-cluster.mongodb.net/Album" --out ./exportacion
```
