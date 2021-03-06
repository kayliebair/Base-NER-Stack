# API Servers



## Overview

TODO: the backend



## TODO: MVP API Endpoints

##### Companies - [http://localhost:3001](http://localhost:3001)

| Endpoint                       | HTTP Method | CRUD Method | Result                                             |
| ------------------------------ | ----------- | ----------- | -------------------------------------------------- |
| /companies/ping                | GET         | READ        | `pong` - Sanity Check                              |
| /companies                     | GET         | READ        | Get all companies' info                            |
| /companies                     | POST        | CREATE      | Add a company                                      |
| /companies                     | PUT         | UPDATE      | Update company info                                |
| /companies                     | DELETE      | DELETE      | Delete a company                                   |
| /companies/<company_id>        | GET         | READ        | Get company info by `ID`                           |
| /companies/<company_id>/events | GET         | READ        | Get all `events` associated with a given `company` |
| /companies/<company_id>/users  | GET         | READ        | Get all `users` interested in a given `company`    |
| /companies/search?term=        | GET         | READ        | Get all companies containing `term` substring      |
| /companies/filter?position=    | GET         | READ        | Get all companies hiring a specific `position`     |
| /companies/filter?major=       | GET         | READ        | Get all companies hiring a specific `major`        |
| TODO                           |             |             |                                                    |

##### Events - [http://localhost:3002](http://localhost:3002)

| Endpoint                     | HTTP Method | CRUD Method | Result                                                       |
| ---------------------------- | ----------- | ----------- | ------------------------------------------------------------ |
| /events/ping                 | GET         | READ        | `pong` - Sanity Check                                        |
| /events                      | GET         | READ        | Get all events                                               |
| /events                      | POST        | CREATE      | Add a single event                                           |
| /events                      | PUT         | UPDATE      | Update a single event                                        |
| /events                      | DELETE      | DELETE      | Delete a single event                                        |
| /events/register             | POST        | CREATE      | Register a user for an event                                 |
| /events/register             | PUT         | UPDATE      | Update user registration for an event                        |
| /events/checkin              | POST        | CREATE      | Check in a user for an event                                 |
| /events/<event_id>           | GET         | READ        | Get event by `ID`                                            |
| /events/<event_id>/users     | GET         | READ        | Get all `users` attending a given `event`                    |
| /events/<event_id>/companies | GET         | READ        | Get all `companies` for a given `event`                      |
| /events/<event_id>?company=  | GET         | READ        | Get all users interested in a given `company` for a given `event` |
| /events/search?term=         | GET         | READ        | Get all events containing `term` substring                   |
| /events/filter?date=         | GET         | READ        | Get all events on a given `date`                             |
| TODO                         |             |             |                                                              |

##### Users - [http://localhost:3003](http://localhost:3003)

| Endpoint                   | HTTP Method | CRUD Method | Result                                                   |
| -------------------------- | ----------- | ----------- | -------------------------------------------------------- |
| /users/ping                | GET         | READ        | `pong` - Sanity Check                                    |
| /users                     | GET         | READ        | Get all users' info                                      |
| /users/register            | POST        | CREATE      | Add a user                                               |
| /users/login               | POST        | CREATE      | Log in a user                                            |
| /users/update              | PUT         | UPDATE      | Update user info                                         |
| /users/<user_id>           | GET         | READ        | Get user info by ID                                      |
| /users/<user_id>/companies | GET         | READ        | Get all `companies` a `user` is interested in            |
| /users/<user_id>/events    | GET         | READ        | Get all `events` a `user` is interested in               |
| /users/search?name=        | GET         | READ        | Get all users whose names contain the substring `name`   |
| /users/search?email=       | GET         | READ        | Get all users whose emails contain the substring `email` |
| /users/filter?year=        | GET         | READ        | Get all students of the given `year`                     |
| /users/filter?major=       | GET         | READ        | Get all students of the given `major`                    |
| /users/filter?position=    | GET         | READ        | Get all students seeking the given `position`            |
| TODO                       |             |             |                                                          |



## TODO: Potential Endpoints

##### Events - [http://localhost:3002](http://localhost:3002)

| Endpoint                   | HTTP Method | CRUD Method | Result                                                     |
| -------------------------- | ----------- | ----------- | ---------------------------------------------------------- |
| /events/<event_id>?paid=   | GET         | READ        | Get all users who have `paid`/not paid for a given `event` |
| /events/filter?committee=  | GET         | READ        | Get all events run by given SWE `committee`                |
| /events/filter?popular=    | GET         | READ        | Get all popular events                                     |
| /events/filter?month=      | GET         | READ        | Get all events in a given `month`                          |
| /events/filter?year=       | GET         | READ        | Get all events in a given calendar `year`                  |
| /events/filter?quarter=    | GET         | READ        | Get all events in a given academic `quarter`               |
| /events/filter?start_date= | GET         | READ        | Get all events starting on or after given `start_date`     |
| /events/filter?end_date=   | GET         | READ        | Get all events starting before given `end_date`            |
| TODO                       |             |             |                                                            |

##### Users - [http://localhost:3003](http://localhost:3003)

| Endpoint                  | HTTP Method | CRUD Method | Result                                                       |
| ------------------------- | ----------- | ----------- | ------------------------------------------------------------ |
| /events/filter?past=      | GET         | READ        | Get all past events                                          |
| /users/filter?ucla=       | GET         | READ        | Get all UCLA-affiliated users                                |
| /users/filter?profession= | GET         | READ        | Get all users that are students, professors, company representatives, etc. |
| /users/filter?graduating= | GET         | READ        | Get all students that are `graduating` or not                |
| /users/<user_id>/favorite | GET         | READ        | Get a user's favorite events by ID                           |
| /users/<user_id>/favorite | POST        | CREATE      | Add a favorite event to a user by ID                         |
| /users/<user_id>/favorite | DELETE      | DELETE      | Delete a favorite event from a user by ID                    |
| /users/<user_id>/past     | GET         | READ        | Get a user's past events by ID                               |
| /users/<user_id>/past     | POST        | CREATE      | Add a past event to a user by ID                             |
| /users/<user_id>/past     | DELETE      | DELETE      | Delete a past event from a user by ID                        |
| TODO                      |             |             |                                                              |



## Local Development

- Instead of running the full stack, we can develop each server locally.
- Navigate to either `server/companies/`, `server/events/`, or `server/users/`, and install the necessary dependencies:

```bash
$ yarn install
```

- Start the app:

```bash
$ yarn start
```

- View the app at [http://localhost:3000](http://localhost:3000) in a browser.
- Exit the app in terminal with `Ctrl+C`



## Testing in Local Development

TODO:  [Mocha](https://mochajs.org/)? `yarn test`



## Standalone Docker

- Rather than running the full stack from root, we can run each service separately
- From either `server/companies/`, `server/events/`, or `server/users/`:

```bash
$ docker build -t companies-server .
$ docker run --rm --publish 3001:3000 companies-server
```

```bash
$ docker build -t events-server .
$ docker run --rm --publish 3002:3000 events-server
```

```bash
$ docker build -t users-server .
$ docker run --rm --publish 3003:3000 users-server
```

- View the server in a browser at the corresponding port:
  - `companies-server` in `server/companies/` is available at [http://localhost:3001](http://localhost:3001) 
  - `events-server` in `server/events/` is available at [http://localhost:3002](http://localhost:3002) 
  - `users-server` in `server/users/` is available at [http://localhost:3003](http://localhost:3003) 
- Remove the image once finished:

```bash
$ docker rmi companies-server
```
```bash
$ docker rmi events-server
```
```bash
$ docker rmi users-server
```