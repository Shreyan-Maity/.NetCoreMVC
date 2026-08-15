# 🖥️ Steps to Start an MVC Project Locally

## 🔹 1. Install Prerequisites
- **.NET SDK** → Download from [Microsoft .NET](https://dotnet.microsoft.com/download).  
- **IDE** → Visual Studio (recommended) or VS Code.  
- **Runtime** → Ensure ASP.NET Core runtime is installed.



## 🔹 2. Create a New MVC Project
### Using Visual Studio:
1. Open **Visual Studio** → *Create a new project*.  
2. Select **ASP.NET Core Web App (Model-View-Controller)**.  
3. Choose project name & location.  
4. Select **.NET Core** and the version (e.g., .NET 6/7).  
5. Click **Create**.

### Using CLI:
```bash
dotnet new mvc -n MyMvcApp
cd MyMvcApp
```



## 🔹 3. Build the Project
- In Visual Studio → Press **Ctrl+Shift+B** (Build).  
- In CLI:
```bash
dotnet build
```



## 🔹 4. Run the Project
- In Visual Studio → Press **F5** (Debug) or **Ctrl+F5** (Run without debugging).  
- In CLI:
```bash
dotnet run
```

👉 This will start a local server, usually at:  
`https://localhost:5001` or `http://localhost:5000`



## 🔹 5. Explore the Default MVC Structure
- **Controllers** → Handle requests (`HomeController.cs`).  
- **Views** → UI pages (`Views/Home/Index.cshtml`).  
- **Models** → Data classes.  
- **wwwroot** → Static files (CSS, JS, images).



✅ At this point, your MVC project is running locally. You can edit controllers, views, and models, then refresh the browser to see changes.

---

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

---

# 📚 ASP.NET Core MVC Learning Roadmap

## 🔹 Basics
- Introduction to MVC (Model–View–Controller pattern)  
- Program.cs (entry point & middleware pipeline)  
- Models (data & business logic)  
- Views (presentation layer with Razor)  
- Controllers (request handling & action methods)  
- Routing (convention-based vs attribute routing)  


## 🔹 Middleware & Services
- Middleware pipeline (built-in & custom middleware)  
- Error handling middleware (global exception handling)  
- Dependency Injection (DI) basics  
- Service lifetimes (Singleton, Scoped, Transient)  
- Using services in controllers  


## 🔹 Advanced MVC Features
- ViewBag, ViewData, TempData  
- Strongly typed views with Models  
- Layouts & Partial Views  
- Tag Helpers & HTML Helpers  
- Model Binding & Validation  
- Filters (Action, Authorization, Exception filters)  


## 🔹 Data & Persistence
- Entity Framework Core basics  
- Database context & migrations  
- CRUD operations (Create, Read, Update, Delete)  
- Repository pattern & Unit of Work  


## 🔹 Security & Identity
- Authentication & Authorization  
- ASP.NET Core Identity (user management)  
- Role-based access control  
- Securing routes & controllers  


## 🔹 APIs & Beyond
- API Controllers vs MVC Controllers  
- Returning JSON responses  
- Consuming APIs in MVC  
- Versioning & Swagger documentation  


## 🔹 Extras (Polish & Deployment)
- Logging & configuration  
- Error pages & exception handling  
- Static files & bundling/minification  
- Publishing & deployment (IIS, Azure, Docker) 


Excellent! Let’s walk through a **real-world example** — a simple **Login Page flow** in an ASP.NET Core MVC project — so you can see how each folder and component interacts step by step.  

---

# 🔐 MVC Login Flow Example

## 🧭 Step 1: User Request
- The user opens the browser and goes to  
  `https://localhost:5001/Account/Login`
- This request is routed to the **AccountController**.



## ⚙️ Step 2: Controller Handles Request
**File:** `Controllers/AccountController.cs`
```csharp
public IActionResult Login() // Action Method
{
    return View();
}
```
- The controller receives the request.  
- It decides to show the login page → calls the **View** named `Login.cshtml`.



## 🎨 Step 3: View Renders the Page
**File:** `Views/Account/Login.cshtml`
```html
<form method="post" asp-action="Login">
    <input type="text" name="Username" />
    <input type="password" name="Password" />
    <button type="submit">Login</button>
</form>
```
- The **View** generates HTML for the browser.  
- It uses CSS/JS from **wwwroot** for styling and validation.



## 🧠 Step 4: User Submits Form → Controller Receives POST
**File:** `Controllers/AccountController.cs`
```csharp
[HttpPost]
public IActionResult Login(UserModel user) // Parameterized Action Method
{
    if (user.Username == "admin" && user.Password == "123")
        return RedirectToAction("Dashboard");
    return View();
}
```
- The controller now processes the form data.  
- It calls the **Model** to validate credentials.



## 🗃️ Step 5: Model Handles Data
**File:** `Models/UserModel.cs`
```csharp
public class UserModel
{
    public string Username { get; set; } //Properties
    public string Password { get; set; } //Properties
}
```
- The **Model** defines the data structure.  
- In real apps, it would connect to a database to verify credentials.



## 🖼️ Step 6: Controller Returns View
- If login succeeds → `Dashboard.cshtml` is rendered.  
- If fails → `Login.cshtml` is shown again with an error message.



## 🌐 Step 7: View + wwwroot
- `Views/Account/Dashboard.cshtml` displays user info.  
- `wwwroot/css/site.css` styles the page.  
- `wwwroot/js/site.js` handles client-side scripts.



# 🧩 Summary of Folder Roles
| Folder | Purpose | Example in Login Flow |
|---------|----------|----------------------|
| **Controllers/** | Handles requests | `AccountController.cs` |
| **Models/** | Defines data | `UserModel.cs` |
| **Views/** | Renders UI | `Login.cshtml`, `Dashboard.cshtml` |
| **wwwroot/** | Static assets | `site.css`, `site.js` |



This flow mirrors the diagram you saw earlier — request → controller → model → view → response — but now with a concrete example.

---

# 🎮 [What Is a Controller?](https://github.com/Shreyan-Maity/.NetCoreMVC/blob/master/Controllers.md)

understanding what a **Model** is will make the rest of MVC feel much more logical.  

# 🧠 What Is a Model in MVC?

In **ASP.NET Core MVC**, the **Model** is a class represents the **data and business logic** of your application.  
It’s the part that deals with **what your app knows**, not **how it looks** or **how it behaves**.

---

## 🔹 Think of It Like This
- **Model = Data + Rules**
- It defines **what kind of data** your app works with (like users, products, orders)  
  and **how that data behaves** (validation, relationships, calculations).


## 🔹 Example
Let’s say you have a login system.  
Your **Model** might look like this:

```csharp
public class UserModel
{
    public int Id { get; set; }
    public string Username { get; set; }
    public string Password { get; set; }
}
```

This class defines the **structure** of a user — what fields exist and their types.



## 🔹 Why It Exists
| Purpose | Description |
|----------|--------------|
| **Data Representation** | Defines the shape of your data (like a blueprint). |
| **Validation** | Ensures data is correct before saving (e.g., required fields). |
| **Database Mapping** | Works with Entity Framework to connect to tables. |
| **Business Logic** | Contains rules or calculations (e.g., total price, age check). |



## 🔹 How It Connects
- The **Controller** uses the **Model** to fetch or update data.  
- The **View** displays that data to the user.  
- The **Model** itself doesn’t know about the UI — it just holds and manages data.



✅ **In short:**  
The **Model** is the **foundation** of your app’s data — it’s what your app *knows* and *stores*.  
Without it, your Controller and View would have nothing meaningful to work with.

---
Let’s unpack what **Views** are and why they’re so important.  



# 🎨 What Is a View in MVC?

In **ASP.NET Core MVC**, a **View** is the **presentation layer** — it’s what the user actually sees in the browser.  
It’s responsible for **displaying data** that the **Controller** sends, using HTML, CSS, and sometimes Razor syntax (`@`).

---

## 🔹 Think of It Like This
- **Model** → Data (what you have)  
- **Controller** → Logic (what you do)  
- **View** → Presentation (what you show)

So, the **View** turns your data into a beautiful, readable webpage.



## 🔹 Example: `Views/Home/Index.cshtml`
```html
@model UserModel

<h1>Welcome, @Model.Username!</h1>
<p>Your email: @Model.Email</p>
```
- The `@model` directive tells the View what data type it’s receiving.  
- `@Model.Username` displays the value passed from the Controller.



## 🔹 How It Works
1. **Controller** calls `return View(model);`  
2. MVC looks for a matching `.cshtml` file in `Views/<ControllerName>/<ActionName>.cshtml`.  
3. The **View** renders HTML using the data from the **Model**.  
4. The browser displays the final page.



## 🔹 Folder Structure
| Folder | Purpose |
|---------|----------|
| `Views/Home/` | Views for `HomeController` |
| `Views/Shared/` | Common layouts like `_Layout.cshtml` |
| `Views/_ViewStart.cshtml` | Defines layout used by all views |
| `Views/_ViewImports.cshtml` | Imports namespaces and tag helpers |



## 🔹 Razor Syntax Highlights
| Syntax | Purpose | Example |
|---------|----------|----------|
| `@Model.Property` | Display data | `@Model.Username` |
| `@if(...) { ... }` | Conditional rendering | `@if(Model.IsAdmin){<p>Admin</p>}` |
| `@foreach(...) { ... }` | Loop through data | `@foreach(var item in Model.Users){...}` |



✅ **In short:**  
A **View** is the **face** of your MVC app — it takes data from the Controller and renders it as HTML for the user.

---

# ⚡ What Is `Program.cs`?

- It’s the **starting file** of your MVC project.  
- When you run the app (`dotnet run`), execution begins here.  
- It sets up the **web host**, configures services, and defines the **middleware pipeline**.  

---

## 🔹 Typical `Program.cs` in .NET 6/7
```csharp
// Entry point of the application
var builder = WebApplication.CreateBuilder(args);

// 1️⃣ Register services with Dependency Injection (DI)
// This adds support for Controllers + Views (MVC pattern)
builder.Services.AddControllersWithViews();

// Build the app with the registered services
var app = builder.Build();

// 2️⃣ Configure middleware pipeline
// Middleware = steps every request passes through

// Error handling: show custom error page in production
if (!app.Environment.IsDevelopment())
{
    app.UseExceptionHandler("/Home/Error");
    app.UseHsts(); // Adds HTTP Strict Transport Security
}

// Redirect HTTP → HTTPS
app.UseHttpsRedirection();

// Serve static files (CSS, JS, images from wwwroot)
app.UseStaticFiles();

// Enable routing (maps URLs to controllers/actions)
app.UseRouting();

// Enable authorization (checks user permissions)
app.UseAuthorization();

// 3️⃣ Define default route pattern
// Example: /Home/Index → HomeController.Index()
app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");

// 4️⃣ Run the application (start web server)
app.Run();

```

## 🔹 Key Takeaways
- **Services** → Registered at the top (AddControllersWithViews).

- **Middleware** → Defines request flow (HTTPS → Static Files → Routing → Authorization).

- **Routing** → Maps URLs to Controllers and Actions.

- **app.Run()** → Boots up the server and starts listening for requests.

## 🔹 Breakdown of Responsibilities

| Section | Purpose |
|----------|----------|
| **CreateBuilder** | Sets up the app configuration and DI container. |
| **Services.AddControllersWithViews()** | Registers MVC services (Controllers + Views). |
| **Middleware Pipeline** | Defines how requests flow (HTTPS, static files, routing, authorization). |
| **MapControllerRoute** | Defines default routing (`/Home/Index`). |
| **app.Run()** | Starts the web server. |



## 🔹 Why It Exists
- **Central Setup** → All app-wide configurations live here.  
- **Routing** → Decides how URLs map to Controllers/Actions.  
- **Middleware** → Defines request handling steps (security, static files, etc.).  
- **Execution Start** → Without `Program.cs`, the app wouldn’t know how to run.  



✅ **In short:**  
`Program.cs` is the **bootstrapper** of your MVC app — it wires up services, middleware, and routing, then launches the web server.

Here’s the visual showing how **`Program.cs` orchestrates the middleware pipeline** in an ASP.NET Core MVC app.  



# ⚡ Middleware Pipeline Flow (via `Program.cs`)

1. **User Request** → Browser sends a request (e.g., `/Home/Index`).  
2. **HTTPS Redirection** → Ensures secure connection.  
3. **Static Files** → Serves CSS, JS, images from `wwwroot`.  
4. **Routing** → Matches URL to Controller/Action.  
5. **Authorization** → Checks if user is allowed.  
6. **Controller** → Executes logic, calls Model.  
7. **View** → Renders HTML.  
8. **Response** → Sent back to browser.



# 🧩 Why This Matters
- `Program.cs` defines this exact order.  
- Each middleware is like a **checkpoint** the request passes through.  
- If any middleware blocks (e.g., failed authorization), the request stops there.  
- Otherwise, it flows all the way to the Controller → View → Response.



✅ **In short:**  
`Program.cs` is the **director** of your MVC app — it sets the stage, decides the order of middleware, and ensures every request flows smoothly from browser to response.

---
Since we’ve already covered **Models, Views, Controllers, and Program.cs**, the natural next step is **Routing**.  


# 🛣️ What Is Routing in MVC?

Routing is the system that decides **which Controller and Action method** should handle a given URL request.

---

## 🔹 Default Routing
Defined in `Program.cs`:
```csharp
app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");
```

- **`{controller}`** → Name of the controller (e.g., `HomeController`).  
- **`{action}`** → Method inside the controller (e.g., `Index()`).  
- **`{id?}`** → Optional parameter (e.g., `/Home/Details/5`).  

So `/Home/Index` → `HomeController.Index()`.



## 🔹 Attribute Routing
Instead of relying only on the default route, you can decorate controllers with attributes:

```csharp
[Route("account")]
public class AccountController : Controller
{
    [Route("login")]
    public IActionResult Login()
    {
        return View();
    }

    [Route("register")]
    public IActionResult Register()
    {
        return View();
    }
}
```

Now:
- `/account/login` → `Login()`  
- `/account/register` → `Register()`



## 🔹 Why Routing Matters
| Benefit | Explanation |
|----------|--------------|
| **Clean URLs** | `/products/details/10` looks better than query strings. |
| **Flexibility** | You can define custom routes for SEO-friendly links. |
| **Control** | Decide exactly which controller/action handles each request. |



✅ **In short:**  
Routing is the **map** of your MVC app — it connects URLs to the right controller actions.

---
Alright, let’s compare **Convention-based Routing vs Attribute Routing** side by side so you can see when each is useful.  



# 🛣️ Routing Approaches in ASP.NET Core MVC

## 🔹 Convention-based Routing
Defined globally in `Program.cs`:
```csharp
app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");
```

### Example
```csharp
public class ProductsController : Controller
{
    public IActionResult Details(int id)
    {
        return View();
    }
}
```

- URL: `/Products/Details/10`  
- Maps automatically to `ProductsController.Details(10)`  
- ✅ Best for **standard patterns** and when most controllers follow the same structure.



## 🔹 Attribute Routing
Defined directly on controllers/actions with `[Route]` attributes:
```csharp
[Route("store")]
public class ProductsController : Controller
{
    [Route("item/{id}")]
    public IActionResult Details(int id)
    {
        return View();
    }
}
```

- URL: `/store/item/10`  
- Maps to `ProductsController.Details(10)`  
- ✅ Best for **custom, SEO-friendly, or complex routes**.



# 📊 Side-by-Side Comparison

| Feature | Convention Routing | Attribute Routing |
|---------|--------------------|-------------------|
| **Defined in** | `Program.cs` | Controller/Action attributes |
| **URL Style** | Standard (`/Controller/Action/Id`) | Custom (`/store/item/10`) |
| **Flexibility** | Limited | Very flexible |
| **Best Use Case** | Simple apps with predictable routes | Complex apps needing custom URLs |



✅ **In short:**  
- Use **Convention Routing** for simplicity and consistency.  
- Use **Attribute Routing** when you need fine-grained control over URLs.  

---
Great flow so far, since we’ve covered **Models, Views, Controllers, Program.cs, and Routing**, the next natural topic in the MVC journey is **Middleware**.  

# ⚡ What Is Middleware in ASP.NET Core?

Middleware is like a **pipeline of components** that every HTTP request passes through before reaching your Controller.  
Each middleware can **inspect, modify, or short-circuit** the request/response.

---

## 🔹 Key Middleware Examples
- **UseHttpsRedirection()** → Forces HTTPS.  
- **UseStaticFiles()** → Serves CSS, JS, images from `wwwroot`.  
- **UseRouting()** → Matches URLs to controllers/actions.  
- **UseAuthorization()** → Checks if the user is allowed.  
- **UseExceptionHandler()** → Handles errors gracefully.  


## 🔹 How Middleware Works
1. Request enters the pipeline.  
2. Each middleware runs in order (defined in `Program.cs`).  
3. Middleware can:
   - Pass the request to the next middleware.  
   - Modify the request/response.  
   - Stop the pipeline (e.g., return an error).  
4. Finally, the Controller handles the request if it reaches that stage.  


## 🔹 Example Custom Middleware
```csharp
app.Use(async (context, next) =>
{
    Console.WriteLine("Request: " + context.Request.Path);
    await next(); // Pass to next middleware
    Console.WriteLine("Response: " + context.Response.StatusCode);
});
```
This logs every request and response.


✅ **In short:**  
Middleware is the **chain of responsibility** in ASP.NET Core — each piece decides how requests and responses are handled before reaching your Controller.

Here’s the visual breakdown of the **Middleware Pipeline in ASP.NET Core MVC**, Shreyan — showing how every request flows through the components defined in `Program.cs`.  

# ⚡ Middleware Pipeline Flow

1. **User Request** → Browser sends a request (e.g., `/Home/Index`).  
2. **UseHttpsRedirection()** → Ensures secure HTTPS connection.  
3. **UseStaticFiles()** → Serves CSS, JS, and images from `wwwroot`.  
4. **UseRouting()** → Matches the URL to the correct Controller/Action.  
5. **UseAuthorization()** → Checks if the user has permission.  
6. **Controller** → Executes logic, may call Models for data.  
7. **View** → Renders HTML with Razor.  
8. **Response** → Sent back to the browser.

# 🧩 Why Middleware Matters
- It’s a **chain of responsibility** — each middleware decides whether to pass the request forward or stop it.  
- The **order matters** — if you place `UseAuthorization()` before `UseRouting()`, it won’t work correctly.  
- You can add **custom middleware** to log requests, handle caching, or inject headers.

✅ **In short:**  
Middleware is the **pipeline** that shapes every request and response in your MVC app. It’s defined in `Program.cs` and runs in the exact order you configure.

---
