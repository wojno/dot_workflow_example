# Basic Workflow and Planning

## Project Description
Imagine that `Walrus Farm` has just acquired a new company.  Unfortunately, the company has never stored their `data` in a `database` and instead uses a `plain text` file.  Your task is to create a `web interface` that accepts `file uploads`, `normalizes the data`, and then stores it in a `relational database`.

Here's what your web-based application must do:

1. Your app must accept (via a `form`) a `tab delimited` file with the following columns: 
  * purchaser name
  * item description
  * item price
  * purchase count
  * merchant address
  * merchant name 
  
  You can assume the columns will always be in that order, that there will always be data in each column, and that there will always be a header line.  An example input file named `example_input.tab` will be provided.

2. Your app must `parse` the given file, `normalize` the data, and `store` the information in a `relational` database.
3. After `upload`, your application should display the `total amount gross revenue` represented by the `uploaded` file.

## Solution

`workflow.png` shows an initial plan for how the application workflow should function.  I chose to leverage a `task queue` to facilitate high levels of traffic in an initial attempt to scale the application.  After `tasks` are received by either the `Revenue` or `Ingestor` service, they push `real time` updates to the `User Interface` through `web sockets`.

`database_schema.png` shows the initial layout for the Database and how all tables are related.

`todo.yml` is a basic `bug tracking` and `todo` list to tie commits to functionality for later reference.  This was implemented as a lightweight solution in place of `Jira` or `Redmine`.
