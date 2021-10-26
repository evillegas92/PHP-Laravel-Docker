# PHP-Laravel-Docker
Laravel sample application with Docker, PHP 7.3 and Composer.

1. Make sure you have Docker installed.
2. Check out the repo.
3. At the root folder of the repo, run ```docker-compose build``` to build the PHP docker image specified by the PHP.Dockerfile.
4. Then run ```docker-compose up``` to run the two container images (NGinx web server and the PHP image).
5. Open a shell inside the PHP container that is running, and execute this command: ```chmod -R 777 /app```. This will change the permissions on the application folder, so the PHP user can access the log files, and Laravel doesn't throw an error saying it can't access storage/logs/laravel.log.
6. The final step should be to restart the NGinx container. And finally open a browser in Windows normally and browse to http://127.0.0.1:82/, you should see the Laravel home page.