# C# CRUD Application with SQL Database

This project is a simple CRUD (Create, Read, Update, Delete) application in C# that interacts with an SQL Server database.


## Table Structure

The application manages user data stored in the `Info` table of the `MyProject` database.


![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)
![image](https://github.com/user-attachments/assets/2959af28-35db-4025-ad05-9ff1bcdaec39)



## Prerequisites

This project is used by the following companies:

- Visual Studio or any C# IDE
- SQL Server
- .NET Framework (version specified in the project)
- SQL Server Management Studio (SSMS) for database management (optional)


## Setup Instructions

### Clone the Repository:
```http
  git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name

```

### Database Setup:
1. Create the Database `MyProject`
Run the following SQL query in SQL Server Management Studio (SSMS) to create the `MyProject` database:

```http
  CREATE DATABASE MyProject;

```

2. Create the Table `Info`
Once the database is created, use the following SQL query to create the `Info` table:

```http
USE MyProject;

CREATE TABLE Info (
    ID INT PRIMARY KEY IDENTITY(1,1),
    FirstName NVARCHAR(100),
    SecondName NVARCHAR(100)
);

INSERT INTO Info (FirstName, SecondName) VALUES 
('Fatima', 'Fariha'),
('Talha', 'Islam'),
('Tanjina', 'Rima'),
('Saima', 'Noor'),
('Tasmeem', 'Prome'),
('Suha', 'Ameer'),
('Moushumi', 'Akand'),
('Ameer', 'Zahid');

```


3. Generate Database Script :
To generate a script for the database in SQL Server:

- Open SSMS, right-click on the `MyProject` database. 
- Select Tasks -> Generate Scripts.
- Follow the wizard to generate a script for the database schema and/or data.

4. Backup the Database:

To back up the `MyProject` database in SQL Server:

- Open SSMS, right-click on the `MyProject` database.
- Select Tasks -> Back Up.
- Choose the destination and options, and click OK.

### Application Configuration

1. Update Connection String
In the `appsettings.json` file or inside your application's `DbContext` class, update the connection string to point to your local SQL Server instance. Example:
```http
  {
  "ConnectionStrings": {
    "DefaultConnection": "Server=your_server_name;Database=MyProject;Trusted_Connection=True;"
  }
}

```


2. Run Database Migrations (if applicable)
If your project uses Entity Framework, you can run migrations using the Package Manager Console or CLI:
```http
Update-Database


```
or

```http
 dotnet ef database update

```

### Running the Application
- Open the project in Visual Studio and build the solution.
- Run the application by pressing `F5`.
- The CRUD operations will interact with the `Info` table in the `MyProject` database.

## CRUD Operations
- Create: Add new records to the `Info` table.
- Read: Fetch records from the `Info` table.
- Update: Modify existing records in the `Info` table.
- Delete: Remove records from the `Info` table

## Backup and Restore
You can use SQL Server Management Studio (SSMS) to back up the database and restore it as needed.

- Backup: Right-click on the `MyProject` database in SSMS, go to Tasks -> Back Up.
- Restore: Right-click on the Databases folder in SSMS, select Restore Database, and choose the backup file.
## API Reference

#### Get all items

```http
  GET /api/items
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get item

```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch |

#### add(num1, num2)

Takes two numbers and returns the sum.


## Support

For support, Email: fatimaameerfariha@gmail.com or Watch https://youtu.be/5vOypcJEufE?si=e4H-hIBVppGC9ypn


## License

