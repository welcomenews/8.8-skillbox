#### 8.8-skillbox


#### Для работы Sonarqube нужно устновить джаву 11 базу данных (например postgresql)
$ sudo apt install openjdk-11-jre-headless -y
$ sudo apt install postgresql postgresql-contrib -y

#### Скачиваем Sonarqube c оф.сайта
https://www.sonarqube.org/downloads/

#### Настраивае Postgress
$ sudo su postgres
$ createuser sonar
$ psql
postgres=# ALTER user sonar WITH ENCRYPTED password 'sonar';
postgres=# create database sonarqube owner sonar;
postgres=# exit

#### Запуск Sonarqube
$ ~/sonarqube/sonarqube-9.6.0.59041/bin/linux-x86-64$ ./sonar.sh start

#### Оф.станица доки 
https://docs.sonarqube.org/latest/setup/install-server/

#### Скачиваем сканер 
https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/




