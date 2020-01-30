!!! Tiddlywiki web storage with automatic git upload

you would need a file named ".env" with 2 things defined:
GITURL=
COMPOSE_PROJECT_NAME=yourproject

whereas GITURL might be in token form ( https://user:tokenOrpass@gitserver.tld/project/path.git )
or mount an .ssh key as volume under /root/.ssh , be sure to either mount the .ssh folder
with authorized keys or do it using docker exec if you use ssh-style GITURL

adjust user and path in the store.php script before usage.




(

This is the fork of the github user makefu for php script out of the bidix tiddlyhome project.
makefu changes some of the more 'questionable' code (security-wise) in the store.php script.

since "split" is deprecated, changes were necesaary on the original script)

# Installation


    apt-get install php5-common php5-cli php5-fpm  nginx
    cp nginx/default.conf /etc/nginx/sites-available/wiki.conf
    # edit the nginx file to represent your environment
    ln -s /etc/nginx/sites-available/wiki.conf /etc/nginx/sites-enabled/wiki.conf
    mkdir -p /var/www/wiki/backup
    chown www-data:www-data -R /var/www/wiki/

    # edit store.php to represent your environment
    cp store.php /var/www/wiki
    chown root:root /var/www/wiki/store.php
    chmod 755 /var/www/wiki/store.php

# Configure Tiddlywiki

→ username and pass from the script
→ url is "https://your.domain/path/to/script.php"
→ be sure to use relative paths 

see https://excogitation.de/wiki/#Tiddlywiki%20saving%20with%20php%20script

