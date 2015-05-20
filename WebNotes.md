#General Security Principles
Awareness + Protection = Security

1. Least privilege
  * User privileges should be limited to their own type of data
  * Code should also be limited to their functions
  
2. Simple is more secure
  * Larger systems have more chances to have bugs and vulnerabilities
  
3. Never trust users
  * Be parainoid about it and use caution.
  * Don't email passwords, backup database to thumbdrives, or leave computer logged in 
  
4. Expect the unexpected
  * Security is not reactive
  * Prevent the crime before it happens
  * Edge Cases - Try to predict what the user might try to do

5. Defense in depth
  * Redundant security
  * Have backup securities if one fails
  
6. Security through obscurity
  * Limit the exposed information
  * Example: login form shouldn't tell which piece of information was not correct
  
7. Blacklisting and whitelisting
  * whitelisting - things that are permitted(restricted by default)
  * blacklisting - things that are forbidden

8. Map exposure point and data passageway
  * Think about the incoming data through urls, forms, cookies, and sessions
  * Think about the outcoming data html or js
  * 
  

#PHP

### Configure Registered Globals(Turned off by default in PHP 4.2 and later)
  The standard is to have it off `register_globals = Off`. Otherwise, always initialize global variables yourself. For example, take a look at the following code. 
```
  <?php
    if (check_password($username, $password)){
      $logged_in = true;
    }
    
    if($logged_in){
      // display the page
    }
   ?>
```
You can easily bypass the login by typing in the url bar `http:somesite.com?logged_in = true`. Since we never created the logged_in variable and set it to false, any one can just assign it to true and log in. 


###Using Superglobals(the standard)
```
$_GET['page']
$_PUT['page']
$_COOKIE['page']
$_SESSION['page']

Example:

http://somesite.com?page=1&query=hello
<?php echo $_GET['page'] ?>
<?php echo $_GET['query'] ?>


```
 

  
  
  
  
