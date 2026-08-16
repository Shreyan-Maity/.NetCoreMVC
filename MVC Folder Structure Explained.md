# 📂 MVC Project Folder Structure Explained

## 🔹 Root Level
- **`Program.cs`** → **Entry point** of the application. Configures services and middleware.  
- ~~**`Startup.cs`**~~ (in older versions) → Defines app configuration, middleware pipeline, and services.  
- **`appsettings.json`** → Stores configuration (connection strings, logging, etc.).  
- **`Properties/launchSettings.json`** → Defines how the app runs locally (ports, profiles).  



## 🔹 `Controllers/`
- **Purpose**: Handles incoming requests and decides what response to send.  
- **Example**: `HomeController.cs` → Has actions like `Index()`, `About()`.  
- **Why**: Implements the **C** in MVC (Controller). It connects Models ↔ Views.  



## 🔹 `Models/`
- **Purpose**: Represents the data and business logic.  
- **Example**: `User.cs` → Defines properties like `Id`, `Name`, `Email`.  
- **Why**: Implements the **M** in MVC (Model). Used for database interaction and validation.  



## 🔹 `Views/`
- **Purpose**: Contains UI templates (`.cshtml` files).  
- **Structure**:
  - `Views/Home/Index.cshtml` → Page for `HomeController.Index()`.  
  - `Views/Shared/_Layout.cshtml` → Master layout (header, footer, nav).  
- **Why**: Implements the **V** in MVC (View). Renders HTML to the browser.  



## 🔹 `wwwroot/`
- **Purpose**: Public static files (CSS, JS, images).  
- **Example**: `wwwroot/css/site.css`, `wwwroot/js/site.js`.  
- **Why**: Anything here is directly accessible by the browser.  



## 🔹 `Areas/` (optional)
- **Purpose**: Organize large apps into modules (e.g., Admin, Customer).  
- **Structure**: Each area has its own Controllers, Views, Models.  
- **Why**: Helps scale big projects.  



## 🔹 `Migrations/` (if using Entity Framework)
- **Purpose**: Tracks database schema changes.  
- **Example**: `20230815_AddUserTable.cs`.  
- **Why**: Keeps DB in sync with Models.  



## 🔹 `bin/` & `obj/`
- **Purpose**: Compiled files and build artifacts.  
- **Why**: Generated automatically, not manually edited.  



# ⚡ How They Work Together
- **Controller** → Receives request (`/Home/Index`).  
- **Model** → Provides data (e.g., fetch users from DB).  
- **View** → Displays data in HTML (`Index.cshtml`).  
- **wwwroot** → Supplies CSS/JS for styling and interactivity.  



👉 Think of it like this:
- **Controllers** = Brains 🧠 (decide what to do).  
- **Models** = Data 📊 (what you work with).  
- **Views** = Face 🎨 (what the user sees).  
- **wwwroot** = Clothes 👕 (style and scripts).  

Here’s the visual diagram — it shows the **MVC flow from request to response**. 

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/ccb758a7-877a-4d2b-8bab-2ad9c50d243c" />

`https://copilot.microsoft.com/th/id/BCO.85870b65-b66d-42b5-ad8c-18569ebdb231.png`

# 🧩 How to Read This Diagram
- **User Request** → Browser sends request (`/Home/Index`).  
- **Controller** → Handles request (`HomeController.cs`). Decides what to do.  
- **Model** → Fetches or processes data (`User.cs`, database).  
- **View** → Renders HTML (`Index.cshtml`).  
- **Response** → Browser shows the final page.  
- **wwwroot** → Supplies CSS, JS, images to style the View.  

This flow is the backbone of MVC:
- **Controller = traffic cop** 🚦 (routes requests).  
- **Model = data brain** 🧠 (logic + database).  
- **View = designer** 🎨 (UI rendering).  
- **wwwroot = toolbox** 🧰 (static assets).

Here’s a **structured list of topics to cover in ASP.NET Core MVC** so you can learn step by step without missing anything.  
