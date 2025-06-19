
# PersonalProfile Web App

## 📄 Project Overview

This project is a full-stack web application designed to manage personal portfolio information, much like a LinkedIn profile. It enables the user to view, edit, add, and remove sections such as personal info, skills, education, experience, and projects.

Technologies used:
- **Frontend:** ReactJS
- **Backend (API):** ASP.NET Core Web API (C#)
- **Class Library:** C# Domain and Services
- **Database:** SQL Server (with stored procedures)

---

## 🧱 Folder Structure

```
PersonalProfileSolution/
├── PersonalProfile/                # ASP.NET Core Web API
├── PersonalProfile.Domain/        # Class Library for domain models
├── PersonalProfile.Service/       # Class Library for business logic services
├── PersonalProfile.DatabaseScripts/SqlScripts/
│   ├── CreateTables.sql
│   ├── InsertSampleData.sql
│   └── StoredProcedures.sql
└── frontend/                       # ReactJS Frontend (in separate folder)
```

---

## ⚙️ Setup Instructions

### Backend

1. Open the solution in **Visual Studio 2022**.
2. Build the solution. All services, interfaces, and models are defined in the Domain and Service libraries.
3. Run the Web API to access endpoints via Swagger UI: `https://localhost:7206/swagger/index.html`

### Frontend

1. Navigate to the frontend folder.
2. Install dependencies:

```bash
npm install
```

3. Start the frontend:

```bash
npm start
```

---

## ❗ Database Issue and Resolution Attempts

### Issue

The **SQL Database Project** in Visual Studio failed to load due to SDK tooling issues. Every attempt to enable the database functionality using Visual Studio’s “Add New Project > SQL Server Database Project” resulted in the following error:

> *“The required components for SQL Server Data Tools were not installed properly.”*

### Troubleshooting Steps Taken

- Verified the installation path and Visual Studio workloads.
- Ran Visual Studio Installer Repair.
- Uninstalled and reinstalled the **SQL Server Data Tools** component.
- Tried a **fresh reinstall** of Visual Studio 2022 Community Edition.
- Installed **SQL Server 2022 Express** successfully.
- Attempted to run `.sql` scripts via `sqlcmd`, which failed due to named pipes/connection timeout issues.

### Final Decision

Due to unresolved installation issues, the database is **represented manually** via `.sql` files containing:
- Table creation scripts
- Insert sample data scripts
- Stored procedures

These are found in:

```
PersonalProfile.DatabaseScripts/SqlScripts/
```

**Note:** Functionality is mocked on the frontend using local ReactJS state. The fetch requests are implemented and commented out for backend integration testing.

---

## 🔧 Testing and Mock Mode

- API endpoints are fully implemented and tested using Swagger.
- React frontend includes working mock logic (add, edit, delete, view) with local state.
- All fetch calls are retained and simply commented out, allowing smooth transition to backend integration once the DB is functional.


## ⚠️ Important Note

Please note that the `node_modules` folder has been excluded from the project to reduce the file size for upload.  
After downloading the project, navigate to the React frontend folder and run:

```
npm install
```

This will restore all necessary dependencies for the frontend.

---

