# MYSQL Replication Master -> Slave

> Docker Build

  docker build -t geunsam2/mysql-master:5.7.28 -f ./master-mysql.cnf .
  docker build -t geunsam2/mysql-slave:5.7.28 -f ./slave-mysql.cnf .
  
 > Docker run
 
  docker run -d -p 13306:3306 --name mysql-master geunsam2/mysql-master:5.7.28
  docker run -d -p 23306:3306 --name mysql-slave --link mysql-master:mysql-master geunsam2/mysql-master:5.7.28
