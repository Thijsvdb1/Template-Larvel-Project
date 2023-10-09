<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

## Instructie Project.

Laravel 10 User Roles and Permissions Tutorial - ItSolutionStuff.com

Je zal nog de 2 seeders moeten pushen zodat je de admin-user aanmaakt en de permissions. Migrations moet je ook pushen, dit doe je verder allemaal in de commandline. En de database connecten/aanmaken. Verder zou het moeten werken.

## Bronnen.

- https://www.digitalocean.com/community/tutorials/simple-laravel-crud-with-resource-controllers
    This is needed for the 'web.php' file, Here you see resource Paths/Routes and that works great and simple 

- https://laravel.com/docs/10.x/migrations#foreign-key-constraints
    This is for Migrations = Search for: Foreign Key Constraints (ctrl+F). This is for a many to many relation, (table migration code).
  
- https://www.tutsmake.com/laravel-10-joins-example-tutorial/
    This is for Inner Joins
  
- https://spatie.be/docs/laravel-permission/v5/basic-usage/blade-directives
    This is for Roles/Permissions you can use @role('Rolename')
  
- https://www.laravelia.com/post/laravel-9-update-user-profile-tutorial#:~:text=We%20will%20open%20the%20".,create%20laravel%20update%20user%20profile.&text=And%20run%20npm%20i%20and%20npm%20run%20dev%20to%20compile%20javascript%20assets.&text=Here%2C%20we%20need%20to%20add,that%20route%20in%20the%20web.
  (Deze werkt maar moeten wel wat dingen toegevoegd worden zoals, uses inde web.php, styling inde blade, en returns met routes, en inde controller: namespace App\Http\Controllers\Admin;  Hier moet admin weg anders krijg je een error)

- https://techtoolindia.com/how-to-change-password-in-laravel-9

- https://www.itsolutionstuff.com/post/laravel-10-user-roles-and-permissions-tutorialexample.html
  Het hele begin/crud gedeelte
  
- https://www.educative.io/answers/how-to-implement-search-in-laravel
  This is for a Search bar

- https://techvblogs.com/blog/get-data-between-two-dates-laravel
  Get data between 2 dates.
  
- To give a new user a role when created u have to be in the auth register controller, remove the first return so that it doesn't close. then this:

```
  protected function create(array $data)
    {
        $user =  User::create([
            'name' => $data['name'],
            'email' => $data['email'],
            'password' => Hash::make($data['password']),

        ]);

            $user->assignRole('Name_of_the_Role');
            return $user;
    }
```
every user that is created gets the 'Name_of_the_Role' role, Now u only need to give the customer certain permissions and you good to go. 
  

