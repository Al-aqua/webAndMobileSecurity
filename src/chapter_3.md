# **3. Authentication and Authorization**

Authentication and authorization are the cornerstones of secure web and mobile applications. This chapter focuses on implementing these concepts securely using Pure PHP and Laravel frameworks.

______________________________________________________________________

## **3.1 Understanding Authentication vs. Authorization**

- **Authentication**: The process of verifying the identity of a user (e.g., login systems).
- **Authorization**: The process of determining what resources a user has access to after authentication.

Example:

- A user logging into a system is authentication.
- Granting that user access to admin features is authorization.

______________________________________________________________________

## **3.2 Pure PHP Implementation**

### **3.2.1 Building Secure Login and Registration Systems**

- **User Registration:**
  - Collect user details (e.g., email, username, password).
  - Hash passwords using `password_hash()` before storing them in the database.

```php
<?php
$hashedPassword = password_hash($password, PASSWORD_BCRYPT);
// Store $hashedPassword in the database
?>
```

- **User Login:**
  - Verify passwords securely using `password_verify()`.

```php
<?php
if (password_verify($inputPassword, $storedHashedPassword)) {
    echo "Login successful!";
} else {
    echo "Invalid credentials!";
}
?>
```

### **3.2.2 Implementing Role-Based Access Control (RBAC)**

1. Assign roles to users (e.g., Admin, Editor, Viewer).
1. Store user roles in the database.
1. Restrict access based on roles.

```php
<?php
if ($userRole === 'Admin') {
    echo "Welcome, Admin!";
} else {
    echo "Access denied!";
}
?>
```

### **3.2.3 Protecting Sessions and Mitigating Session Hijacking**

- **Best Practices:**
  - Use `session_start()` securely with `session_regenerate_id()`.
  - Set session cookies with the `HttpOnly` and `Secure` flags.

```php
<?php
session_start();
session_regenerate_id(true);
$_SESSION['user'] = $username;
?>
```

- **Prevent Session Fixation:**
  - Regenerate session IDs after login.
  - Set strict session timeout policies.

______________________________________________________________________

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

______________________________________________________________________

## **3.4 Hands-On Activities**

1. **Build a Simple Authentication System in Pure PHP:**

   - Create a secure login and registration form.
   - Protect sessions and implement RBAC.

1. **Implement Laravel Authentication:**

   - Scaffold authentication and customize login workflows.
   - Add role-based access control.

1. **Secure an API with Laravel Sanctum:**

   - Build a token-based API.
   - Protect endpoints with middleware.
