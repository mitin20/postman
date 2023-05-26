# install
npm install

# run
node lesson1/index.js

## GET
/
curl localhost:4000                                                                                ─╯
{"status":"success"}

## GET
/products

POST
{
    "name": "TV",
    "price": "100",
    "category": "electronics"
}

## GET
/products/1
{
    "product": {
        "id": 1,
        "name": "TV",
        "price": 100,
        "category": "electronics",
        "createdAt": "2023-05-26T15:07:05.722Z",
        "updatedAt": "2023-05-26T15:07:05.722Z"
    }
}

## DELETE
/products/1

## PATCH
{
    "price": 99999
}

# run
node lesson2/index.js

## POST
/signup
{
    "email": "test@gmail.com",
    "password": "password"
}

## POST
/login
{
    "email": "test@gmail.com",
    "password": "password"
}

# Run
node lesson3/index.js

## POST
/login
body
{
    "email": "{{email}}",
    "password": "{{password}}"
}


test
var res = pm.response.json()
pm.environment.set('token', res.token)


## CODE: curl
curl --location --request POST 'localhost:4000/login' \
--header 'Content-Type: application/json' \
--header 'Cookie: connect.sid=s%3ApA_7QimXnbbX0N3O6ZE0eGQINL-saUe4.PI8vGmwj6h6Alapj47YOGQgAa9Fv%2F89LplkbfnoPjDE' \
--data-raw '{
    "email": "test@gmail.com",
    "password": "password"
}' |jq

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6InRlc3RAZ21haWwuY29tIiwiaWF0IjoxNjg1MTIwODA4LCJleHAiOjE2ODUxMjQ0MDh9.3sKGvMWyqOpBC57yBdI6_Dc09kyGonlkdb68iODp0zA"
}