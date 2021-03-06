# ModernShopping: Modern Software Application Sample

When you look at the sample applications out there today, you will see that they are pretty simple and possibly only focuses on one bit of concept or technology. This is really good to get your head around it at first but after a while, you may struggle to get everything together and produce a lovely solution.

**ModernShopping** targets to provide a fully fledged solution for a shopping company like Amazon.

## Main Objectives

This application will be built several objectives in mind:

 - HTTP interface first approach
 - Microservices-like approach
 - Polyglot persistence
 - Centralized logging
 - Top-notch deployment, release and versioning story
 - Multiple clients (Web, iPhone, Android, etc.)
 - Not-only-one architectural pattern

## Approach to Take (Premature Thoughts)

The below is the prefered approach to take to build this project:

 - **Authentication/Identity:** We need to identify users in our system and persist the identity. Good case for relational data storage system like SQL Server.
 - **Lookup:** We should be able to view the products on a client (e.g. lookup by id or simple listing). Incredibly sensible for MongoDB.
 - **Search:** We should be able to search for products.
 - **Shopping Cart:** User should be able to fill in their shopping cart. Perfect case for event store!
 - **Order:** Whole point of the business. Without the orders, we are NOTHING! Good case for asyncronous processing (stock limit, price changes, etc.).

### Cross Cutting Concerns

 - Analytics: This is important bit so that
     - 1-) we can approach people with recommendations. Good case for a graph database.
     - 2-) we can identify the application usage. Good case for Google analytics.

### Going Beyond
 - Product Comments: Make users comment on products and identify users with legit comments for the stuff that they have bought.

## Some Constraints

 - Have integration tests only, no unit tests.
 - Use NodaTime on all .NET projects whenever possible.
 - The whole solution should be runable cohesively with minimal config locally as well as individual pieces running seperately.

## How to Run the Solution

> :warning: This is still in progress but the below is the ideal approach that is targgeted to run this during development.

This application consists of several little, targetted applications and in order to be able to run the entire solution in a cohesive way in your local machine, it leverages [Docker Compose](https://docs.docker.com/compose/). You should be able to get everything up and running by running `docker-compose up` command under the root directory of this repository.

## Technologies to Use

This type of architecture encouranges to use different flovours of technologies. However, there are some certain technologies we will use within the solution:

 - [ASP.NET MVC Core](https://github.com/aspnet/Mvc)
 - [React](https://facebook.github.io/react/)
 - [Neo4j](https://neo4j.com/)
 - [Elasticsearch](https://www.elastic.co/products/elasticsearch)
