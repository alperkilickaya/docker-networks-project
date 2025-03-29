# Star Wars Favorites API

A simple REST API that allows users to save their favorite Star Wars movies and characters. The application uses MongoDB for data persistence and communicates with the Star Wars API (SWAPI).

## Features

- Save favorite Star Wars movies and characters
- List all saved favorites
- Fetch movies from SWAPI
- Fetch characters from SWAPI

## Docker Network Setup

This project uses Docker networking to connect the application with MongoDB. Here's how to set it up:

1. Create a Docker network:

```bash
docker network create favorites-net
```

2. Build and run the application container:

```bash
docker build -t favorites-node .
docker run --name favorites --network favorites-net -d --rm -p 3000:3000 favorites-node
```

3. Run MongoDB container:

```bash
docker run -d --name mongodb --network favorites-net mongo
```

The application will connect to MongoDB using the container name as the hostname: `mongodb://mongodb:27017/swfavorites`

## API Endpoints

- `GET /favorites` - List all saved favorites
- `POST /favorites` - Save a new favorite
- `GET /movies` - Fetch movies from SWAPI
- `GET /people` - Fetch characters from SWAPI

## Dependencies

- Express.js
- MongoDB
- Mongoose
- Axios
- Body Parser

## Environment Variables

No environment variables are required for this project.
