# Junior php interview - episode2

## Questions:

### What is primary key in a database table?


A primary key in a database table is a unique identifier for each row or record in the table. Imagine you have a big table with lots of information about different people or things, like a list of students in your school. Each student has a unique student ID number, like a special code just for them. This special code is their "primary key."
This primary key is essential because it makes sure that no two students have the same code. It's like each student gets their own secret number, and no two students can have the same secret number.
Why is this important? Well, let's say you want to find information about a specific student, like their name, grade, or teacher. You can use their secret number (primary key) to quickly find exactly the right student in the table. It's like a magic key that helps you unlock the information you need.
Also, this magic key makes sure that there are no duplicate students in the table. Imagine if two students had the same secret number; that would be confusing, right? So, the primary key helps keep everything organized and prevents any mix-ups.

In summary, a primary key is like a unique secret code for each item in a table. It helps you find things quickly and ensures that there are no duplicates, making everything neat and tidy in the database. Common examples of primary keys include auto-incrementing integers, globally unique identifiers (GUIDs), or natural keys like social security numbers, email addresses, or product codes, depending on the specific requirements of the database and the nature of the data being stored.

## How you can redirect from one url to another using php ?
Redirecting from one URL to another in PHP is a common task, often used for purposes like sending a user to a different page after a form submission, or redirecting to a new site location after a URL change. This can be accomplished using the header() function in PHP. Here's a basic guide on how to do it:

- Using the header() Function:

  The header() function is used to send raw HTTP headers to the browser. To perform a redirect, you can use the Location header.

- Basic Redirect:
  To redirect to a different URL, you would use the header() function like this:
  ```
  header("Location: http://www.example.com");
  exit();
  ```

- Exit After Redirect:
  
    It's important to call exit() after sending the location header. This stops the execution of the current script, ensuring that no further code is executed which could interfere     with the redirection.

  


While the header() function defaults to a 302 Found HTTP status code, indicating a temporary redirect, you can specify a different status code if needed, such as 301 Moved Permanently for permanent redirects:

```
header("Location: http://www.example.com", true, 301);
```


