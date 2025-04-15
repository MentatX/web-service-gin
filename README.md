# Web Service with Gin Framework

This is a simple web service built using the [Gin](https://gin-gonic.com/) framework in Go. The service provides a RESTful API for managing a collection of music albums.

## Features

- **GET /albums**: Retrieve a list of all albums.
- **GET /albums/:id**: Retrieve a specific album by its ID.
- **POST /albums**: Add a new album to the collection.
- **DELETE /albums/:id**: Delete an album by its ID.

## Project Structure

- `main.go`: The main application file containing all routes and logic.

## Prerequisites

- Go 1.18 or later installed on your system.
- [Gin framework](https://github.com/gin-gonic/gin) installed.

## Running the Application

1. Clone the repository:
   ```bash
   git clone https://github.com/MentatX/web-service-gin.git
   cd web-service-gin
   ```

2. Run the application:
   ```bash
   go run main.go
   ```

3. The server will start at `http://localhost:8080`.

## API Endpoints

### 1. Get All Albums
- **Endpoint**: `GET /albums`
- **Sample with curl**:
  ```bash
  curl -X GET http://localhost:8080/albums
  ```
- **Response**:
  ```json
  [
    {"id": "1", "title": "Blue Train", "artist": "John Coltrane", "price": 56.99},
    {"id": "2", "title": "Jeru", "artist": "Gerry Mulligan", "price": 17.99},
    {"id": "3", "title": "Sarah Vaughan and Clifford Brown", "artist": "Sarah Vaughan", "price": 39.99}
  ]
  ```

### 2. Get Album by ID
- **Endpoint**: `GET /albums/:id`
- **Sample with curl**:
  ```bash
  curl -X GET http://localhost:8080/albums/1
  ```
- **Response**:
  ```json
  {"id": "1", "title": "Blue Train", "artist": "John Coltrane", "price": 56.99}
  ```

### 3. Add a New Album
- **Endpoint**: `POST /albums`
- **Sample with curl**:
  ```bash
  curl -X POST http://localhost:8080/albums \
  -H "Content-Type: application/json" \
  -d '{"id": "4", "title": "Kind of Blue", "artist": "Miles Davis", "price": 45.99}'
  ```
- **Response**:
  ```json
  {
    "id": "4",
    "title": "Kind of Blue",
    "artist": "Miles Davis",
    "price": 45.99
  }
  ```

### 4. Delete an Album
- **Endpoint**: `DELETE /albums/:id`
- **Sample with curl**:
  ```bash
  curl -X DELETE http://localhost:8080/albums/1
  ```
- **Response** (if successful):
  ```json
  {"message": "album deleted"}
  ```
- **Response** (if not found):
  ```json
  {"message": "album not found"}
  ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
