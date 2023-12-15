# DhbwNfcDemoTheme

This is the Shopware Theme for our DHBW Crossmedia project.

## Initializing the Project

1. Clone this repo
2. Use the dockware dev template (See docker-compose.yml) with ``docker-compose up -d``
3. The Theme should placed in ./plugins/**DhbwNfcDemoTheme**
4. login to the admin with http://localhost/admin (See Credentials below)

```
. (the current dockware root folder)
├── docker-compose.yml
└── plugins
    └── DhbwNfcDemoTheme
```

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
```shell
bin/console plugin:install DhbwNfcDemoTheme && bin/console plugin:activate DhbwNfcDemoTheme
```
and to install, activate and change the Theme
```shell
bin/console theme:change
```


## CLI commands (inside the container)
```shell
bin/console theme:compile #compiles the theme
```

```shell
bin/console cache:clear #cache clear
```

## Update Docker image if necessary
https://docs.dockware.io/use-dockware/update-dockware

```shell
docker pull dockware/dev:latest
```

# Contributors
- Philipp Borutta
- Paul Eitenbichler
- Julian Fleischmann
- Arthur Kaczynski
- Chris Sägner
- Sven Schuppel