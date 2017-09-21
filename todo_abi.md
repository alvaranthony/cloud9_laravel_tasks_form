#juurkaustas, loome uue projekti kausta
composer create-project --prefer-dist laravel/laravel todo

#muuda .env faili (pane andmebaasi kastuaja ja andmebaasi nimi paika)

#loome tabeli loomiseks "migratsiooni" faili-fassaadi
php artisan make:migration create-tasks_table --create=tasks
#lisasime "tasks" tabeli up funktsiooni $table->string('name');

#mariaDB-d kasutades tuleb muuta app->providers->AppServiceProvider.php faili
php artisan migrate

#loob Task mudeli(Task.php) app kausta
php artisan make:model Task