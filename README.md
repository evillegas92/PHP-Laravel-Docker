# PHP-Laravel-Docker
Laravel sample application with Docker, PHP 7.3 and Composer.

## Instructions to start the project
1. Make sure you have Docker installed.
2. Check out the repo.
3. At the root folder of the repo, run ```docker-compose build``` to build the PHP docker image specified by the PHP.Dockerfile.
4. Then run ```docker-compose up``` to run the two container images (NGinx web server and the PHP image).
5. Finally open a browser in Windows normally and browse to http://127.0.0.1:82/, you should see the Laravel home page.
6. Now you can start editing files inside the folder named app.


## Manual steps performed prior to create the Laravel project (just as FYI,  for troubleshooting)
1. Create Laravel application: Open a shell inside the PHP container that is running, run ```cd /app``` and then run the Composer command to create an empty Laravel application: ```composer create-project --prefer-dist laravel/laravel:^7.0 .```
2. Edit permissions on the new Laravel files: Open a shell inside the PHP container that is running, and execute this command: ```chmod -R 777 /app```. This will change the permissions on the application folder, so the PHP user can access the log files, and Laravel doesn't throw an error saying it can't access storage/logs/laravel.log.
3. The final step was to restart the NGinx container. And finally open a browser in Windows normally and browse to http://127.0.0.1:82/, you should see the Laravel home page.

### Refereces
- Guide to set up everything from scratch: https://www.sitepoint.com/docker-php-development-environment/ (until the MySQL part).
- Solve the "The stream or file "/app/storage/logs/laravel.log" could not be opened in append mode: failed to open stream: Permission denied" problem: https://www.edureka.co/community/86899/stream-storage-laravel-opened-failed-stream-permission-denied