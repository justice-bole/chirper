# Chirper
Chirper is a microblogging web application made with Laravel.

![Chirper Demo](https://github.com/justice-bole/chirper/blob/main/chirper/resources/gif/chirper.gif)

## How it works
- Installation/Setup
  - Install PHP 
		- php artisan serve
		- php artisan breeze: install blade
		- php artisan migrate
	- Install Composer
		- composer require laravel/breeze —dev
	— Configure .env for SQLite.
	- Install Laravel Breeze.
		- Simple authentication features:
			- Login
			- Registration
			- Password reset
			- Email verification
			- Password confirmation
	- Use blade templates for view layer.
	- Populate database with breeze default tables.
  
- Creating chirps
	- Models - interact with tables in database.
	- Migrations - create and modify database tables.
	- Controllers - process requests and return responses.
	- Create MMC with php artisan make::model -mrc
	- Routing
		- Index route displays form and list of chirps.
		- Store route saves new chirps.
		- Middleware:
			- Auth middleware ensures that only logged-in users can access the route.
			- Verified ensures email is verified if email verification is turned on.
	- Use blade and tailwind CSS to create chirp form.
	- Update blade navigation file to add a menu item for desktop and mobile.
	- Add validation to store route (ensure message doesn’t exceed 255char limit).
	- Create “has many” relationship between User and Chirps.
	- Add safe mass assignment to chirps with $fillable property.

- Showing chirps
	- Use Eloquent’s “with” method to eager-load each chirps associated user.
		- Eager load loads both specified tables and matches them directly in two loop throughs/iterations.
	- Returning all chirps at once doesn’t scale well, so use pagination instead in production.
	- Connect user model to chirp model with a “belongs to” relationship.
