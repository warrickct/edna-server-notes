
# Server notes

## Apache2

* Apache is set up to redirect port 80 to force it to use SSL located at port 8000.
* It also has the CORS configuration stuff included for outgoing headers.
* All the aforementioned mods can be viewed at ```/etc/apache2/sites-enabled/default.conf``` or something like that.

* on 30th Sept. 2019 we fixed a problem where it was being served on 8000 with the regular http. This was due to a nginx installation that was running on the eDNA server that prevented the apache2 configurations from functioning correctly. Problem was solved by doing a full removal of nginx using 

## Docker

* We also added ```restart: always``` under the title of each service to the eDNA server master compose.yml "docker-compose.yml" so that on nectar VM reboot, it'll always rerun the docker container for eDNA. (This is all on the nectar VM). **NOTE: This change has only occured on the server as of 30th sept 2019 and hasn't yet been pushed to the master branch so the docker-restart changes will not be made until then.**

* Lets encrypt is running and is on auto-renew. You can view/verify this by viewing the ```/etc/cron.d/certbot``` file.
