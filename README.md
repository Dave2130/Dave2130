# 📚 LectureNoteAPI

A robust RESTful API built with **ASP.NET Core** for managing lectures, notes, students, and documents in an academic environment.

---

## 🚀 Features

- 🔐 **User Authentication & Authorization** (JWT-based with roles)
  - Admin & Student roles
- 🧾 **Lecture Management**
  - Create, view, and delete lectures
- 🗒️ **Notes Management**
  - Add, update, view, and delete notes for a lecture
- 📁 **Document Upload**
  - Upload and store documents securely
- 👥 **Student Management**
  - View and delete student users

---

## 🔧 Technologies Used

- ASP.NET Core 8
- Entity Framework Core (SQL Server)
- Identity + Role Management
- JWT Authentication
- Swagger / OpenAPI

---

## 📁 Project Structure

LectureNoteAPI/
│
├── Controllers/
├── Dtos/
│ ├── Lecture/
│ ├── Note/
│ ├── Login/
│ ├── RegisterStudent/
│ └── Document/
├── Models/
├── Services/
│ ├── Interfaces/
│ └── Implementations/
├── Middleware/
├── Data/
└── Program.cs

pgsql
Copy code

---

## 📄 API Endpoints

### 🔐 Auth

| Method | Endpoint             | Access | Description             |
|--------|----------------------|--------|-------------------------|
| POST   | `/api/Auth/register` | Public | Register a new user     |
| POST   | `/api/Auth/login`    | Public | Login and receive token |

### 📚 Lectures

| Method | Endpoint             | Access | Description         |
|--------|----------------------|--------|---------------------|
| GET    | `/api/Lectures`      | All    | Get all lectures    |
| GET    | `/api/Lectures/{id}` | All    | Get lecture by ID   |
| POST   | `/api/Lectures`      | Admin  | Create a lecture    |
| DELETE | `/api/Lectures/{id}` | Admin  | Delete a lecture    |

### 🗒️ Notes

| Method | Endpoint                          | Access        | Description           |
|--------|-----------------------------------|---------------|-----------------------|
| GET    | `/api/Notes/lecture/{lectureId}`  | Admin,Student | Notes for a lecture   |
| POST   | `/api/Notes/lecture/{lectureId}`  | Admin         | Add note to lecture   |
| GET    | `/api/Notes/{id}`                 | Admin,Student | Get a note by ID      |
| PUT    | `/api/Notes/{id}`                 | Admin         | Update a note         |
| DELETE | `/api/Notes/{id}`                 | Admin         | Delete a note         |

### 📁 Documents

| Method | Endpoint               | Access | Description        |
|--------|------------------------|--------|--------------------|
| POST   | `/api/Documents/upload`| Admin  | Upload a document  |

### 👥 Students

| Method | Endpoint             | Access | Description         |
|--------|----------------------|--------|---------------------|
| GET    | `/api/Students`      | Admin  | List all students   |
| DELETE | `/api/Students/{id}` | Admin  | Delete a student    |

---

## 🛠️ Setup Instructions

### Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download)
- SQL Server (LocalDB or Express)

### Run Locally

```bash
git clone https://github.com/your-username/LectureNoteAPI.git
cd LectureNoteAPI
dotnet restore
dotnet ef database update
dotnet run
📚 Test with Swagger
After launching the app, open your browser and go to:

bash
Copy code
https://localhost:5224/swagger
Use Swagger UI to test endpoints interactively.

👨‍💻 Author
David S Lansana
📧 Email: your.XSolo536@gmail.com

📄 License
This project is open-source and free to use.
