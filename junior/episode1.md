# Junior php interview - episode1

#### Questions:
- [What is the difference between include() and require() in PHP? When would you use each one?](#what-is-the-difference-between-include---and-require---in-php-when-would-you-use-each-one)
- [How does PHP handle sessions and what are the methods to store session data](#how-does-php-handle-sessions-and-what-are-the-methods-to-store-session-data)
- [What are access modifiers in PHP? What is their purpose and how are they used?](#what-are-access-modifiers-in-php-what-is-their-purpose-and-how-are-they-used)
- [What is the difference between an abstract class and an interface in PHP?](#what-is-the-difference-between-an-abstract-class-and-an-interface-in-php)
- [How do you check if a file exists in PHP? What function do you use?](#how-do-you-check-if-a-file-exists-in-php-what-function-do-you-use-)




### What is the difference between include() and require() in PHP? When would you use each one?​
In PHP, both include() and require() functions are used to include the contents of a file in another PHP file. The difference between them is how they handle errors.


When you use include() to include a file, and the file cannot be found or loaded, PHP will issue a warning, but the script will continue to run.

On the other hand, when you use require() to include a file, and the file cannot be found or loaded, PHP will issue a fatal error and stop the script from running.

Here are some guidelines on when to use each function:

- Use include() when the included file is not critical to the execution of the script. For example, if the file contains non-essential functions, or if it is optional and may not always exist.

- Use require() when the included file is essential to the execution of the script. For example, if the file contains important configuration settings, or if it contains functions that are required for the rest of the script to work correctly.

### How does PHP handle sessions and what are the methods to store session data

Sessions are used to maintain data across multiple HTTP requests in PHP. When a user visits a PHP website, a unique session ID is generated for the user, which is stored as a cookie in the user's browser or passed as a parameter in the URL. This session ID is used to retrieve session data stored on the server-side for that user.

In PHP, session data can be stored in various ways, including:

- File-based sessions: This is the default method of storing session data in PHP. Session data is stored in a file on the server, with the filename being the session ID. This method is easy to set up and requires no additional configuration, but can be slow if there are many concurrent users.

- Database-based sessions: Session data is stored in a database table. This method is faster than file-based sessions and can handle more concurrent users, but requires additional configuration.

- In-memory sessions: Session data is stored in memory, either on the server or in a distributed cache such as Redis or Memcached. This method is the fastest and can handle the most concurrent users, but requires additional setup and can be more expensive.

To use sessions in PHP, the session_start() function must be called at the beginning of every page that uses sessions. This function starts a new session or resumes an existing one based on the session ID passed in the request. Session data can be stored and retrieved using the $_SESSION superglobal array.

To store session data, you simply assign a value to a key in the $_SESSION array, like so:

```
$_SESSION['username'] = 'John';
```
To retrieve session data, you can simply access the value from the $_SESSION array:
```
$username = $_SESSION['username'];
```
To destroy a session, you can use the session_destroy() function, which will delete the session data from the server and remove the session ID cookie from the user's browser:
```
session_destroy();
```
### What are access modifiers in PHP? What is their purpose and how are they used?​

Access modifiers in PHP are keywords used to control the visibility and accessibility of class properties and methods. There are three access modifiers in PHP:

1. public: Public properties and methods can be accessed from anywhere, both inside and outside the class.

2. protected: Protected properties and methods can only be accessed from within the class or its subclasses.

3. private: Private properties and methods can only be accessed from within the class itself, not from its subclasses or from outside the class.

The purpose of access modifiers is to enforce encapsulation and prevent external code from modifying or accessing the internal state of an object in unexpected ways. By limiting the visibility of certain properties and methods, you can ensure that they are only accessed and modified in the intended way, which can help prevent bugs and make your code more maintainable.

### What is the difference between an abstract class and an interface in PHP?​
In PHP, both abstract classes and interfaces provide a way to define a set of methods that must be implemented by classes that use them. However, there are several differences between the two:

- Implementation: An abstract class can include both abstract and non-abstract methods, while an interface can only include method signatures (i.e. method names and arguments) without any implementation.

- Multiple inheritance: A class can extend only one abstract class, but it can implement multiple interfaces.

- Visibility: The methods in an interface are by default public, while in an abstract class they can have any visibility (public, protected, or private).

- Instantiation: An abstract class cannot be instantiated on its own, while an interface cannot be instantiated at all.

Overall, abstract classes are useful when you want to provide a base implementation for a group of related classes, while interfaces are useful when you want to define a set of methods that must be implemented by unrelated classes.

### How do you check if a file exists in PHP? What function do you use? ​

In PHP, you can check if a file exists using the file_exists() function. The function takes a single argument, which is the path to the file you want to check. The function returns true if the file exists and is accessible, and false otherwise.

Here's an example of how to use file_exists() function:
```
<?php
$file = 'example.txt';

if (file_exists($file)) {
    echo "File exists.";
} else {
    echo "File does not exist.";
}
?>
```

It's important to note that the file_exists() function does not differentiate between files and directories. If you want to check specifically if a file exists (as opposed to a directory), you can use the is_file() function in combination with file_exists(). Here's an example:
```
<?php
$file = 'example.txt';

if (file_exists($file) && is_file($file)) {
    echo "File exists.";
} else {
    echo "File does not exist or is not a file.";
}
?>
```