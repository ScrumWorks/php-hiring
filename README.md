# Amateri PHP hiring backend
Create simple backend service that shows logged-in users list of albums

## Content
The service should contain functionality for
* login with name/password
* list of albums for logged-in users only with simple filter

Backend has to be written in PHP. Other than that, you can use any frameworks or libraries you like. 
For faster server testing/running Dockerfile with docker-compose.yml specification is also preferred.

### Login
User logs in using the `POST api/login` endpoint. 
- takes json body payload with `username` and `password` and returns some response with authorization token.

User authorization process can be anything you prefer.

Test curl:
```
curl --include --location --request POST 'http://localhost/api/login' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{ "username": "", "password": "" }'
```

You don't need to create registration process of the user. User can be hardcoded it in any way at the startup of the server.

### Albums
Albums can be listed using `GET api/albums` endpoint. 

- accessible only for logged-in users
- returns list of album entities in JSON format.
  - Album entity should contain attributes: `id`, `title`, `description`, `images`, 
    - `id` is unique id of the album, 
    - `ownerId` id of the user that created the album
    - `title` and `description` are strings and 
    - `images` array of image urls
- filter query parameter `filterByOwnerId`, filters returned list by `ownerId`

Albums can be initialized using hardcoded or random data during server startup.

##### Optional
Implement `POST api/albums` endpoint that adds new album to the storage. Added albums can be listed using `GET api/albums`

## Submitting your work
- must be git repository
- instructions how to run the server are required
- instructions for login authorization and album endpoints and how to test them are also required.
