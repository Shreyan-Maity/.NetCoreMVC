Perfect, let’s build a **custom middleware class** step by step. This way, instead of writing inline middleware in `Program.cs`, you’ll have a reusable component you can plug into any project.  

# 🛠️ Step 1: Create Middleware Class
```csharp
public class RequestLoggingMiddleware
{
    private readonly RequestDelegate _next;

    public RequestLoggingMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        // Before request
        Console.WriteLine("➡️ Incoming Request: " + context.Request.Path);

        await _next(context); // Pass to next middleware

        // After response
        Console.WriteLine("⬅️ Outgoing Response: " + context.Response.StatusCode);
    }
}
```

# 🛠️ Step 2: Create Extension Method
This makes it easy to add the middleware in `Program.cs`:
```csharp
public static class RequestLoggingMiddlewareExtensions
{
    public static IApplicationBuilder UseRequestLogging(this IApplicationBuilder builder)
    {
        return builder.UseMiddleware<RequestLoggingMiddleware>();
    }
}
```


# 🛠️ Step 3: Register in `Program.cs`
```csharp
var builder = WebApplication.CreateBuilder(args);
builder.Services.AddControllersWithViews();

var app = builder.Build();

// Add custom middleware here
app.UseRequestLogging();

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
- Every request logs its **path** before hitting the next middleware.  
- Every response logs its **status code** after the pipeline finishes.  
- You can expand this to log headers, execution time, or even write to a file/database.


✅ **In short:**  
A custom middleware is just a class with an `InvokeAsync` method. You register it in `Program.cs`, and it becomes part of the request pipeline.
