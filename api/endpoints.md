# API Endpoints

## List Terms

Lists terms with academic calendar information. By default returns all four quarters in the current academic year.

    GET /terms

### Parameters

- in: YYYY format that returns all terms in the academic year
- since: ISO-8601 formatted date
- until: ISO-8601 formatted date

### Response

```json
{
    "id": 1,
    "name": "Fall 2014",
    "start_date": "2014-09-01",
    "end_date": "2014-12-31"
}
```

## Get a single Term

Get a term from its id.

    GET /terms/:term_id

Also includes special endpoints for frequently accessed terms.

    GET /terms/current
    GET /terms/prev
    GET /terms/next

### Response

```json
{
    "id": 1,
    "name": "Fall 2014",
    "start_date": "2014-09-01",
    "end_date": "2014-12-31"
}
```

## List Courses

List all currently active courses.

    GET /courses

List all courses offered in a specific term.

    GET /terms/:term_id/courses

### Response

Note that course number and suffix have no numeric meaning, and may be characters, so are returned as strings.

```json
{
    "id": 1,
    "department": "MORS",
    "number": "430",
    "suffix": "0",
    "code": "MORS-430-0",
    "title": "Management and Organizations"
}
```

## Get a single Course

Get a course from its id.

    GET /courses/:course_id

### Response

```json
{
    "id": 1,
    "department": "MORS",
    "number": "430",
    "suffix": "0",
    "code": "MORS-430-0",
    "title": "Management and Organizations"
}
```

## List Instructors

List all active instructors.

    GET /instructors

List all instructors who have taught or a scheduled to teach a specific course.

    GET /courses/:course_id/instructors

### Response

```json
{
    "id": 1,
    "first_name": "John",
    "middle_name": "",
    "last_name": "Doe",
    "homepage": "",
    "img_url": ""
}
```

## Get a single Instructor

Get an instructor from their id.

    GET instructors/:instructor_id

### Response

```json
{
    "id": 1,
    "first_name": "John",
    "middle_name": "",
    "last_name": "Doe",
    "homepage": "",
    "img_url": ""
}
```

### List Sections

    GET /sections
    GET /terms/:term_id/sections
    GET /courses/course_id/sections
    GET /instructors/:instructor_id/sections

### Response

> @todo The course_id could be keyed by either id, code or both.

A section may have multiple instructors. For ease of use, instructors ids will be contained in an array of integers.

```json
{
    "id": 1,
    "term_id": 1,
    "course_id": 1,
    "course_code": "MORS-430-0",
    "section_number": 61,
    "instructors": [
        591,
        366
    ],
    "day": "MR",
    "time": "8:30-10:30"
}
```

### Get a single Section

Get a section from its id.

    GET /sections/:section_id

### Response

See note above regarding instructor id.

```json
{
    "id": 1,
    "term_id": 1,
    "course_id": 1,
    "course_code": "MORS-430-0",
    "section_number": 61,
    "instructors": [
        591,
        366
    ],
    "day": "MR",
    "time": "8:30-10:30"
}
```
