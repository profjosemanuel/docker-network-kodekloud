docker run -d -e MYSQL_ROOT_PASSWORD=db_pass123 --name mysql-db --network bridge mysql:5.6

docker run --network=bridge -e DB_Host=mysql-db -e DB_Password=db_pass123 -p 38080:8080 --name webapp --link mysql-db:mysql-db -d kodekloud/simple-webapp-mysql
