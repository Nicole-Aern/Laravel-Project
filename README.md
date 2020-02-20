<p align="center">My first project in LARAVEL</p>
<p align="center">Laravel Framework 5.7.11</p>

1) Install MYSQL
2) Install PHP 7.2
3) Install Apache 2
4) Install Workbench mysql  and create our database with the columns and fields that we want:
<img src="https://raw.githubusercontent.com/Nicole-Aern/Laravel-Project/master/docs/images/workbench.png">

5) Via Composer Create-Project:
  a) composer install
  b) composer update
  c) composer create-project --prefer-dist laravel/laravel newproject

6) Before using Laravel's encrypter, you must set a key option in your config/app.phpconfiguration file. You should use the php artisan key:generate command to generate this key since this Artisan command will use PHP's secure random bytes generator to build your key

7) We set up a quick database so we can do all of our CRUD
functionality:
php artisan make:migration create_people_table
<img src="https://raw.githubusercontent.com/Nicole-Aern/Laravel-Project/master/docs/images/workbench_2.png">

8) Now from the command line run this migration. Our database now has a people table to house all of the people we CRUD (create, read, update, and delete):
<img src="https://raw.githubusercontent.com/Nicole-Aern/Laravel-Project/master/docs/images/workbench_3.png">
  php artisan migrate

We create all the fields that we want in our database

9) Create Eloquent model :

Each database table has a corresponding "Model" which is used to interact with that table. Models allow you to query for data in your tables, as well as insert new records into the table.

Models lives in the app directory
In the app/models folder, let's create a People.php model:
php artisan make:model People
<img src="https://raw.githubusercontent.com/Nicole-Aern/Laravel-Project/master/docs/images/code.png">

10) Creating the Controller
To create our Controller we have to use :
php artisan make:controller PeopleController
<img src="https://raw.githubusercontent.com/Nicole-Aern/Laravel-Project/master/docs/images/code_2.png">

11) Setting Up the Routes
With this Command we can see what list root we have :
php artisan route:list
<img src="https://raw.githubusercontent.com/Nicole-Aern/Laravel-Project/master/docs/images/cli_routes.png">

We have also and this for the roots :
  route:cache
  route:clear

We have also two different ways to create routes

  a) Route::resource('people', 'PeopleController');

  with this we create all RESTful action with one command

  b) Route::get('/people', 'PeopleController@index');
  Route::get('/people', 'PeopleController@create');
  Route::post('/people', 'PeopleController@store');
  Route::get('/people', 'PeopleController@show');
  Route::get('/people', 'PeopleController@edit');
  Route::put('/people', 'PeopleController@update');
  Route::patch('/people', 'PeopleController@update');
  Route::delete('/people', 'PeopleController@destroy');

12) Forms & HTML

Begin by installing this package through Composer. Run the following
from the Terminal:

composer require "laravelcollective/html":"^5.7.11"

Next, add your new provider to the providers array of config/app.php:

  'providers' => [
  // ...
  Collective\Html\HtmlServiceProvider::class,
  // ...
  ],
  Finally, add two class aliases to the aliases array of config/app.php:
  'aliases' => [
  // ...
  'Form' => Collective\Html\FormFacade::class,
  'Html' => Collective\Html\HtmlFacade::class,
  // ...
  ],

13) When using {{ Form::open() }}, Laravel will automatically create a hidden input field with a token to protect from cross-site request CSRF forgeries.

14) Routing
Laravel provides a quick way to scaffold all of the routes and views you need for authentication using one simple command:
php artisan make:auth

15) Middleware provide a convenient mechanism for filtering HTTP requests entering your application. For example, Laravel includes a middleware that verifies the user of your application is authenticated. If the user is not authenticated, the middleware will redirect the user to the login screen. 

16) php artisan make:auth
with this command we can make all of the routes and views you need for authentication .

We create :LoginController, RegisterController, ResetPasswordController, and VerificationController

Also the make:auth command will also create a resources/views/layouts directory containing a base layout for your application. All of these views use the Bootstrap CSS framework, but you are free to customize them however you wish.
