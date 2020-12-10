# different-steps-to-make-a-database-connection-in-PHP


 PHP works with Mysql Database using Mysqli and PDO.

    MySQLi (object-oriented)
    MySQLi (procedural)
    PDO

MySQLi Object-Oriented:
    
    <?php
    $servername = "localhost";
    $username = "username";
    $password = "password";
    $db  = "mydb";
    // Create connection
    $conn = new mysqli($servername, $username, $password, $db);

    // Check connection
    if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
    }
    echo "Connected successfully";
    ?> 
    
MySQLi Procedural
    
    <?php
    $servername = "localhost";
    $username = "username";
    $password = "password";
    $db = "mydb";
    // Create connection
    $conn = mysqli_connect($servername, $username, $password, $db);

    // Check connection
    if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
    }
    echo "Connected successfully";
    ?> 

 PDO:
    
    <?php
    $servername = "localhost";
    $username = "username";
    $password = "password";

    try {
    $conn = new PDO("mysql:host=$servername;dbname=myDB", $username, $password);
    // set the PDO error mode to exception
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    echo "Connected successfully";
    } catch(PDOException $e) {
    echo "Connection failed: " . $e->getMessage();
    }
    ?> 
My Blog: https://sleepy-coder.blogspot.com/2020/12/write-different-steps-to-make-database.html
 Happy coding!
