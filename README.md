#### 8.8-skillbox

-----------------------------------------------------------

```diff 
- Sonarqube  может просканировать код на всех известных яз.программирования и сделать оценку качества кода.
```

- ![#f03c15]Sonarqube  может просканировать код на всех известных яз.программирования и сделать оценку качества кода. `#f03c15`


#### Для работы Sonarqube нужно устновить джаву 11 базу данных (например postgresql)
$ sudo apt install openjdk-11-jre-headless -y

$ sudo apt install postgresql postgresql-contrib -y

#### Скачиваем Sonarqube c оф.сайта
https://www.sonarqube.org/downloads/

#### Настраивае Postgress
```
$ sudo su postgres
$ createuser sonar
$ psql
postgres=# ALTER user sonar WITH ENCRYPTED password 'sonar';
postgres=# create database sonarqube owner sonar;
postgres=# exit
```

#### Запуск Sonarqube
$ ~/sonarqube/sonarqube-9.6.0.59041/bin/linux-x86-64$ ./sonar.sh start

#### Оф.станица доки 
https://docs.sonarqube.org/latest/setup/install-server/

#### Скачиваем сканер
#### https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/
-------------------------------------------------------------------

#### Bandit может просканировать код на языке Python
$ sudo apt install bandit

#### Клонируем репу и в ней запускаем
#### $ bandit -r .

--------------------------------------------------------------------

#### Cppcheck - это инструмент статического анализа исходного кода на языке Си и Си++
$ sudo apt install cppcheck -y

#### Клонируем репу и в ней запускаем
#### $ cppcheck .
--------------------------------------------------------------------

#### Nmap сканер портов
$ sudo apt install nmap -y

#### $ nmap -A localhost
---------------------------------------------------------------------


https://habr.com/ru/company/solarsecurity/blog/497864/   часть 1

https://habr.com/ru/company/solarsecurity/blog/499860/   часть 2

https://habr.com/ru/company/solarsecurity/blog/499866/   часть 3







