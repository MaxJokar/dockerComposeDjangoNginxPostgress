# Deploy Django, Nginx and MySql with Docker Compose

This repository contains code to deploy Django, Nginx and MySql containers with Docker Compose.

Nginx will serve web requests on port 80. For serving Django application running on port 8001, we are using Gunicorn.

# Usage

After cloning the repository Run

```
Build the image : docker compose build

Run the containers : docker compose up

Close the containers : docker compose down
```
# All ifo about
#docker/postgres:https://markheath.net/post/exploring-postgresql-with-docker
# https://www.commandprompt.com/education/how-to-useexecute-postgresql-query-in-docker-container/
#  https://markheath.net/post/exploring-postgresql-with-docker
# https://geshan.com.np/blog/2021/12/docker-postgres/
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
# to make image from Dockerfile:
PS C:\mydrive\DjangoProjects2023\dockerComposeDjangoNginxPostgress> docker compose build
PS C:\mydrive\DjangoProjects2023\dockerComposeDjangoNginxPostgress> docker compose up 



data==>postgres\db 
django==>core(project),static(css,fonts,img,js),venv,dockerignore ,.env,Dockerfile,manage.py,requ.txt
nginx(Dockerfile,default.conf)
.gitignore
docker-compose.yml
readme.md 





  db:
    image: mysql
    container_name: "db_cont"
    environment:
      - MYSQL_ROOT_PASSWORD=neeraj
      - MYSQL_DATABASE=test_db
    volumes:
      - ./data/mysql/db:/var/lib/mysql

Dockerignore:
   venv inisde .dockerignore because we dont want   to be uploaded inside docker container 



docker :on Root
PS C:\mydrive\DjangoProjects2023\dockerComposeDjangoNginxPostgress> docker compose build   

To use Postress do following:
$docker pull Postgres:alpine
$docker images
$ docker run --name <something> -e POSTGRES_PASSWORD = passsword -d -p 5432:5432 postgres:alpine
$docker ps :we can see container running inside our  container


go to docker , containers , running  , terminal :
# All ifo about docker/postgres:https://markheath.net/post/exploring-postgresql-with-docker
# https://www.commandprompt.com/education/how-to-useexecute-postgresql-query-in-docker-container/
#  https://markheath.net/post/exploring-postgresql-with-docker
# https://geshan.com.np/blog/2021/12/docker-postgres/
docker quary in container terminal to see if exists: mysql -p ; mysql>show databases

After you check and assure everything works properly in docker  go to browser and check:
http://localhost:8001/


# for django installation we need to migrate some data :
in Docker , terminal , django_cont : python manage.py migrate 


* we also can create a project this way(without project or venv etc)
1. create dockefile
2.create docker-compose
3.$docker compose build
PS C:\mydrive\DjangoProjects2023\dockerComposeDjangoNginxPostgress> docker compose build
PS C:\mydrive\DjangoProjects2023\dockerComposeDjangoNginxPostgress> docker compose up  
4.$docker compose run --rm app sh -c "django-admin startproject app ."
4.$docker compose run --rm app sh -c "python manage.py startapp core "
4.$docker compose run --rm app sh -c "python manage.py makemigrations "



