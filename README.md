# SchoolAppCore

A modern ASP.NET Core Razor Pages application for managing a school information system. This project demonstrates how to build a small yet complete academic management platform using ASP.NET Core, Razor Pages, Entity Framework Core, and SQL Server.

[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![.NET](https://img.shields.io/badge/.NET-10.0-512BD4)](https://dotnet.microsoft.com/)
[![Platform](https://img.shields.io/badge/platform-Web%20Application-2DDE98)](https://learn.microsoft.com/aspnet/core/)

## Overview

SchoolAppCore is a web-based academic management system designed for educational institutions to manage core university data efficiently. The application supports common school operations such as maintaining student records, instructor profiles, departments, courses, and enrollment data.

The project follows a clean MVC-style page-based architecture using Razor Pages and leverages Entity Framework Core for object-relational mapping and database access. It is especially useful as a learning reference for developers who want to understand database modeling, page-based web application development, and data-driven UI workflows in ASP.NET Core.

## Key Features

- Student management with create, read, update, and delete operations
- Instructor management support
- Department record management
- Course management with enrollment-related relationships
- Enrollment tracking and academic registration workflow
- Server-side data access using Entity Framework Core
- Razor Pages-based UI for a straightforward and maintainable structure
- SQL Server integration through connection-string configuration

## Technology Stack

- ASP.NET Core 10.0
- Razor Pages
- C#
- Entity Framework Core
- SQL Server
- HTML / CSS / Bootstrap-style web front-end
- Visual Studio / .NET CLI workflow

## Domain Model

The application is built around a typical academic domain model:

- Student
- Instructor
- Department
- Course
- Enrollment

These entities are represented in the `SchoolAppCore/Model` directory and are managed through a centralized `SchoolContext` database context.

## Project Structure

```text
ASPNETCoreRazorPageSchoolApp/
├── SchoolAppCore/
│   ├── Model/
│   │   ├── Course.cs
│   │   ├── Department.cs
│   │   ├── Enrollment.cs
│   │   ├── Instructor.cs
│   │   ├── SchoolContext.cs
│   │   └── Student.cs
│   ├── Pages/
│   │   ├── Courses/
│   │   ├── Departments/
│   │   ├── Enrollments/
│   │   ├── Instructors/
│   │   ├── Students/
│   │   ├── Shared/
│   │   ├── Index.cshtml
│   │   ├── Privacy.cshtml
│   │   ├── Error.cshtml
│   │   ├── _ViewImports.cshtml
│   │   └── _ViewStart.cshtml
│   ├── wwwroot/
│   ├── appsettings.json
│   ├── appsettings.Development.json
│   ├── Program.cs
│   ├── libman.json
│   ├── NuGet.Config
│   └── SchoolAppCore.csproj
├── NuGet.Config
├── SchoolAppCore.slnx
├── .gitignore
└── README.md
```

## Prerequisites

Before running the project, ensure the following are installed:

- .NET SDK 10.0 or later
- SQL Server (local instance or accessible server)
- A database management or connection tool such as SQL Server Management Studio
- An IDE such as Visual Studio 2022 or VS Code

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/PhamMinh-777/ASPNETCoreRazorPageSchoolApp.git
cd ASPNETCoreRazorPageSchoolApp
```

2. Restore NuGet packages:

```bash
dotnet restore
```

3. Configure the database connection string in `SchoolAppCore/appsettings.json`:

```json
{
  "ConnectionStrings": {
    "SchoolDBConnectionString": "Server=localhost;Database=SchoolDB;Trusted_Connection=True;TrustServerCertificate=True;"
  }
}
```

Update the server name and database name to match your local environment.

4. Ensure that the target SQL Server database exists or create it before running the application.

5. Build and run the application:

```bash
dotnet build

dotnet run --project SchoolAppCore
```

6. Open the browser and navigate to the local development URL, typically:

```text
https://localhost:5001
```

or

```text
http://localhost:5000
```

## Database Configuration

The project uses `SchoolContext` and registers it in `Program.cs` with SQL Server support:

```csharp
builder.Services.AddDbContext<SchoolContext>(options =>
    options.UseSqlServer(builder.Configuration.GetConnectionString("SchoolDBConnectionString")));
```

This design allows the app to connect to SQL Server, map the application entities, and perform CRUD operations efficiently using EF Core.

## Application Workflow

The app follows a common academic information-system flow:

1. Manage departments and academic units
2. Register instructors and staff
3. Add or update course offerings
4. Keep student records synchronized
5. Record enrollments and student-course relationships
6. View details and summaries through page-based data access

This workflow reflects a typical educational administration scenario and is suitable as a foundation for further enhancements such as authentication, reporting, role-based access control, and advanced analytics.

## Why This Project Matters

This repository is valuable for developers and learners because it demonstrates several practical software engineering concepts:

- Domain-driven modeling
- Razor Pages architecture in ASP.NET Core
- ORM integration with Entity Framework Core
- Relational database design
- CRUD user interfaces with data validation and navigation
- Real-world educational application patterns

## Future Enhancements

Potential improvements for the project include:

- Authentication and authorization
- User roles (admin, teacher, student)
- Reporting and dashboard analytics
- Search and filtering across tables
- Pagination and sorting improvements
- Student grade tracking and transcript generation
- Integration with modern UI frameworks

## Contributing

Contributions are welcome. If you would like to improve the project, please follow these steps:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Open a pull request with a clear description

## License

This project is provided for educational and demonstration purposes. Please check the repository license if added in your environment or adapt according to your organization’s policies.

## Acknowledgments

This project was designed to illustrate a practical ASP.NET Core application pattern for school management and educational data processing. It is intended as a learning resource for developers exploring Razor Pages and Entity Framework Core in real-world scenarios.

## Contact

For questions or collaboration opportunities, please use the repository's GitHub issue tracker or contact the project maintainer through the repository profile.

---

Built with ASP.NET Core and designed for academic information management.
