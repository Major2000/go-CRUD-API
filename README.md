# Movie Store CRUD API

This is a simple CRUD (create, read, update, delete) API for a movie store. It allows you to create, view, update, and delete movies in the store.

## Dependencies

- [Gorilla Mux](https://github.com/gorilla/mux) : A router and dispatcher for building HTTP services in Go.

## Running the program

To run the program, clone the repository and install the dependencies:

```
go get github.com/gorilla/mux
```

Then, build and run the program:

```
go build
./movie-store-crud-api
```

The API will be listening on port 8000.

## API endpoints

The following endpoints are available:

- `GET /movies` : returns a list of all movies in the store

- `GET /movies/{id}` : returns a single movie with the specified ID

- `POST /movies` : creates a new movie based on the data sent in the request body

- `PUT /movies/{id}` : updates an existing movie with the specified ID based on the data sent in the request body

- `DELETE /movies/{id}` : deletes the movie with the specified ID from the store

Each movie has the following fields:

- `ID` : a unique ID for the movie
- `Isbn` : the ISBN for the movie
- `Title` : the title of the movie
- `Director` : the director of the movie (first name and last name)

## Example usage

Here is an example of how to use the API using [curl](https://curl.se/):

```
# Add a new movie
$ curl -X POST -H "Content-Type: application/json" -d '{"isbn":"448743","title":"Movie 1","director":{"firstname":"Director","lastname":"One"}}' http://localhost:8000/movies

# Get a list of all movies
$ curl http://localhost:8000/movies

# Get a single movie
$ curl http://localhost:8000/movies/1

# Update a movie
$ curl -X PUT -H "Content-Type: application/json" -d '{"isbn":"448744","title":"Updated Movie 1","director":{"firstname":"Director","lastname":"One"}}' http://localhost:8000/movies/1

# Delete a movie
$ curl -X DELETE http://localhost:8000/movies/1
```

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/Major2000/go-CRUD-API/blob/main/LICENSE) file for details.
