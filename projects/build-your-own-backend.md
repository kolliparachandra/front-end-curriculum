---
title: Build Your Own Backend
module: 4
---

## Abstract

Practice makes practice. Last week's project had you dive head first into a full-stack application with Node, Express, Knex, and a front-end to boot. That was a lot thrown at you in one week so this time around we are going to focus solely on the backend.

The main focus of this project will be to reinforce your understanding of CRUD methods, querying a database, and responding with JSON data. You can do this project right now, without any new lessons.

The secondary focus of this project is prepping your Capstone project so you have data ready to go and can dive into building a super badass UI instead of wasting a week in Node land. It's not necessary that you find perfect data for your Capstone, but it's vital that you know how to setup production APIs that are well tested. You can easily replace the source of your data, so don't worry if you can't come up with a good data source or if you have no idea what you want to build for the Capstone. Find or create interesting data that you might want to use in the future.

## Base Expectations

### API Structure & Best Practices

In the README, developer should provide documentation on the API endpoints that can be hit. This can be as simple as just listing all endpoints (and accepted params) with explanation of responses. Here is a [great example of in depth documentation](https://github.com/500px/api-documentation/blob/master/README.md)

### Sources of Data

Data source MUST BE LOCKED IN by Tuesday (5/16) EOD . We don't want you wasting the whole week trying to find data. Having production API endpoints well tested is more important.

Possible sources of data:

* Rebuild a backend from your personal project
* Work with and scrape new data from an API. Some APIs are easier to work with than others - you may not be able to pull off the thing you want to do - be prepared for that.
  * https://developer.nrel.gov/
  * https://sunlightfoundation.com/api/
  * https://developer.foursquare.com/
  * data.world
* Parse CSVs or JSON files (Node has built-in modules for parsing CSVs)
* Create the data yourself. You must create a ‘seed file’ with a minimum of 30 rows of data for each main table

### Relationships

At minimum, you must have at least 1 relationship between two or more tables. (e.g. one-to-one, one-to-many, many-to-many)

### Required endpoints

* 4 GET endpoints
  * 2 GET endpoints for all of one resource (i.e. '/api/v1/merchants')
  * 2 GET endpoints for a specific resource (i.e. '/api/v1/merchants/:id')
* 2 POST endpoints
* 2 PUT OR PATCH endpoints
* 2 DELETE endpoints

### Status Codes & Error Handling

All endpoints should respond with the minimum status code results:

* 200: Success
* 404: Not Found

If POST request fails to save an entity due to bad information being sent to it, you should respond with

* 422: Unprocessable Entity

If you have a critical server error, you should respond with

* 500: Internal Server Error

You are welcome to use other status codes.

All of the above scenarios (other than the 500 error) should be tested per endpoint.

In addition to responding with the appropriate status code, you are expected to send back clear, informative error messages when something goes wrong. Do not simply `console.log` 'WHATEVER'. If a `POST` request fails because the request didn't include a required parameter, respond with something like 'Entity requires a <fieldName> but none was provided.'

### Custom API Endpoints

* Developer must use GET params on at least one endpoint, which would allow the user to narrow down the nature of their request or filter their results. So for example, you may have an endpoint like:

`GET api/v1/merchants?areacode=80202`

Which would limit the results to merchants in the 80202 area code.

A further example of this implementation can be found here: [params](https://scotch.io/tutorials/use-expressjs-to-get-url-and-post-parameters)

* Developer must secure at least 4 endpoints with a JWT. It typically makes sense to secure all POST/PUT/PATCH/DELETE requests.

### Testing & Linting

* All endpoints need to be tested for happy and sad paths. You should not only test status codes but also your test database to assert that your requests are doing what you are expecting.

* You are expected to use a linter on this project and have 0 linting errors. You are free to choose your own linting configuration that fits your style preferences (e.g. you can tell eslint that you will never use semicolons), but your project must pass your linter. Bonus points for using a git hook that prevents you from committing any unlinted code.

### Deployment

* Your application should be deployed to Heroku & have builds running with CircleCI. You do not need a staging environment for this project, but your production repo should be configured for automatic deployments to Heroku via CircleCI.


## Instructor Evaluation Points

The following set of points are distributed at the discretion of the instructor.

### Endpoints

* **60 points** - Developer has implemented all 10 endpoints, 4 are secured via JWTs and one is a custom endpoint that filters data based on query params.
* **40 points** - Developer has implemented all 10 endpoints but did not secure 4 of them with JWTs or have a custom endpoint based on query params.
* **20 points** - Developer is missing endpoints and has not secured or customized any of the ones that have been implemented.

### Data Persistence with SQL Database

* **40 points** - The application persists data in a SQL database but with correct relationships between folders and URLs.
* **20 points** - The application persists data in a SQL database but with some incorrect relationships between folders and URLs.
* **0 points** - The application does not persist data in a SQL database.

### Testing & Linting

* **30 points** - Project has a running test suite that covers all happy and sad paths for the appropriate endpoints. The project has a linting configuration that passes with no errors.
* **20 points** - Project has a running test suite that covers most happy and sad paths for each endpoint. Linter has some errors that need fixing.
* **10 points** - Project has significant lack of testing for happy and sad paths of endpoints; Linter is failing on multiple lines.

### JavaScript Style

* **20 points** - Application has exceptionally well-factored code with little or no duplication and all components separated out into logical components. There _zero_ instances where an instructor would recommend taking a different approach.
* **15 points** - Application is thoughtfully put together with some duplication and no major bugs. Developer can speak to choices made in the code and knows what every line of code is doing.
* **12 points** - Your application has some duplication and minor bugs. Developer can speak to most choices made in the code and knows what every line is doing.
* **5 points** - Your application has a significant amount of duplication and one or more major bugs. Developer cannot speak to most choices and does not know what every line of code is doing.


## Projects are due on Friday 5/19, 1:00 p.m. We will provide a submission form for all teams to submit their repos.

## Project is worth 150 points

## To get a 3 on this project, you need to score 110 points or higher

## To get a 4 on this project, you need to score 140 points or higher

# Final Score: x / 150
