### 윈도우 파워쉘은 개행해서 할려면 백틱(`)을 사용해야한다.

```
docker `
run `
    --name "db" `
    -v "$(pwd)/db_data:/var/lib/mysql" `
    -e "MYSQL_ROOT_PASSWORD=123456" `
    -e "MYSQL_DATABASE=wordpress" `
    -e "MYSQL_USER=wordpress_user" `
    -e "MYSQL_PASSWORD=123456" `
    --network wordpress_net `
mysql:5.7
```

```
docker `
    run `
    --name app `
    -v "$(pwd)/app_data:/var/www/html" `
    -e "WORDPRESS_DB_HOST=db" `
    -e "WORDPRESS_DB_USER=wordpress_user" `
    -e "WORDPRESS_DB_NAME=wordpress" `
    -e "WORDPRESS_DB_PASSWORD=123456" `
    -e "WORDPRESS_DEBUG=1" `
    -p 8080:80 `
    --network wordpress_net `
wordpress:latest
```
