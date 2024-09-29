# docker-opengamepanel
Docker version of OpenGamePanel, that include:
- Web Interface
- Agent

## Web

This is the list of all environments variables that you *MUST DEFINE*:
```.env
OGP_SQL_HOST=mysql
OGP_SQL_USER=user
OGP_SQL_PASSWORD=password
OGP_SQL_DATABASE=database
```

## Usage

Copy `.env.dist` and `docker-compose.override.yml.dist` and adapt your configuration
```bash
cp .env.dist .env
cp docker-compose.override.yml.dist docker-compose.override.yml
```

Finally, up the compose:
```bash
docker-compose up --d
```

## Panel Web Credentials
```
Username: admin
Password: password
```

## Get Remote Encryption Key
1. Open a terminal window on your host machine.
2. Execute the following command:

``` docker logs ogp-agent-1 ```

3. In the terminal output, locate the OGP credentials. They should appear in a format similar to this:
```
This is the OGP credentials:
ogpUser=ogp_agent
ogpPass=1WvXl6wo3TmKtqC
ogpEnc=q8N9n3oN
```

## Panel Web GameServer Config
```
Remote Host: Your Host IP
Remote Host Port: 27015
Remote Host Name: Name Display in Panel
FTP IP: Your Host IP
FTP Port: 21
Remote Encryption Key: Write your ogpEnc
Time Out: 5
Use NAT: No
Display Public IP: 
```
