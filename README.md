# library-management
API that manages library.

## Description
This is the documentation for the Library API, version 1.0.0. The API provides endpoints to manage books and authors in a library system.

## Base URL
https://library.com

## Endpoints

### /books

#### GET
- Summary: Get all books
- Description: Retrieve all books, ordered by their last update date. Optionally, you can filter the books by name or within a specific date range.
- Operation ID: getBooks
- Parameters:
  - `bookName` (query parameter): Filter return books by the given name (optional).
  - `startDate` (query parameter): Filter books with release dates after this date (optional, date format).
  - `endDate` (query parameter): Filter books with release dates before this date (optional, date format).

#### PUT
- Summary: Create or update a list of books
- Operation ID: crupdateBooks
- Request Body: Expects an array of book objects in JSON format.

### /authors

#### GET
- Summary: Get author by name
- Description: Retrieve authors filtered by name.
- Operation ID: getAuthor
- Parameters:
  - `AuthorName` (query parameter): Filter return authors by the given name (optional).

#### PUT
- Summary: Create or update an author
- Operation ID: crupdateAuthor
- Request Body: Expects an array of author objects in JSON format.

#### DELETE
- Summary: Delete an author
- Description: Delete an author by their ID.
- Operation ID: deleteAuthor
- Parameters:
  - `authorId` (query parameter): ID of the author to delete (required).

## Schemas

### Book
- `id` (string)
- `bookName` (string)
- `author` (object): Author details associated with the book.
- `pageNumbers` (integer)
- `topic` (string): Can be one of: ROMANCE, COMEDY, OTHER.
- `releaseDate` (string, date format)

### Author
- `id` (string)
- `name` (string)
- `sex` (string): Can be either 'M' or 'F'.


