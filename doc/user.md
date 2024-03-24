# user API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
  "username": "Khannedy",
  "password": "Rahasia",
  "name": "Eko Khannedy"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "Khannedy".
    "name": "Eko Khannedy",
  }
}
```

Response Body (Failed) :

```json
{
  "data": {
    "errors": "Username already registered"
  }
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "Khannedy",
  "password": "Rahasia"
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "Khannedy",
    "name": "Eko Khannedy",
    "token": "session_id_generated"
  }
}
```

Response Body (Failed) :

```json
{
  "data": {
    "errors": "Unauthorized"
  }
}
```

## Get User

Endpoint : GET /api/users/current

Headers :

- Authorization: token

Response Body (Success) :

```json
{
  "data": {
    "username": "Khannedy",
    "name": "Eko Khannedy"
  }
}
```

Response Body (Failed) :

```json
{
  "data": {
    "errors": "Username already registered"
  }
}
```

## Update User

Endpoint : PATCH /api/users/current

Headers :

- Authorization: token

Request Body :

```json
{
  "password": "Rahasia", // optional, if want to change
  "name": "Eko Khannedy" // optional, if want to change
}
```

Response Body (Success) :

```json
{
  "data": {
    "username": "Khannedy".
    "name": "Eko Khannedy",
  }
}
```

## Logout User

Endpoint : DELETE /api/users/current

Headers :

- Authorization: token

Response Body (Success) :

```json
{
  "data": true
}
```
