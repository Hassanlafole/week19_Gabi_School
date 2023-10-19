# Render Link 
https://gabi-readme-deploy.onrender.com

MainRoute : `/api/owner`

# Owner Sign Up

Endpoint: `/signup`

Method: `POST`

Creates a new owner account.

#### Request Body

| Parameter | Type   | Description     |
|-----------|--------|-----------------|
| name      | string | Owner's name    |
| email     | string | Owner's email   |
| password  | string | Owner's password|

#### Response

##### Success Response

Status Code: `201 Created`

```json
{
  "message": "Owner created successfully",
  "owner": {
    "name": "John Doe",
    "email": "johndoe@example.com"
  }
}
```

##### Error Responses

Status Code: `409 Conflict`

```json
{
  "message": "Owner already exists"
}
```

Status Code: `500 Internal Server Error`

```json
{
  "message": "Something went wrong",
  "error": "Internal server error message"
}
```

# Owner Login

Endpoint: `/login`

Method: `POST`

Logs in an existing owner.

#### Request Body

| Parameter | Type   | Description     |
|-----------|--------|-----------------|
| email     | string | Owner's email   |
| password  | string | Owner's password|

#### Response

##### Success Response

Status Code: `200 OK`

```json
{
  "message": "Owner logged in successfully",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJqb2huZG9lQGV4YW1wbGUuY29tIiwiaWF0IjoxNTE2MjM5MDIyfQ.2iG2X1Eo1kV9EiKQ2Xy6Y1WtMXUJN9o1w-PmTmzBv0Q"
}
```

##### Error Responses

Status Code: `404 Not Found`

```json
{
  "message": "Owner not found"
}
```

Status Code: `401 Unauthorized`

```json
{
  "message": "Invalid credentials"
}
```

Status Code: `500 Internal Server Error`

```json
{
  "message": "Something went wrong",
  "error": "Internal server error message"
}
```


## Author Routes Documentation

### Get All Authors

- Method: GET
- Endpoint: `/authors`
- Authentication: Required

Retrieves a list of all authors.

#### Request

```http
GET /authors
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON array containing all authors"
}
```

#### Error Response

If no authors are found:

```json
Status: 404 Not Found
{
  "error": "No authors found"
}
```

### Get Single Author

- Method: GET
- Endpoint: `/authors/:id`
- Authentication: Required

Retrieves a single author by their ID.

#### Request

```http
GET /authors/1
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON object representing the author"
}
```

#### Error Response

If the author is not found:

```json
Status: 404 Not Found
{
  "message": "Author not found"
}
```

### Add Author

- Method: POST
- Endpoint: `/authors`
- Authentication: Required

Adds a new author.

#### Request

```http
POST /authors
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john.doe@example.com"
}
```

#### Response

```json
Status: 201 Created
{
  "message": "JSON object with a message property set to New Author created successfully and a createAuthor property containing the details of the created Author"
}
```

#### Error Response

If adding the author fails:

```json
Status: 500 Internal Server Error
{
  "message": "Failed to add Author"
}
```

### Update Author

- Method: PUT
- Endpoint: `/authors/:id`
- Authentication: Required

Updates an existing author.

#### Request

```http
PUT /authors/1
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON object with a message property set to author updated successfully and an updateAuthors property containing the details of the updated Author",

}
```
```

#### Error Response

If the author is not found:

```json
Status: 404 Not Found
{
  "message": "Author not found"
}
```

### Delete Author

- Method: DELETE
- Endpoint: `/authors/:id`
- Authentication: Required

Deletes an author.

#### Request

```http
DELETE /authors/1
```

#### Response

```json
Status: 200 OK
{
  "message": "Author deleted"
}
```

#### Error Response

If the author is not found:

```json
Status: 404 Not Found
{
  "message": "Author not found"
}
```

If deleting the author fails:

```json
Status: 500 Internal Server Error
{
  "message": "Failed to delete Author"
}
```


## Bookstore Routes Documentation

### Get All Bookstores

- Method: GET
- Endpoint: `/bookstores`
- Authentication: Required

Retrieves a list of all bookstores.

#### Request

```http
GET /bookstores
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON array containing all Bookstores"
}
```

#### Error Response

If no bookstores are found:

```json
Status: 404 Not Found
{
  "message": "Bookstores not found"
}
```

### Get Single Bookstore

- Method: GET
- Endpoint: `/bookstores/:id`
- Authentication: Required

Retrieves a single bookstore by its ID.

#### Request

```http
GET /bookstores/1
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON object representing the Bookstore"
}
```

#### Error Response

If the bookstore is not found:

```json
Status: 404 Not Found
{
  "message": "Bookstore not found"
}
```

### Add Bookstore

- Method: POST
- Endpoint: `/bookstores`
- Authentication: Required

Adds a new bookstore.

#### Request

```http
POST /bookstores
Content-Type: application/json

