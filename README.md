# Easy_NextCloud
Docker-compose solution to deploy NextCloud with MariaDB, Swag for TLS support and DuckDNS. 

## Setup & Prerequisites
*  Login to [DuckDNS](duckdns.org/). Create a domain and copy the token.
* Replace the following variables in the docker-compose.yml file.
    * YOUR_MYSQL_PASSWORD
    * DDNS_TOKEN
    * EMAIL_TO_RENEW_CERT
* Install docker and docker-compose if not already installed.


## Deployment

```bash
# Follow these steps to create and nginx conf.

# create the containers, volumes/dirs and start the services.
docker-compose up -d 

# Navigate to ./swag/config/nginx/proxy-confs
cp nextcloud.subdomain.conf.sample nextcloud.subdomain.conf

# Restart swag container after enabling nextcloud routing
docker restart swag

```

Once this is done and traffic is allowed on port 443 visit https://nextcloud.<YOUR_DUCK_DNS_DOMAIN>.duckdns.org


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.


### TODO
[ ] Add Redis
