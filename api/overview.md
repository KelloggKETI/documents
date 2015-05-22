# API Overview

## Schema

- Protocol: HTTPS only
- Domain: TBD
- Content type: JSON only
- Date format: ISO 8601 (YYYY-MM-DDTHH:MM:SSZ)

All valid GET requests return a json object as the response. GET requests return either a collection or an item in the data property. 

A collection is returned as an array of objects:

````json
{
    “data”: [
        ...
    ],
    ...
}
```

An item is returned as an object:

```json
{
    “data”: {
        ...
    },
    ...
}
```

Other members can be used for metadata (e.g. links) and are described in the appropriate sections.

## Authentication

TBD

## Pagination

All GET requests that return a collection are paginated with a default page length of 20. A specific page can be accessed by appending a `page` parameter to the query string. The number of items returned per page can be changed by appending a `per_page` parameter to the query string, up to a maximum of X.

The links field in the response contains navigable links (next, last, first, prev) for following. Somewhere in the response, it includes the total number of pages and current page.
