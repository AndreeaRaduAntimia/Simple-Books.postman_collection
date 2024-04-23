Simple Books API
This API allows you to reserve a book.

The API is available at https://simple-books-api.glitch.me

1. Endpoints
Status
GET /status

Returns the status of the API.

2. List of books
GET /AllBooks

Returns a list of books.

3. List of FictionBooks

Optional query parameters:

type: fiction
limit: 3
Get a FictionBooks
GET /books?type=fiction&limit=3

Retrieve detailed information about all the books with type "fiction" and limit 3

4. List of NonFictionBooks

Optional query parameters:

type: non-fiction
limit: 3
Get a NonFictionBooks
GET /books?type=non-fiction&limit=3

Retrieve detailed information about all the books with type "non-fiction" and limit 3

5. Authentication
POST /api-clients/
{
   "clientName": "Exemple",
   "clientEmail": "exemple@yahoo.com"
}

The response body will contain the access Token

6. Submit an order
POST /orders

Allows you to submit a new order. Requires authentication.

The request body needs to be in JSON format and include the following properties:

bookId - Integer - Required
customerName - String - Required


7. Update an order
PATCH /orders/:orderId

Update an existing order. Requires authentication.

The request body needs to be in JSON format and allows you to update the following properties:

customerName - String

8. Delete an order
DELETE /orders/:orderId

Delete an existing order. Requires authentication.

The request body needs to be empty.

The response body will contain the access token. The access token is valid for 7 days.

Possible errors

Status code 409 - "API client already registered." Try changing the values for clientEmail and clientName to something else.
