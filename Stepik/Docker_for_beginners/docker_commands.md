### Docker commands
```bash
docker run image-name - запустить контейнер из образа (если образа нет локально, скачает его из Docker Hub)

-t — предоставляет доступ к терминалу внутри контейнера
-i — интерактивный режим, делает возможным взаимодействие с терминалом внутри контейнера
-d — запуск контейнера в фоновом режиме (detached mode)
--rm — автоматическое удаление контейнера после завершения его работы

docker run image-name:5.0 - запустить/скачать образ 5 версии (где :5.0 - тег. По умолчанию скачивается последняя - latest)

docker run --name container-name image-name - запустить контейнер с именем container_name из образа image_name  (флаг --name)

docker run image-name sleep 20 - запустить контейнер из образа image_name с командой sleep и аргументом 20

docker run -p 1000:80 image-name - перенаправляет трафик с 80 порта на порт 1000 внутри контейнера (флаг -p)

docker run -v /opt/datadir/:/var/lib/container-name image-name - связать/монтировать директорию на хосте /opt/datadir/ с директорией внутри контейнера /var/lib/container-name (флаг -v)

docker run --log-driver none image-name -  запустить контейнер с отключенным логированием
```
```bash
docker exec - позволяет выполнять команды на работающем контейнере

docker exec container-name cat /etc/hosts - покажет содержимое файла /etc/hosts на контейнере

docker exec -it container-name /bin/bash - интерактивно подключиться к контейнеру для управления (exit - выход)

docker attach container-name - прикрепить контейнер к консоли (STDIN, STDOUT или STDERR)/подключиться к контейнеру в реалтайме
```
```bash
docker pull image-name - скачать образ на хост из registry

docker push image-name - отправить локальный образ в registry

docker search image-name - поиск образа в registry

docker history image-name - посмотреть историю образа
```
```bash
docker start container-name - запустить контейнер


docker ps - посмотреть список запущенных контейнеров

docker ps -a - посмотреть список всех контейнеров


docker stop container-name - остановить запущенный контейнер

docker stop $(docker ps -a -q) - остановить все контейнеры


docker rm container-name - удалить контейнер

docker rm -f $(docker ps -aq) - удалить все запущенные и остановленные контейнеры

docker container prune - удалить все контейнеры


docker inspect container-name - посмотреть подробную информацию о контейнере (сетевые адреса, переменные окружения, политику рестарта и т.д.)

docker logs container-name - посмотреть логи контейнера

docker container logs -f container-name - получить поток логов контейнера

docker port container-name - Показать публичный порт контейнера

docker top container-name - отобразить процессы в контейнере

docker stats container-name - статистика использования ресурсов в контейнере
```
```bash
docker build . -t my_app - билд контейнера в текущей папке, скачивает все слои для запуска образа (берет инструкцию из Dockerfile)

docker images - посмотреть список доступных образов на хосте

docker rmi image-name - удалить образ

docker image prune - удалить все образы

docker image history --no-trunc image-name - посмотреть историю слоёв образа
```
```bash
docker volume create todo-db - создать том(volume) для постоянного хранения файлов

docker volume ls - Отобразить список всех томов

docker volume inspect - инспекция томов

docker volume rm - удалить том
```
```bash
docker network create todo-app - Создать сеть

docker network rm - удалить сеть

docker network ls - показать все сети

docker network inspect - вся информация о сети

docker network connect - соединиться с сетью

docker network disconnect - отсоединиться от сети
```
```bash
Dockerfile

FROM — устанавливает базовый образ
RUN — выполняет команду в контейнере
ENV — устанавливает переменную окружения
WORKDIR — устанавливает рабочую директорию
VOLUME — создает точку монтирования для тома
CMD — устанавливает исполняемый файл для контейнера
```
```bash
docker-compose up - разворачивает стек из файла docker-compose.yml текущей директории

docker-compose down - останавливает стек и удаляет все контейнеры и сети

docker-compose stop - остановить стек без удаления контейнеров

docker-compose ps - показывает контейнеры за которые отвечает Docker Compose

docker-compose logs - общий пул логов поднятого стека Docker Compose

docker-compose up --scale wordpress=2 - управление количеством реплик определенной службы

Docker compose

version: '2'
services:
  app:
    build:
      context: ./app
    depends_on:
      - redis
    environment:
      - REDIS_HOST=redis
    ports:
      - "5000:5000"
  redis:
    image: redis:3.2-alpine
    volumes:
      - redis_data:/data
volumes:
  redis_data:
```
```bash
docker version - посмотреть версию Docker
```
