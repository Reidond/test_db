# db

```sh
sudo docker run --name mysqldb -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_DATABASE=initial -e MYSQL_USER=reidond -e MYSQL_PASSWORD=1234 -v /home/reidond/src/test_db:/test_db -p 3306:3306 -d mysql:latest --character-set-server=utf8mb4 --collation-server=utf8mb4_unicode_ci
```

# data

```sh
sudo docker exec -i mysqldb sh -c 'cd /test_db; exec mysql -uroot -p"1234" < ./employees.sql'
```

# test

```sh
sudo docker exec -i mysqldb sh -c 'cd /test_db; exec mysql -uroot -p"1234" < ./test_employees_sha.sql'
```
