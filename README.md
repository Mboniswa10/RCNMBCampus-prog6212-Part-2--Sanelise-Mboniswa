RaceDay – PROG6212 Part 2

1. Project Overview

RaceDay is an event management system developed as part of the PROG6212 Part 2 assignment. The project builds on the database design completed in Part 1 and provides a RESTful Web API for managing race events and related information.

The API connects to a Microsoft SQL Server database and uses Entity Framework Core to access and manage data. JWT (JSON Web Token) authentication is implemented to support secure access to protected endpoints.

2. Technologies Used

Programming language: C#

Framework: .NET 8

Development environment: Microsoft Visual Studio 2022

API architecture: ASP.NET Core Web API

Database: Microsoft SQL Server LocalDB

Data access: Entity Framework Core

Authentication: JWT Bearer Authentication

API documentation and testing: Swagger / OpenAPI

Unit testing: xUnit

Version control: Git and GitHub

3. Solution Structure

The solution contains the following projects:

RaceDay.Api – Contains the Web API, controllers, data access configuration, database context, models, authentication, and application configuration.

RaceDay.Contracts – Contains the contracts project for sharing request or response definitions between application components.

RaceDay.Api.Tests – Contains automated tests for API functionality.

The repository also retains the relevant Part 1 SQL scripts, documentation, and other assignment files.

4. Database Design

The application connects to the RaceDay database using SQL Server LocalDB.

The database includes the following main entities:

Users – Stores user information, including names, email addresses, password hashes, and roles.

Events – Stores race event details, including event names, dates, venues, distances, entry fees, and participant limits.

Categories – Stores event participation categories.

Enrolments – Records participants' enrolments in events.

Results – Stores race result information.

The database design uses relational database principles, including primary keys and foreign-key relationships, to maintain data integrity.

Database connection

The application uses a connection string configured in appsettings.json. For local development, the connection string follows this format:

Server=(localdb)\MSSQLLocalDB;Database=RaceDay;Trusted_Connection=True;TrustServerCertificate=True;

Make sure the RaceDay database exists in your local SQL Server instance before running the API.


