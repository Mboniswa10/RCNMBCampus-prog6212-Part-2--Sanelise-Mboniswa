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


5. Implemented API Features

The following functionality has been implemented and tested during development:

Events API

Retrieve all events.

Retrieve an event by its ID.

Categories API

Retrieve all categories.

Retrieve a category by its ID.

Enrolments API

Retrieve all enrolments.

Retrieve an enrolment by its ID.

Return HTTP 404 when an enrolment cannot be found.

Results API

Retrieve all results.

Retrieve a result by its ID.

Return HTTP 404 when a result cannot be found.

Protect the results endpoints with JWT authentication.

Authentication API

Register a new user.

Log in using registered credentials.

Hash passwords before storing them.

Generate JWT tokens after successful login.

Use JWT Bearer authentication to access protected endpoints.

Public registration assigns the Participant role by default.

Database diagnostics

A database diagnostic endpoint is available to help verify the database connection:

GET /api/diagnostics/database

6. API Endpoints

The following endpoints are available in the implemented API:

Method

Endpoint

Purpose

POST

/api/Auth/register

Register a user

POST

/api/Auth/login

Log in and obtain a JWT token

GET

/api/Events

Retrieve all events

GET

/api/Events/{id}

Retrieve an event by ID

GET

/api/Categories

Retrieve all categories

GET

/api/Categories/{id}

Retrieve a category by ID

GET

/api/Enrolments

Retrieve all enrolments

GET

/api/Enrolments/{id}

Retrieve an enrolment by ID

GET

/api/Results

Retrieve all results (JWT required)

GET

/api/Results/{id}

Retrieve a result by ID (JWT required)

GET

/api/diagnostics/database

Check database connectivity

Open Swagger after starting the application to view and test the available endpoints.

7. How to Run the Project

Prerequisites

Ensure that the following are installed:

Microsoft Visual Studio 2022.

The .NET 8 SDK.

SQL Server LocalDB.

The RaceDay database and required tables.

Setup instructions

Clone the RaceDay repository from GitHub or open the existing local repository.

Open the solution file (.sln) in Visual Studio 2022.

Check that the required NuGet packages are restored.

Verify the database connection string in RaceDay.Api/appsettings.json.

Confirm that the RaceDay database contains the required tables and sample data.

Set RaceDay.Api as the startup project.

Build the solution using Build → Build Solution.

Run the application using HTTPS or the configured development profile.

Open the Swagger page displayed by the application.

Testing authentication

Use POST /api/Auth/register to create a test account.

Use POST /api/Auth/login with the registered email and password.

Copy the JWT token returned by the login endpoint.

Use the token to authorize requests to protected endpoints.

Test the Results endpoints and confirm that authenticated requests return the expected data.

Security note: Keep JWT signing keys and other secrets out of public repositories. Use development secrets or environment variables for sensitive configuration. Do not use a development signing key in production.

8. Testing and Verification

The following checks were completed during development:

The solution built successfully.

The database diagnostic endpoint returned HTTP 200.

The Events API returned HTTP 200 for collection and individual-event requests.

The Categories API returned HTTP 200 for collection and individual-category requests.

The Enrolments API returned HTTP 200 for existing data and HTTP 404 for a missing enrolment.

The Results API returned HTTP 200 for collection and individual-result requests and HTTP 404 for a missing result.

User registration and login returned successful HTTP responses.

JWT authentication was used to access a protected Results endpoint.

The automated test suite reported 3 tests passed and 0 failed at the time of verification.

These results reflect the functionality verified during development. Run the build and tests again before final submission.

9. Automated Testing

The RaceDay.Api.Tests project uses xUnit for automated testing.

To run the tests in Visual Studio 2022:

Open Test → Test Explorer.

Build the solution.

Select Run All Tests.

Check the results and resolve any failures.

Alternatively, run the following command from the solution directory:

dotnet test

11. Demonstration Video

The demonstration video presents the RaceDay Part 2 project and its implemented functionality.

YouTube video: [Insert your YouTube video link here]

Replace the placeholder above with the actual link to your demonstration video.

12. Conclusion

RaceDay Part 2 extends the original database project by introducing a .NET 8 Web API, database integration through Entity Framework Core, API endpoints for race-related data, JWT authentication, Swagger documentation, and automated testing.

The project demonstrates the implementation and verification of core API functionality using Microsoft development technologies.

Assignment: PROG6212 – Part 2
Project: RaceDay
Framework: .NET 8
Development environment: Visual Studio 2022


