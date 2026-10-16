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
