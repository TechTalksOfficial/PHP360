### **Lecture 11: Error and Exception Handling**

#### **Overview**  
This lecture delves into **Error and Exception Handling** in PHP. Proper error management ensures your application is robust, secure, and user-friendly, even in the face of unexpected issues. By mastering these concepts, you can handle runtime errors effectively and provide meaningful feedback to users while keeping your code maintainable.  

---

#### **Topics Covered**  
1. Types of Errors in PHP (Parse, Fatal, Warning, Notice)  
2. Using `error_reporting()` to Control Error Visibility  
3. Custom Error Handling with `set_error_handler()`  
4. Understanding Exceptions and the `try-catch` Block  
5. Throwing Custom Exceptions  
6. Logging Errors for Debugging  

---

### **Directory Structure**  

```  
Lecture11_ErrorAndExceptionHandling/  
│  
├── errorBasics.php           // Demonstrates basic error handling  
├── customErrorHandler.php    // Implements a custom error handler  
├── exceptionHandling.php     // Explains try-catch blocks  
├── customException.php       // Demonstrates custom exceptions  
├── errorLogging.php          // Example of error logging in PHP  
├── README.md                 // Detailed explanation of error and exception handling  
```  

---

### **File Descriptions**  

1. **errorBasics.php**  
   - **Purpose**: Introduces basic PHP errors and how to control error reporting using `error_reporting()` and `display_errors`.  

2. **customErrorHandler.php**  
   - **Purpose**: Implements a custom error handler using `set_error_handler()` to gracefully manage errors.  

3. **exceptionHandling.php**  
   - **Purpose**: Demonstrates the use of `try-catch` blocks to handle exceptions effectively.  

4. **customException.php**  
   - **Purpose**: Shows how to create and throw custom exceptions for application-specific error scenarios.  

5. **errorLogging.php**  
   - **Purpose**: Explains how to log errors to a file for debugging and monitoring purposes using `error_log()`.  

6. **errorConcepts.md**  
   - **Purpose**: Provides a comprehensive explanation of error and exception handling in PHP with examples.  

---

### **Key Concepts**

#### **1. Types of Errors in PHP**  
PHP errors can be classified into the following categories:  
- **Parse Errors**: Issues in code structure, like missing a semicolon.  
- **Fatal Errors**: Execution stops due to critical issues, like calling an undefined function.  
- **Warnings**: Non-fatal issues; script continues running but needs attention.  
- **Notices**: Minor issues, like using an undefined variable.  

#### **Example:**  
```php  
// Trigger a notice  
echo $undefinedVariable;  

// Trigger a warning  
include('nonexistentFile.php');  

// Trigger a fatal error  
nonExistentFunction();  
```  

---

#### **2. Exception Handling**  
Exceptions are a way to gracefully handle runtime errors in PHP. Use `try-catch` blocks to catch exceptions and execute fallback code.  

**Example:**  
```php  
try {  
    $file = fopen("nonexistentFile.txt", "r");  
    if (!$file) {  
        throw new Exception("File not found.");  
    }  
} catch (Exception $e) {  
    echo "Error: " . $e->getMessage();  
}  
```  

---

#### **3. Custom Error Handling**  
Use `set_error_handler()` to define your own error-handling logic.  

**Example:**  
```php  
function customErrorHandler($errno, $errstr) {  
    echo "Custom Error: [$errno] $errstr";  
}  

set_error_handler("customErrorHandler");  

// Trigger an error  
echo 10 / 0;  
```  

---

#### **4. Error Logging**  
Log errors to a file for debugging and monitoring using `error_log()`.  

**Example:**  
```php  
// Log a custom error message  
error_log("An error occurred in the script.", 3, "errors.log");  
```  

---

### **Best Practices**  
- Avoid displaying detailed errors to users; use error logging instead.  
- Always handle exceptions using `try-catch` blocks.  
- Use custom error handlers for application-specific error scenarios.  
- Follow PHP’s error levels and use `error_reporting()` for control.  

---

### **Conclusion**  
Effective error and exception handling ensures a smooth user experience and simplifies debugging for developers. It is an essential skill for creating robust and maintainable applications.  

In the next lecture, we will explore **PHP and MySQL Integration**, learning how to connect to databases and perform essential CRUD operations (Create, Read, Update, Delete) to manage data effectively.