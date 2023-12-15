# DhbwNfcDemoTheme

This is the Shopware Theme for our DHBW Crossmedia project.

## Initializing the Project

1. Use the dockware dev template (See example docker-compose.yml below)
2. add the theme to the local dev from https://github.com/Julianfleischmann/DhbwNfcDemoTheme
3. The Theme should placed in [Dockware path]/plugins/**DhbwNfcDemoTheme**
(Dockware path is the folder where the docker-compsoe.yml is inside)
```
. (the current dockware root folder)
├── docker-compose.yml
└── plugins
    └── DhbwNfcDemoTheme
```

## 1. Setting up dockware
1. use the docker-compose-yml
2. Install dockware with ``docker-compose up -d``
3. login to the admin with http://localhost/admin (See Credentials below)

## Local dockware Credentials
### Admin
- User: shopware
- Password: dockware

https://docs.dockware.io/use-dockware/default-credentials
### SSH
What are the default dockware SSH/SFTP credentials?
- User: dockware
- Password: dockware
- Port: 22

## Change Theme
1. Use ``docker exec -it nfc-demo bash`` to acces the cli
2. Use the commands 
``bin/console plugin:install DhbwNfcDemoTheme && bin/console plugin:activate DhbwNfcDemoTheme``
and ``bin/console theme:change`` to install, activate and change the Theme

## Update Docker image if necessary
https://docs.dockware.io/use-dockware/update-dockware

``docker pull dockware/dev:latest``


# The example docker-compose.yml
```
version: '3'

services:
  shop:
    container_name: nfc-demo
    image: dockware/dev:latest
    ports:
      - "22:22"     # ssh
      - "80:80"     # apache2
      - "443:443"   # apache2 https
      - "8888:8888" # watch admin
      - "9998:9998" # watch storefront proxy
      - "9999:9999" # watch storefront
      - "3306:3306" # mysql port
    volumes:
    #  - "./src:/var/www/html"
      - "./plugins:/var/www/html/custom/plugins"
    networks:
      - web
    environment:
      - XDEBUG_ENABLED=0

## ***********************************************************************
##  NETWORKS
## ***********************************************************************
networks:
  web:
    external: false
```


# Contributors
- Philipp Borutta
- Paul Eitenbichler
- Julian Fleischmann
- Arthur Kaczynski
- Chris Sägner
- Sven Schuppel