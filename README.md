# Phing and Phoenix for Jenkins

This repo holds a composer build of Phing and Phoenix for Jenkins (it is not a fork of Phing as the name might imply). It exists to provide a fixed location that Jenkins can find the configuration and code it needs to operate. Jenkins expects it to be deployed to util55.phx2:/cbs/home/gamespot/phing.

## How to update Jenkins when somehing in phoenix Components/Phing changes

First time clone to your local computer:
* Run `git clone git@github.com:cbsi/phing.git` locally
* Run `php composer.phar install`

Thereafter you can do:
* Run `php composer.phar update phoenix` to update the composer.lock file with the latest phoenix master 
* Do a git commit and push of the new lock file
* Run `ssh util55.phx2.cbsig.net` to login to the Jenkins server
* Run `cd /cbs/home/gamespot/phing`
* Run `git pull`
* Run `php composer.phar install --prefer-source`

All done!
