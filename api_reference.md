Exercise B: API Reference Entry

There’s no single right design, so keep yours consistent: the field names in the parameters table must match the example request and the example response exactly.

Model: Create a Task

POST /api/v1/projects/{project_id}/tasks

Description: Creates a new task in the specified project and returns the created task. The authenticated user must be a member of the project.

Path parameters

Name	Type	Required	Description
project_id	integer	Yes	The unique ID of the project that will contain the task.

Request headers

Header	Required	Description
Authorization: Bearer <token>	Yes	The access token of the authenticated user.
Content-Type: application/json	Yes	Tells the server the body is JSON.

Request body parameters

Name	Type	Required	Description
title	string	Yes	Short name of the task (max 200 characters).
description	string	No	Longer explanation of the task (max 2,000 characters).
assignee_id	integer	Yes	The ID of the user responsible for the task.
due_date	string	Yes	Deadline in YYYY-MM-DD format.
priority	string	Yes	One of low, medium or high.

Example request body

json
{
  "title": "Design login page",
  "description": "Create wireframes for the login and password reset screens.",
  "assignee_id": 42,
  "due_date": "2026-12-05",
  "priority": "high"
}

Response codes

Code	Meaning	When it occurs
201 Created	Success	The task was created.
400 Bad Request	Invalid input	The JSON is malformed, a required field is missing, or priority isn’t low, medium or high.
401 Unauthorized	Not authenticated	The token is missing, invalid or expired.
403 Forbidden	No permission	The user isn’t a member of this project.
404 Not Found	Resource missing	The project or the assignee doesn’t exist.
429 Too Many Requests	Rate limit	The user sent too many requests in a short time.
500 Internal Server Error	Server fault	Something unexpected went wrong on the server.

Example response (201 Created)

json
{
  "id": 1087,
  "project_id": 15,
  "title": "Design login page",
  "description": "Create wireframes for the login and password reset screens.",
  "assignee_id": 42,
  "due_date": "2026-12-05",
  "priority": "high",
  "status": "open",
  "created_at": "2026-11-18T09:30:00Z"
}