{
  "name": "Bookstore 3",
  "location": "Location 3"
}
```

#### Response

```json
Status: 201 Created
{
  "message": "JSON object with a message property set to New Bookstore created successfully and a createBookstore property containing the details of the created Bookstore"
}
```

#### Error Response

If adding the bookstore fails:

```json
Status: 500 Internal Server Error
{
  "message": "Failed to add bookstore"
}
```

### Update Bookstore

- Method: PUT
- Endpoint: `/bookstores/:id`
- Authentication: Required

Updates an existing bookstore.

#### Request

```http
PUT /bookstores/1
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON object with a message property set to bookstore updated successfully and an updatebookstore property containing the details of the updated bookstore",

}
```

#### Error Response

If the bookstore is not found:

```json
Status: 404 Not Found
{
  "message": "Bookstore not found"
}
```

### Delete Bookstore

- Method: DELETE
- Endpoint: `/bookstores/:id`
- Authentication: Required

Deletes a bookstore.

#### Request

```http
DELETE /bookstores/1
```

#### Response

```json
Status: 200 OK
{
  "message": "Bookstore deleted"
}
```

#### Error Response

If the bookstore is not found:

```json
Status: 404 Not Found
{
  "message": "Bookstore not found"
}
```

If deleting the bookstore fails:

```json
Status: 500 Internal Server Error
{
  "message": "Failed to delete bookstore"
}
```

## Book Routes Documentation

This documentation provides a summary of the routes available for managing books in an application. The routes are implemented using Express.js and Prisma ORM.

### Get All Books

- Method: GET
- Endpoint: `/books`
- Authentication: Required

Retrieves a list of all books.

#### Request

```http
GET /books
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON array containing all books"
}
```

#### Error Response

If no books are found:

```json
Status: 404 Not Found
{
  "message": "Books not found"
}
```

### Get Single Book

- Method: GET
- Endpoint: `/books/:id`
- Authentication: Required

Retrieves a single book by its ID.

#### Request

```http
GET /books/1
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON object representing the book"
}
```

#### Error Response

If the book is not found:

```json
Status: 404 Not Found
{
  "message": "Book not found"
}
```

### Add Book

- Method: POST
- Endpoint: `/books`
- Authentication: Required

Adds a new book.

#### Request

```http
POST /books
```

#### Response

```json
Status: 201 Created
{
  "message": "JSON object with a message property set to New Book created successfully and a createBook property containing the details of the created book"
}
```

#### Error Response

If adding the book fails:

```json
Status: 500 Internal Server Error
{
  "message": "Failed to add book"
}
```

### Update Book

- Method: PUT
- Endpoint: `/books/:id`
- Authentication: Required

Updates an existing book.

#### Request

```http
PUT /books/1
```

#### Response

```json
Status: 200 OK
{
  "message": "JSON object with a message property set to Book updated successfully and an updateBook property containing the details of the updated book",

}
```

#### Error Response

If the book is not found:

```json
Status: 404 Not Found
{
  "message": "Book not found"
}
```

### Delete Book

- Method: DELETE
- Endpoint: `/books/:id`
- Authentication: Required

Deletes a book.

#### Request

```http
DELETE /books/1
```

#### Response

```json
Status: 200 OK
{
  "message": "Book deleted"
}
```

#### Error Response

If the book is not found:

```json
Status: 404 Not Found
{
  "message": "Book not found"
}
```

If deleting the book fails:

Status: `500 Internal Server Error`
```json
{
  "message": "Failed to delete book"
}
```
