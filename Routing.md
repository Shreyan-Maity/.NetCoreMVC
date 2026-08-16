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

