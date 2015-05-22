# API Endpoints

## List Terms

Lists terms with academic calendar information. By default returns all four quarters in the current academic year.

    GET /terms

### Parameters

- in: YYYY format that returns all terms in the academic year
- since: ISO-8601 formatted date
- until: ISO-8601 formatted date

### Response

<insert json>

## Get a single Term

Get a term from its id. Contains the special endpoints (current, prev, next) for frequently accessed terms.

    GET /terms/:term_id
    GET /terms/current
    GET /terms/prev
    GET /terms/next

### Response

<insert json>

## List Courses

List all currently active courses.

    GET /courses

List all courses offered in a specific term.

    GET /terms/:term_id/courses

### Response

<insert json>

## Get a single Course

Get a course from its id.

    GET /courses/:course_id

### Response

Data element will be an item of the form
<insert json>

## List Instructors

List all active instructors

    GET /instructors

List all instructors who have taught or a scheduled to teach a specific course.

    GET /courses/:course_id/instructors

### Response

Data element will be a Collection with items of the following form:

```json
{
    "id": unique identifier
    "first_name": "Gad”
    "middle_name": ""
    "last_name": "Allon",
    "homepage": ""
    "img_url": ""
}
```

## Get a single Instructor

Get an instructor from their id.

    GET instructors/:instructor_id

### Response

Data element will be an Item of the form:

```json
{
    "id": unique identifier
    "first_name": "Gad”
    "middle_name": ""
    "last_name": "Allon",
    "homepage": ""
    "img_url": ""
}
```

### List Sections

    GET /sections
    GET /terms/:term_id/sections
    GET /courses/course_id/sections
    GET /instructors/:instructor_id/sections

### Response

<insert json>

### Get a single Section

Get a section from its id.

    GET /sections/:section_id

### Response

<insert json>

