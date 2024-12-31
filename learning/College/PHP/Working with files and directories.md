- **File** - a collection of data or information store on the disk.
- **Directory** - a collection of interrelated files or other directories.

### **Opening a file**

- In PHP we can open a file by using the `fopen()` function.
- `fopen()` accepts 2 arguments:
1. path to file.
2. mode of access.

- A file can be opened in 4 modes:
1. `r` - read mode. 
2. `w` - write mode. Creates a new file or overwrites the existing file.
3. `a` - append mode. Create a new file if the file doesn't exists.
4. `x` - Creates a new file for writing. Fails if the file already exists.


- After the required information has been extracted from the file, it is important to close them by using the `fclose()` function.
```php
$file = fopen("example.txt", "r");
if($file){
	echo "File opened successfully";
	fclose($file)
}
```


### **Copying a file**

```php
copy("source.txt", "destination.txt");
```

### **Rename a file**

```php
rename("old_file_name.txt", "new_file_name.txt")
```

### **Delete a file**

```php
unlink("file_to_delete.txt");
```

### **Creating, Scanning and removing directories**
```php
mkdir("new_folder")
```

```php
rmdir("folder_name")
```

```php
$files = scandir(".");
print_r($files);
```

### **File upload**
```html
<form action="upload.php" method="POST" enctype="multipart/form-data">
	<label for="file">Choose file:</label>
	<input type="file" name="fileToUpload" id="file">
	<input type="submit" value="Upload">
</form>
```

```php
if($_SERVER(["Request Method"] == 'POST')){
	$targetDir = 'uploads/';
	$targetFileName = $targetDir . basename($_FILES["fileToUpload"]["name"]);
	if(move_uploaded_file($_FILES["fileToUpload"]["tmp_name"], targetFile)){
		echo "The file " . htmlspecialchars(basename($_FILES["fileToUpload"]["name"])) . " has been uploaded.";
    } else {
        echo "Sorry, there was an error uploading your file.";
    }
	
}
```

### **Download**

```php
$file = "example.txt";
if (file_exists($file)) {
    header('Content-Description: File Transfer');
    header('Content-Type: application/octet-stream');
    header('Content-Disposition: attachment; filename="' . basename($file) . '"');
    header('Content-Length: ' . filesize($file));
    readfile($file);
    exit;
}
```

##### `move_uploaded_file()`
- **Purpose**: Moves an uploaded file from a temporary location to a specified destination.
- **Usage**:
    - PHP stores uploaded files in a temporary directory (as specified in the `php.ini` file) during the upload process.
    - `move_uploaded_file()` ensures that the file is safely transferred to its final location.
- **Syntax**:
```php
move_uploaded_file(string $from, string $to): bool
```


###### `file_exists()`

- **Purpose**: Checks if a file or directory exists at a given path.
- **Usage**:
    - Useful for validating paths before performing file operations (e.g., reading, writing, or deleting a file).
- **Syntax**:
```php
file_exists(string $filename): bool
```
