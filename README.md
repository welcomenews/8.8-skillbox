#### 8.8-skillbox

-----------------------------------------------------------
<ins>`Sonarqube`</ins> может просканировать код на всех известных яз.программирования и сделать оценку качества кода.

#### Для работы Sonarqube нужно устновить джаву 11, базу данных (например postgresql)
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

<ins>`Bandit`</ins> может просканировать код на языке Python

$ sudo apt install bandit

#### Клонируем репу и в ней запускаем
$ bandit -r .

--------------------------------------------------------------------
<ins>`Cppcheck`</ins> это инструмент статического анализа исходного кода на языке Си и Си++

$ sudo apt install cppcheck -y

#### Клонируем репу и в ней запускаем
$ cppcheck .

--------------------------------------------------------------------
<ins>`Nmap`</ins> сканер портов

$ sudo apt install nmap -y

$ nmap -A localhost

---------------------------------------------------------------------
<ins>`Trivy`</ins> умеет сканировать как образ в репозитории, так и локальный образ, а также проводить сканирование на основании переданного .tar файла с Docker-образом. А так же может сканировать просто репозитории

```
Debian/Ubuntu
$ sudo apt-get install wget apt-transport-https gnupg lsb-release
$ wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | gpg --dearmor | sudo tee /usr/share/keyrings/trivy.gpg > /dev/null
$ echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb $(lsb_release -sc) main" | sudo tee -a /etc/apt/sources.list.d/trivy.list
$ sudo apt-get update
$ sudo apt-get install trivy
```
#### Пулим образ и запускаем
$ trivy image <имя образа>

#### Сканируем репу
$ trivy repo <ссылка на репу>

https://aquasecurity.github.io/trivy/v0.31.2/getting-started/installation/

----------------------------------------------------------------------

<ins>`goreporter`</ins> может просканировать код на языке Go

#### Установить go 

#### после запустить

$ go get -u github.com/360EntSecGroup-Skylar/goreporter

#### Клонировать репу и запустить

$ goreporter -p <путь к репе>

-----------------------------------------------------------------------

<ins>`Semgrep`</ins> может просканировать код на языках C#, Go, Java, JavaScript, JSX, JSON, PHP, Python, Ruby, Scala, TypeScript, TSX 
Интегрируется с GitHub, GitLab, CircleCI

#### To install Semgrep use Homebrew or pip, or run without installation via Docker:
```
# For macOS
$ brew install semgrep

# For Ubuntu/WSL/Linux/macOS
$ python3 -m pip install semgrep

# To try Semgrep without installation run via Docker
$ docker run --rm -v "${PWD}:/src" returntocorp/semgrep
```
#### RUN
```
# Check for Python == where the left and right hand sides are the same (often a bug)

$ semgrep -e '$X == $X' --lang=py path/to/src

# Fetch rules automatically by setting the `--config auto` flag.
# This will fetch rules relevant to your project from Semgrep Registry.
# The name of your project will be sent to Semgrep Registry as an identifier
# to make selecting relevant rules fast next time;
# source code will not be uploaded.

$ semgrep --config auto
```

https://github.com/returntocorp/semgrep

-------------------------------------------------------------------------------




