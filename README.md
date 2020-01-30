# Tiddlywiki web storage with automatic git upload

!! BE CAREFUL ABOUT store.php , it is not in .gitignore  , so pulling might reset your users

you would need a file named ".env" with 2 things defined like below:

GITURL=git@github.com:anyuser/anyrepo.git
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

setup docker , in thise case it is meant to be used with the famous jwilder nginx setup 

# Configure Tiddlywiki

→ username and pass from the script
→ url is "https://your.domain/path/to/script.php"
→ be sure to use relative paths 

see https://excogitation.de/wiki/#Tiddlywiki%20saving%20with%20php%20script

