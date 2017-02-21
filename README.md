# Restaurant-android-application
The Restaurant App is a mobile reservation system that used for managing reservation and restaurant menu. Admin can manage reservation, restaurant menu and other configurations such as tax and currency code from admin panel on the web and users will be able to see the menu from mobile app and make a reservation. Run under Android platform which is the number one popular mobile operating system right now.
Getting Started
Before doing installation, you need to do the following things:
1. Have a web hosting to store admin panel files and SQL database. Because this
documentation using cpanel, a web hosting with cpanel is recommended.
2. Install tools that requires for developing Android app such as Java Development Kit,
Eclipse, Android SDK and ADT plugin. For updated tutorial about how to install them
please see on Android Developer website here.
Once you do all things above, you can go to the next step.
Installing Admin Panel
To install admin panel, login to your hosting via cpanel, it usually yourwebsite.com/cpanel.
Select File Manager in Files section. It will bring you to File Manager page. On that page create
new folder inside public_html, name it as you like, for example Restaurant. Then upload
Admin_Panel.zip package into that folder and select Extract to extract that package.
Once it done, back to cpanel, go to Databases section and select MySQL® Databases. In MySQL
Databases create new database, database name is up to you. Add username and password to
this database
Go back to cpanel, select PhpMyAdmin in Databases section. You will go to PhpMyAdmin page,
on that page select database that you have just created on the left side and click Import.
Upload db_restaurant.sql by Choose File button and click Go. This will add some tables into
database which are required by admin panel and android app.
Back to File Manager and find variables.php in public_html/YOUR_FOLDER/variables. Open
that file using Code Editor, this file contain some configurations such as database configuration,
in this configuration you need to fill database host name, username, password, and database
name your hosting configuration. Other configurations are access key, google play url, and
contact email. If you change the access key value, you need to also change access key value on
android app similar with this access key value
<?php
// database configuration
$host ="db_host_name";
$user ="db_username";
$pass ="db_pasword";
$database = "database_name";
$connect = new mysqli($host, $user, $pass,$database) or die("Error :
".mysql_error());
// access key to access API
$access_key = "12345";
// google play url
$gplay_url =
"https://play.google.com/store/apps/details?id=your.package.com";
// email configuration
$admin_email = "contact@website.com";
$email_subject = "The Restaurant App: Information Email";
$change_message = "You have change your admin info such as email and or
password.";
$reset_message = "Your new password is ";
...
?>
Next, open close_database.php and connect_database.php located in includes directory
using Code Editor. And find the following code,

include($_SERVER['DOCUMENT_ROOT'].'/YOUR_FOLDER/variables/variables.php');

change YOUR_FOLDER with folder name you have just created inside public_html. For example,
if your folder name is Restaurant. Then the code above will look like this,

include($_SERVER['DOCUMENT_ROOT'].'/Restaurant/variables/variables.php');

Now you can go to admin page through YourWebsite.com/YOUR_FOLDER. Default username
and password is admin. You can start creating category menu and new menu, set tax and
currency code, and also change admin username, password and email.
Importing Android Project
To import The Restaurant App project firstly you need to extract the TheRestaurantApp.zip.
Then, run Eclipse IDE, and select File > Import.... On Import window select Android > Existing
Android Code Into Workspace then click Next. Find The Restaurant App project by clicking
Browse... button then click Finish.

Thank you and enjoy....
