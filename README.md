# Human Resource Management System (HRMS)

This is a simple Human Resource Management System (HRMS) implemented in Go using the Fiber web framework and MongoDB as the database. It provides basic CRUD (Create, Read, Update, Delete) operations for managing employee records.

## Prerequisites

Before running this application, make sure you have the following installed:

- Go
- MongoDB

## Installation

1. Clone the repository:

   ```shell
   git clone https://github.com/your-username/hrms.git
   ```

2. Change to the project directory:

   ```shell
   cd hrms
   ```

3. Install the required dependencies:

   ```shell
   go get
   ```

4. Start the application:

   ```shell
   go run main.go
   ```

   The application will start listening on `http://localhost:3000`.

## API Endpoints

The following API endpoints are available:

### Get All Employees

- **URL:** `/employee`
- **Method:** `GET`
- **Description:** Retrieves all employees' records from the database.
- **Success Response:**
  - **Status Code:** 200
  - **Content:**
    ```json
    [
      {
        "id": "employee_id",
        "name": "John Doe",
        "salary": 5000,
        "age": 30
      },
      {
        "id": "employee_id",
        "name": "Jane Smith",
        "salary": 6000,
        "age": 35
      }
    ]
    ```

### Create Employee

- **URL:** `/employee`
- **Method:** `POST`
- **Description:** Creates a new employee record.
- **Request Body:**
  ```json
  {
    "name": "John Doe",
    "salary": 5000,
    "age": 30
  }
  ```
- **Success Response:**
  - **Status Code:** 201
  - **Content:**
    ```json
    {
      "id": "employee_id",
      "name": "John Doe",
      "salary": 5000,
      "age": 30
    }
    ```

### Update Employee

- **URL:** `/employee/:id`
- **Method:** `PUT`
- **Description:** Updates an existing employee record.
- **URL Parameters:**
  - `id` - The ID of the employee to update.
- **Request Body:**
  ```json
  {
    "name": "John Doe",
    "salary": 5500,
    "age": 32
  }
  ```
- **Success Response:**
  - **Status Code:** 200
  - **Content:**
    ```json
    {
      "id": "employee_id",
      "name": "John Doe",
      "salary": 5500,
      "age": 32
    }
    ```

### Delete Employee

- **URL:** `/employee/:id`
- **Method:** `DELETE`
- **Description:** Deletes an employee record.
- **URL Parameters:**
  - `id` - The ID of the employee to delete.
- **Success Response:**
  - **Status Code:** 200
  - **Content:**
    ```json
    "record deleted"
    ```

## Database Configuration

By default, the application connects to a local MongoDB instance running on `mongodb://localhost:27017/HRMS`. You can modify the `mongoURI` constant in the code to specify a different MongoDB connection URI.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
