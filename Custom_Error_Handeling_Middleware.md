Perfect, let’s build a **custom error-handling middleware** so you can catch exceptions globally instead of sprinkling `try-catch` blocks across controllers.  

---

# 🛠️ Step 1: Create Middleware Class
```csharp
public class ErrorHandlingMiddleware
{
    private readonly RequestDelegate _next;

    public ErrorHandlingMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        try
        {
            // Pass request to next middleware
            await _next(context);
        }
        catch (Exception ex)
        {
            // Log the error (you can use ILogger here)
            Console.WriteLine($"❌ Exception: {ex.Message}");

            // Return a friendly error response
            context.Response.StatusCode = 500;
            await context.Response.WriteAsync("Something went wrong. Please try again later.");
        }
    }
}
```

# 🛠️ Step 2: Create Extension Method
```csharp
public static class ErrorHandlingMiddlewareExtensions
{
    public static IApplicationBuilder UseErrorHandling(this IApplicationBuilder builder)
    {
        return builder.UseMiddleware<ErrorHandlingMiddleware>();
    }
}
```

# 🛠️ Step 3: Register in `Program.cs`
```csharp
var builder = WebApplication.CreateBuilder(args);
builder.Services.AddControllersWithViews();

var app = builder.Build();

// Add custom error-handling middleware
app.UseErrorHandling();

app.UseHttpsRedirection();
app.UseStaticFiles();
app.UseRouting();
app.UseAuthorization();

app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");

app.Run();
```

# 🔍 What Happens
- Any **unhandled exception** in your pipeline or controllers will be caught here.  
- Instead of crashing, the middleware logs the error and returns a **500 Internal Server Error** with a friendly message.  
- You can expand this to:
  - Log errors to a file or database.  
  - Return JSON error responses for APIs.  
  - Redirect users to a custom error page.  

✅ **In short:**  
This middleware acts as a **global safety net** — it catches exceptions, logs them, and ensures users see a clean error message instead of a crash.
