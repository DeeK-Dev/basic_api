
# MySQL & API's

This is a Node.js project that provides endpoints for managing courses, enrolments, and users in a collage relational database system

## Installation

To install this project, follow these steps:

- Clone this repository to your local machine.
- Navigate to the root directory of the project in your terminal.
- Run npm install to install the required dependencies.

## Usage

To start the server, run the command ```node server.js``` in the root directory of the project.

The server will listen on port 3000 by default.

## Endpoints

### GET /view/courses
This endpoint returns a list of all courses in the database.

### GET /view/users
This endpoint returns a list of all users in the database.

### GET /view/enrolments
This endpoint returns a list of all enrolments in the database.

### GET /view/roles
This endpoint returns a list of all roles in the database.

### POST /course/:courseID/availability
This endpoint allows an admin to enable or disable a course. To use this endpoint, include the following elements in the request body:

- **userID**: *(integer)* the ID of the user making the request (required)
- **isAvailable**: *(boolean)* a boolean value indicating whether the course should be enabled (true) or disabled (false).
### POST /course/:courseID/teacher
This endpoint allows an admin to assign a teacher to a course. To use this endpoint, include the following elements in the request body:

- **userID**: *(integer)* the ID of the user making the request (required, must be Admin)
- **teacherID**: *(integer)* the ID of the teacher to be assigned to the course (required)
### GET /courses
This endpoint returns a list of all courses that are set to available. To use this endpoint, include the following element in the request body:

- **userID**: *(integer)* the ID of the user making the request (required)
  ###POST /course/:courseID/enroll
  This endpoint allows a student to enroll in a course. To use this endpoint, include the following elements in the request body:

- **userID**: *(integer)* the ID of the student who is enrolling in the course (required)
- **courseID**: *(integer)* the ID of the course in which to enroll (required)
### POST /enrollment/:enrollmentID/grade
This endpoint allows a teacher to pass or fail a student. To use this endpoint, include the following elements in the request body:

- **pass**: (boolean) a boolean value indicating whether the student has passed (true) or failed (false). This element is optional; if not provided, the student's mark will not be changed.
- **userID**: *(integer)* the ID of the teacher making the request (required)