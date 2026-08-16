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
### 🛠️ [Create Custom Middleware Class](https://github.com/Shreyan-Maity/.NetCoreMVC/blob/master/Custom_Middleware.md)

### 🛠️ [Custom Error-handling Middleware Class](https://github.com/Shreyan-Maity/.NetCoreMVC/blob/master/Custom_Error_Handeling_Middleware.md)
