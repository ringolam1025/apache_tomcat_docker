# Apache Tomcat Docker Sample


## Requirements
- Docker
- Docker-compose
- Apache (will install by docker)
- Tomcat 8.5.57 (will install by docker)
- MySQL (will install by docker)

## Installation

1. Put source file into `www`

1. Input MYSQL information in `.env` (Optional)
    ```
    MYSQL_USER=db
    MYSQL_PASSWORD=db123
    MYSQL_DATABASE=demo
    MYSQL_ROOT_PASSWORD=root
    ```
    > Reminder to update your database connection, if MYSQL setting has been changed
    > 
    
1. Build cointainer
    > ### Before create cointainer
    > 
    > 1. Default is using port 85 in Apache. Please *DO NOT* use in production environment.
    > Before running on production, please change *ports* from `"85:80"` to `"80:80"` in `docker-compose.yml`
    >       ```yml
    >       apache:
    >         build: ./apache
    >         restart: always
    >         ports:
    >          - "85:80"
    >         depends_on:
    >           - web
    >       ```
    >   
 
    ```bash
    ./dockerstart.sh
    ```
1. Open in broswer to test Tomcat server
    ```
    http://[YourHostIP]:8860
    ```
    >
    > If fail, please try to restart `web` container manaully, and try again. 
    >
1. Enter below link to test Apache proxy forward service
    ```
    http://[YourHostIP]:85
    ```    

## Phpmyadmin
Phpmyadmin is also setup in last section and the access link
```
http://[YourHostIP]:8861
```
