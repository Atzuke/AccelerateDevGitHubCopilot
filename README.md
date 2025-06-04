# Library App

## Description

Library App is a console-based library management system built with .NET 8.0. It allows users to search for patrons, view and manage book loans, and renew memberships. The application uses a clean architecture approach, separating core business logic, infrastructure, and presentation layers. Data is stored in JSON files for easy setup and portability.

## Project Structure

- AccelerateDevGitHubCopilot.sln
- README.md
- src/
  - Library.ApplicationCore/
    - Library.ApplicationCore.csproj
    - Entities/
    - Enums/
    - Interfaces/
    - Services/
  - Library.Console/
    - appSettings.json
    - CommonActions.cs
    - ConsoleApp.cs
    - ConsoleState.cs
    - Library.Console.csproj
    - Json/
      - Authors.json
      - Books.json
      - BookItems.json
      - Loans.json
      - Patrons.json
    - Program.cs
  - Library.Infrastructure/
    - Library.Infrastructure.csproj
    - Data/
      - JsonData.cs
      - JsonLoanRepository.cs
      - JsonPatronRepository.cs
- tests/
  - UnitTests/
    - LoanFactory.cs
    - PatronFactory.cs
    - ApplicationCore/
      - PatronService/
        - RenewMembership.cs
      - LoanService/
        - ReturnLoan.cs
        - ExtendLoan.cs
    - UnitTests.csproj

## Key Classes and Interfaces

- **Core Entities**
  - `Patron`, `Loan`, `BookItem`, `Book`, `Author` ([src/Library.ApplicationCore/Entities/](src/Library.ApplicationCore/Entities/))
- **Enums**
  - `MembershipRenewalStatus`, `LoanReturnStatus`, `LoanExtensionStatus`, `EnumHelper` ([src/Library.ApplicationCore/Enums/](src/Library.ApplicationCore/Enums/))
- **Interfaces**
  - `IPatronRepository`, `ILoanRepository`, `IPatronService`, `ILoanService` ([src/Library.ApplicationCore/Interfaces/](src/Library.ApplicationCore/Interfaces/))
- **Services**
  - `PatronService`, `LoanService` ([src/Library.ApplicationCore/Services/](src/Library.ApplicationCore/Services/))
- **Infrastructure**
  - `JsonData`, `JsonPatronRepository`, `JsonLoanRepository` ([src/Library.Infrastructure/Data/](src/Library.Infrastructure/Data/))
- **Console Application**
  - `ConsoleApp`, `ConsoleState`, `CommonActions` ([src/Library.Console/](src/Library.Console/))

## Usage

1. **Build the project:**
   ```sh
   dotnet build
   ```

2. **Run the console application:**
   ```sh
   dotnet run --project src/Library.Console/Library.Console.csproj
   ```

3. **Unit Tests:**
   ```sh
   dotnet test
   ```

4. **Configuration:**
   - Edit `src/Library.Console/appSettings.json` to change JSON data file paths if needed.
   - Data files are located in `src/Library.Console/Json/`.

## License

This project is licensed under the MIT License.
