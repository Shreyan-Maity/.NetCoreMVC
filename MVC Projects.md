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
