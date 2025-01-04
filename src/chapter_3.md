# **3. Authentication and Authorization**

Authentication and authorization are the cornerstones of secure web and mobile applications. This chapter focuses on implementing these concepts securely using Pure PHP and Laravel frameworks.

---

## **3.1 Understanding Authentication vs. Authorization**

- **Authentication**: The process of verifying the identity of a user (e.g., login systems).
- **Authorization**: The process of determining what resources a user has access to after authentication.

Example:

- A user logging into a system is authentication.
- Granting that user access to admin features is authorization.

---

## **3.2 Pure PHP Implementation**

### **3.2.1 Database Setup: Create a users table to store user data securely.**

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password_hash VARCHAR(255) NOT NULL,
    role VARCHAR(20) DEFAULT 'user',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### **3.2.2 Building Secure Login and Registration Systems**

- **User Registration:**
  - Collect user details (e.g., email, username, password).
  - Hash passwords using `password_hash()` before storing them in the database.

```php
<?php
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $username = htmlspecialchars($_POST['username']);
    $password = $_POST['password'];

    $passwordHash = password_hash($password, PASSWORD_BCRYPT);

    $conn = new mysqli("localhost", "root", "", "php_auth");
    if ($conn->connect_error) {
        die("Connection failed: " . $conn->connect_error);
    }

    $stmt = $conn->prepare("INSERT INTO users (username, password_hash) VALUES (?, ?)");
    $stmt->bind_param("ss", $username, $passwordHash);

    if ($stmt->execute()) {
        echo "Registration successful.";
    } else {
        echo "Error: " . $stmt->error;
    }

    $stmt->close();
    $conn->close();
}
?>

<form method="POST">
    Username: <input type="text" name="username" required><br>
    Password: <input type="password" name="password" required><br>
    <button type="submit">Register</button>
</form>
```

- **User Login:**
  - Verify passwords securely using `password_verify()`.

```php
<?php
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $username = htmlspecialchars($_POST['username']);
    $password = $_POST['password'];

    $conn = new mysqli("localhost", "root", "", "php_auth");
    if ($conn->connect_error) {
        die("Connection failed: " . $conn->connect_error);
    }

    $stmt = $conn->prepare("SELECT password_hash FROM users WHERE username = ?");
    $stmt->bind_param("s", $username);
    $stmt->execute();
    $stmt->bind_result($passwordHash);

    if ($stmt->fetch() && password_verify($password, $passwordHash)) {
        session_start();
        $_SESSION['username'] = $username;
        echo "Login successful.";
    } else {
        echo "Invalid credentials.";
    }

    $stmt->close();
    $conn->close();
}
?>

<form method="POST">
    Username: <input type="text" name="username" required><br>
    Password: <input type="password" name="password" required><br>
    <button type="submit">Login</button>
</form>
```

### **3.2.3 Assignments**

1. **Implementing Role-Based Access Control (RBAC)**

   1. Assign roles to users (e.g., Admin, Editor, Viewer).
   1. Store user roles in the database.
   1. Restrict access based on roles.

Explain the steps you took to implement RBAC in your application.

```

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------
```

2. **Protecting Sessions and Mitigating Session Hijacking**

- **Best Practices:**

  - Use `session_start()` securely with `session_regenerate_id()`.
  - Set session cookies with the `HttpOnly` and `Secure` flags.

- **Prevent Session Fixation:**

  - Regenerate session IDs after login.
  - Set strict session timeout policies.

Explain the steps you took to implement session protection in your application.

```

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------

--------------------------------------------------------------------
```

---

## **3.3 Laravel Implementation**

### **3.3.1 Laravel Authentication Basics**

- Use Laravel’s built-in `auth` scaffolding for rapid implementation.

```bash
php artisan make:auth
```

### **3.3.2 Customizing Authentication Workflows**

- Modify login and registration controllers to add custom logic (e.g., multi-factor authentication).

```php
public function login(Request $request) {
    $credentials = $request->only('email', 'password');

    if (Auth::attempt($credentials)) {
        return redirect()->intended('dashboard');
    }

    return back()->withErrors(['message' => 'Invalid credentials!']);
}
```

### **3.3.3 Implementing Authorization Policies and Gates**

- **Policies:** Define access rules for models.

```bash
php artisan make:policy PostPolicy
```

- Example policy:

```php
public function update(User $user, Post $post) {
    return $user->id === $post->user_id;
}
```

- **Gates:** Define simple authorization checks.

```php
Gate::define('edit-post', function (User $user, Post $post) {
    return $user->id === $post->user_id;
});
```

### **3.3.4 Securing APIs with Passport or Sanctum**

- **Laravel Passport:** Suitable for full OAuth2 authentication.

```bash
composer require laravel/passport
php artisan passport:install
```

- Protect routes using Passport middleware:

```php
Route::middleware('auth:api')->get('/user', function (Request $request) {
    return $request->user();
});
```

- **Laravel Sanctum:** Lightweight token-based authentication.

```bash
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
php artisan migrate
```

### **3.3.5 Best Practices in Laravel Security**

1. Use `bcrypt` for password hashing (default in Laravel).
1. Enable CSRF protection for forms.
1. Validate all input using `FormRequest`.
1. Secure sensitive configuration using environment variables.

---
