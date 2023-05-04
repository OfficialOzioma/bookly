# Bookly-REST-API

**Bookly** This is a RESTful API where users can search for books related to programming, IT or technology, from <https://itbook.store>. Registered user can also add books to their favourite list.

### Contents

- [Bookly-REST-API](#bookly-rest-api)
    - [Contents](#contents)
  - [Features](#features)
  - [Tech used](#tech-used)
  - [How to get the project](#how-to-get-the-project)
    - [Using Git (recommended)](#using-git-recommended)
    - [Using manual download ZIP](#using-manual-download-zip)
    - [Setting up environments](#setting-up-environments)
  - [Run the project using docker](#run-the-project-using-docker)
  - [API endpoints](#api-endpoints)
      - [*Indication*](#indication)
    - [User related](#user-related)
    - [Book related](#book-related)
- [License](#license)

## Features

- Users can create their profiles (token-based authentication)
- Users can search for books by title, author or keywords
- Users can view details of a particular book
- Users can add books to their favorite list
- Users can remove books from their favorite list
- Users can view their list of favorite books

## Tech used

**Runtime environment**

- [x] Node.js

**API for books**

- [x] [IT Book Store API](https://api.itbook.store/)

**Database**

- [x] MongoDB

**Containerized tool**

- [x] Docker

## How to get the project

### Using Git (recommended)

1. Navigate & open CLI into the directory where you want to put this project & Clone this project using this command.

```bash
git clone git@github.com:OfficialOzioma/bookly.git
```

### Using manual download ZIP

1. Download repository
2. Extract the zip file, navigate into it & copy the folder to your desired directory

### Setting up environments

1. Inside the project folder
2. You will find a file named `.env.example`
3. Rename the file to `.env` & change the values of the variables in file, this include the MONGODB_URL and DB_NAME.
4. You can also change the PORT variable to your desired port number
5. Create a database in MongoDB & name it as you like.
6. run `npm install` on the terminal to install all dependencies.
7. start the server using `npm run dev` or `npm start`
8. You can now access the API at `http://localhost:3000`

## Run the project using docker

1. To build **docker image**

    ```bash
    docker compose build --no-cache
    ```

2. To run the **containers** in detached mode (wait for a while for database connection)

    ```bash
    docker compose up -d
    ```

3. To view running **containers**

    ```bash
    docker container ps
    ```

4. To view **API logs**

    ```bash
    docker logs booksearch-api-c
    ```

5. To **run tests**, first enter within the API container
   - on windows CMD (not switching to bash)

        ```bash
        docker exec -it booksearch-api-c /bin/sh
        ```

   - on windows CMD (after switching to bash)

        ```bash
        docker exec -it booksearch-api-c //bin//sh
        ```

        or

        ```bash
        winpty docker exec -it booksearch-api-c //bin//sh
        ```

    now run **test command**

    ```bash
    npm test
    ```

6. To exit from **API container**, press <kbd>Ctrl</kbd>+<kbd>D</kbd> on terminal

7. To **stop** the containers

    ```bash
    docker compose down
    ```

## API endpoints

#### *Indication*

- [x] **Authentication required**
- [ ] **Authentication not required**

### User related

- [ ] [Resgister](docs/user/register.md): `POST localhost:3000/user/register`
- [ ] [Login](docs/user/login.md): `POST localhost:3000/user/login`
- [x] [Logout](docs/user/logout.md): `DELETE localhost:3000/user/logout`
- [x] [Refresh token](docs/user/refreshToken.md): `POST localhost:3000/user/me/tokenRefresh`
- [x] [Get loggedin user's info](docs/user/getLoggedInUserData.md): `GET localhost:3000/user/me/getLoggedInUserData`

### Book related

- [ ] [Search for books](docs/book/searchBook.md): `GET localhost:3000/book/search/:searchParams/:page`
- [ ] [Get details of a particular book](docs/book/getDetailsOfABook.md): `GET localhost:3000/book/getBookDetails/:bookId`
- [x] [Add a book to user's favourite list](docs/book/addBookToFavourite.md): `POST localhost:3000/book/addToFavourite`
- [x] [Remove a book from user's favourite list](docs/book/removeBookFromFavourite.md): `DELETE localhost:3000/book/removeFromFavourite`
- [x] [Get user's favourite book list](docs/book/getUserFavouriteBookList.md): `GET localhost:3000/book/getFavouriteBooks`

# License

[Apache License]([LICENSE](http://www.apache.org/licenses/LICENSE-2.0))
