# Welcome to Flights Service

## Project Setup

- Clone the project on your local machine
- Execute `npm install` on the same path as of your root directory of the downloadedd project
- Create a `.env` file in the root directory and add the following environment variable
  - `PORT=3000`
- Inside the `src/config` folder create a new file `config.json` and then add the following piece of json

```
{
  "development": {
    "username": "<YOUR_DB_LOGIN_NAME>",
    "password": "<YOUR_DB_PASSWD>",
    "database": "Flights_Search_DB_DEV",
    "host": "127.0.0.1",
    "dialect": "mysql"
  }
}
```

- Once you've added your db config as listed above, go to the src folder from your terminal and execute `npx sequelize db:create`
  and then execute
  `npx sequlize db:migrate`

## DB Design

Airplane Table

- id
- model_number
- capacity

Airport Table

- id
- Name
- City_id
- address

Flights Table

- id
- departure_city_id
- destination_city_id
- airplane_id
- departure
- arrival
- Flight_number
- Airport_id

City

- id
- name

- A flight belongs to an airplane but one airplane can be used in multiple flights
- A cith has many airports but one airport belongs to a city
- One airport can have many flights, but a flight belongs to one airport

## Tables

### City -> id, name, created_At, updated_At

### Airport -> id, name, address, city_id, created_at, updated_at

    Relationship -> City has many airports and Airports belongs to a city (one to many)
