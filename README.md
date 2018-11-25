# mediastation

__This could be used for illegal downloads, but don't! It's for educational purposes and legal downloads only.__


## 1. Install Docker

Install Docker and docker-compose for your system of choice.


## 2. Run this command to automatically download the docker images and start the services

```
docker-compose up -d
```


## 3. IP number

Find the IP number of the machine running the services.


## 4. DNS or hosts file configuration.

For noobs, add this to your /etc/hosts file (or equivalent):
```
{IP number} sabnzbd.media couchpotato.media sonarr.media plex.media
```
_Pros might choose to install a DNS service or just us a public 😱 IP configured with a proper domain name. For that, the nginx configs in `./config/nginx/nginx/site-confs` need changing. Also, SSL is a good idea in that scenaro... I won't even go there._


## 5. Final service configuration

Visit these urls to do final setup of each service:
* `http://sabnzbd.media`
* `http://couchpotato.media`
* `http://sonarr.media`
* `http://plex.media` _(See caveat under **Configure PLEX** below)_


## 6. ???

Now it's up to you.


## 7. Profit!

😎


# Configure PLEX
A huge and irritating gotcha for the plex server setup is that it needs to think you're setting it up from localhost to let you get to all the juicy options. So just SSH tunnel to the docker host with a port forward like so:

```
ssh plex.media -L 8888:localhost:32400
```

Then visit `http://localhost:8888/web` and follow the wizard.