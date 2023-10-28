# Exercise Tracker - User Documentation
### Overview:
- [Description](#description)
- [Response](#response)
- [Routes](#routes)
- [Visit Site](https://obn-excercise-tracker.onrender.com/)


## Description
The Exercise Tracker project is an API-based online application that allows users to enter their workouts and measure their fitness improvement. This project offers user creation, exercise logging, and exercise log retrieval functions.

## Response
Your response should have the following structure.

Excercise: 
```json
  {
    username: "user_one",
    description: "user_one_description",
    duration: 60,
    date: "Mon Jan 01 1990",
    _id: "5fb5853f734231456cc54d05"
  }
```

User:
```json
{
  username: "user_one",
  _id: "5fb5853f734231456cc54d05"
}
```
Logs:
```json
{
  username: "user_one",
  count: 1,
  _id: "5fb5853f734231456cc54d05",
  log: [{
    description: "user_one_description",
    duration: 60,
    date: "Mon Jan 01 1990",
  }]
}
```

## Routes

* You can POST to /api/users with form data username to create a new user.
* The returned response from POST /api/users with form data username will be an object with username and _id properties.
* You can make a GET request to /api/users to get a list of all users.
* The GET request to /api/users returns an array.
* Each element in the array returned from GET /api/users is an object literal containing a user's username and _id.
* You can POST to /api/users/:_id/exercises with form data description, duration, and optionally date. If no date is supplied, the current date will be used.
* The response returned from POST /api/users/:_id/exercises will be the user object with the exercise fields added.
* You can make a GET request to /api/users/:_id/logs to retrieve a full exercise log of any user.
* A request to a user's log GET /api/users/:_id/logs returns a user object with a count property representing the number of exercises that belong to that user.
* A GET request to /api/users/:_id/logs will return the user object with a log array of all the exercises added.
* Each item in the log array that is returned from GET /api/users/:_id/logs is an object that should have a description, duration, and date properties.
* The description property of any object in the log array that is returned from GET /api/users/:_id/logs should be a string.
* The duration property of any object in the log array that is returned from GET /api/users/:_id/logs should be a number.
* The date property of any object in the log array that is returned from GET /api/users/:_id/logs should be a string. Use the dateString format of the Date API.
* You can add from, to and limit parameters to a GET /api/users/:_id/logs request to retrieve part of the log of any user. from and to are dates in yyyy-mm-dd format. limit is an integer of how many logs to send back.

