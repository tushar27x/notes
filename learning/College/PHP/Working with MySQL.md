### **Establishing connection**

- In PHP we can connect to a `mysql` database using either `mysqli` of `pdo` extensions.
```php
$servername = "localhost";
$username = "root";
$pass = "root";
$dbname = "test";

$conn = new mysqli($servername, $username, $pass, $dbname);
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
echo "Connected to DB successfully"
```


#### **Performing Basic Database Operations (DML)**

- **INSERT**:
```php
$sql = "INSERT INTO users (username, email) VALUES ('JohnDoe', 'john@example.com')";
if ($conn->query($sql) === TRUE) {
    echo "New record created successfully";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}
```

- **DELETE**:

```php
$sql = "DELETE FROM users WHERE id=1";
if ($conn->query($sql) === TRUE) {
    echo "Record deleted successfully";
} else {
    echo "Error deleting record: " . $conn->error;
}
```

- **UPDATE**:
```php
$sql = "UPDATE users SET email='john_updated@example.com' WHERE id=1";
if ($conn->query($sql) === TRUE) {
    echo "Record updated successfully";
} else {
    echo "Error updating record: " . $conn->error;
}
```

- **SELECT**:

```php
$sql = "SELECT id, username, email FROM users";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Name: " . $row["username"]. " - Email: " . $row["email"] . "<br>";
    }
} else {
    echo "0 results";
}
```

#### 3. Setting Query Parameters

- Use prepared statements to set query parameters and prevent SQL injection.

```php
$stmt = $conn->prepare("INSERT INTO users (username, email) VALUES (?, ?)");
$stmt->bind_param("ss", $username, $email);

$username = "JaneDoe";
$email = "jane@example.com";
$stmt->execute();

echo "New record created successfully";
$stmt->close();
```

#### 4. Executing Joins

- **Cross Join**: Returns the Cartesian product of two tables.

```sql
SELECT * FROM table1 CROSS JOIN table2;
```

- **Inner Join**: Returns records that have matching values in both tables.

```sql
SELECT users.id, users.username, orders.order_date
FROM users
INNER JOIN orders ON users.id = orders.user_id;
```

- **Left Outer Join**: Returns all records from the left table and matched records from the right table. Unmatched records will have NULLs.

```sql
SELECT users.id, users.username, orders.order_date
FROM users
LEFT JOIN orders ON users.id = orders.user_id;
```

- **Right Outer Join**: Returns all records from the right table and matched records from the left table. Unmatched records will have NULLs.

```sql
SELECT users.id, users.username, orders.order_date
FROM users
RIGHT JOIN orders ON users.id = orders.user_id;
```

- **Self Join**: Joins a table to itself to create a hierarchical relationship.

```sql
SELECT e1.id AS EmployeeID, e1.name AS EmployeeName, e2.name AS ManagerName
FROM employees e1
LEFT JOIN employees e2 ON e1.manager_id = e2.id;
```