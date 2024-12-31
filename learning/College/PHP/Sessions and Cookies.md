# **Sessions**
- A **session** is a way to store information across multiple pages.
- PHP session store data on the server, making them more secure compared to cookies.

### **Starting a session**
```php
session_start()
```

### **Registering a session variable**
```php
$_SESSION['username'] = "Tushar Sharma";
```

### **Destroying a session**
```php
session_destroy();
```



# **Cookies**

- A **cookie** is a small file stored on the clients computer by the browser.
- Cookies can hold a small amount of data and are used for tracking or storing user preferences.

### **Setting cookies in PHP**

```php
setcookie("username", "Tushar", time()+ (86400 * 30), "/");
```

### **Using cookies with sessions**

- Store session Ids using cookies.
```php
session_start();
if(!isset($_COOKIE['PHPSESSIONID'])){
	echo "Cookie is not set."
}
```

### **Deleting a cookie**

- to unset a cookie, delete its value and set the expiration date to past time.
```php
if (isset($_COOKIE['username'])) {
    unset($_COOKIE['username']);
    setcookie("username", "", time() - 3600, "/");
    echo "Cookie 'username' has been unset.";
}
```



### **Unset V/S Destroy**

| Aspect              | Unsetting Variables                     | Destroying the Session                    |
| ----------------------- | ------------------------------------------- | --------------------------------------------- |
| **Scope**               | Affects specific variables only.            | Ends the entire session.                      |
| **Session Persistence** | The session remains active.                 | The session is invalidated.                   |
| **Session File**        | Session file on the server is retained.     | Session file is deleted from the server.      |
| **Use Case**            | When you need to remove specific data only. | When you want to log out or clear everything. |


#### Best Practices

- Use secure and HTTP-only cookies for sensitive data.
- Always validate and sanitize session data to prevent session hijacking.
- Implement session timeouts to enhance security.

#### Best Practices for File Handling

- Always validate and sanitize file inputs to prevent security vulnerabilities.
- Use proper error handling with `try-catch` blocks or error-checking functions.
- Set appropriate permissions for uploaded files and directories.
- Avoid overwriting existing files by checking if a file exists before performing write operations.