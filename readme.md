# Example of finding your PHP version

The `phpinfo` command will show you a lot of information about your installation of PHP.

## Running this project
To run this project make sure that you have docker and docker-compose installed.

Then run the following commands in your shell:

    cd docker
    docker-compose up
    
You will see PHP and nginx starting up.  

Once your terminal stops moving you can visit
http://localhost/index.php in your browser to see the output of the script in `src/index.php`.

To stop the server go back to your terminal and press CTRL-C.

## Changing which version of PHP you're using

You will notice that the file `docker-compose.yml` contains two versions of PHP.
You can change which version nginx uses by setting the `container_name` to "php" for the version that you want to use.

    php7:
        image: php:7.2-fpm
        volumes:
          - '../src:/code'
        container_name: php
    
    php5:
        image: php:5.6-fpm
        volumes:
          - '../src:/code'
        container_name: php5
       
In the example above we have renamed the PHP7.2 container to "php" and so Nginx will use that one.
    
Here is how we will change it to use PHP5.6:
    
    php7:
        image: php:7.2-fpm
        volumes:
          - '../src:/code'
        container_name: php7
    
    php5:
        image: php:5.6-fpm
        volumes:
          - '../src:/code'
        container_name: php5.2


## Caution

This is very much not an appropriate configuration for production and is a bare-bones demonstration of running 
a single PHP script.  Do not use this as an example of a config!
