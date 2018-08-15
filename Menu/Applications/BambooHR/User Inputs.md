# Send data from a webpage back to our server to be processed

## Build a form(http request)

   name="name" set in the url of html
   method of post is set in the body
    
    <form action="" method="">
      <input type="text" name="name">
      <input type="submit">
    </form>
    
    
   is the data available to you?
          
      <?php 
    if(isset($_POST['name'],$_POST['age'])){
        echo 'Name and age are available';
    }
     ?>


    <form action="index.php" method="post">
        <input type="text" name="name" placeholder="Name">
        <input type="text" name="age" placeholder="Age">
        <input type="submit">
    </form>        

    
### GET
    * <?php 
	print_r($_GET)
 ?>

<form action="index.php" method="get">
	<input type="text" name="name">
	<input type="submit">
</form>

### POST

### Create a form to submit a name to another page to be processed using GET or POST
