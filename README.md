# Notes-MicroProject-Backend
# Simple Notes API

A basic Notes API built with Express.js that allows you to add, retrieve, update, and delete notes. This API was tested using Postman as a frontend.

## Features

- **Create Note**: Add new notes to the collection.
- **Get All Notes**: Retrieve all stored notes.
- **Delete Note**: Remove a note by its index.
- **Update Note**: Modify an existing note's title by its index.

## Technologies Used

- **Node.js**: JavaScript runtime environment.
- **Express.js**: Fast, unopinionated, minimalist web framework for Node.js.

## Setup and Installation

To get this API running on your local machine, follow these steps:

1.  **Clone the repository**:

    ```bash
    git clone <your-repository-url>
    cd simple-notes-api
    ```

2.  **Install dependencies**:
    Make sure you have Node.js and npm installed.

    ```bash
    npm install express
    ```

3.  **Run the application**:

    ```bash
    node app.js
    ```

    The server will start on `http://localhost:3000`.

## API Endpoints

The API exposes the following endpoints:

### 1. Create a Note

-   **URL**: `/notes`
-   **Method**: `POST`
-   **Body**:
    ```json
    {
        "title": "My first note",
        "content": "This is the content of my first note."
    }
    ```
-   **Success Response**:
    -   **Code**: `200 OK`
    -   **Content**:
        ```json
        {
            "message": "Note added successfully",
            "notes": [
                {
                    "title": "My first note",
                    "content": "This is the content of my first note."
                }
            ]
        }
        ```

### 2. Get All Notes

-   **URL**: `/notes`
-   **Method**: `GET`
-   **Success Response**:
    -   **Code**: `200 OK`
    -   **Content**:
        ```json
        [
            {
                "title": "My first note",
                "content": "This is the content of my first note."
            },
            {
                "title": "Another note",
                "content": "Some more content here."
            }
        ]
        ```

### 3. Delete a Note

-   **URL**: `/notes/:index`
-   **Method**: `DELETE`
-   **URL Params**:
    -   `index`: The array index of the note to delete (e.g., `0`, `1`, etc.).
-   **Success Response**:
    -   **Code**: `200 OK`
    -   **Content**:
        ```json
        {
            "message": "note deleted successfully"
        }
        ```

### 4. Update a Note

-   **URL**: `/notes/:index`
-   **Method**: `PATCH`
-   **URL Params**:
    -   `index`: The array index of the note to update.
-   **Body**:
    ```json
    {
        "title": "Updated note title"
    }
    ```
-   **Success Response**:
    -   **Code**: `200 OK`
    -   **Content**:
        ```json
        {
            "message": "note updated successfully"
        }
        ```

## Testing with Postman

You can use Postman to test these API endpoints.

### Example: Creating a Note

1.  Open Postman.
2.  Set the request type to `POST`.
3.  Enter the URL: `http://localhost:3000/notes`.
4.  Go to the "Body" tab, select "raw", and choose "JSON (application/json)".
5.  Enter the JSON body:
    ```json
    {
        "title": "My new note",
        "content": "This is a note I'm creating via Postman."
    }
    ```
6.  Click "Send".

### Example: Getting All Notes

1.  Open Postman.
2.  Set the request type to `GET`.
3.  Enter the URL: `http://localhost:3000/notes`.
4.  Click "Send".

