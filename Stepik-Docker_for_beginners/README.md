### Docker commands
```
docker run image_name - запустить контейнер из образа (если образа нет локально, скачает его из Docker Hub)

-t — предоставляет доступ к терминалу внутри контейнера
-i — интерактивный режим, делает возможным взаимодействие с терминалом внутри контейнера
-d — запуск контейнера в фоновом режиме (detached mode)
--rm — автоматическое удаление контейнера после завершения его работы

docker run image_name:5.0 - запустить/скачать образ 5 версии (где :5.0 - тег. По умолчанию скачивается последняя - latest)

docker run --name container_name image_name - запустить контейнер с именем container_name из образа image_name  (флаг --name)

docker run image_name sleep 20 - запустить контейнер из образа image_name с командой sleep и аргументом 20

docker run -p 1000:80 image_name - перенаправляет трафик с 80 порта на порт 1000 внутри контейнера (флаг -p)

docker run -v /opt/datadir/:/var/lib/container_name image_name - связать/монтировать директорию на хосте /opt/datadir/ с директорией внутри контейнера /var/lib/container_name (флаг -v)

docker run --log-driver none image_name -  запустить контейнер с отключенным логированием
```
```
docker exec - позволяет выполнять команды на работающем контейнере

docker exec container_name cat /etc/hosts - покажет содержимое файла /etc/hosts на контейнере
```
```
docker attach container_name - прикрепить контейнер к консоли (STDIN, STDOUT или STDERR)
```
```
docker pull image_name - скачать образ на хост
```
```
docker ps - посмотреть список запущенных контейнеров

docker ps -a - посмотреть список всех контейнеров
```
```
docker images - посмотреть список доступных образов на хосте
```
```
docker stop container_name - остановить запущенный контейнер

docker stop $(docker ps -a -q) - остановить все контейнеры
```
```
docker rm container_name - удалить контейнер

docker container prune - удалить все контейнеры
```
```
docker rmi image_name - удалить образ

docker image prune - удалить все образы
```
```
docker inspect container_name - посмотреть подробную информацию о контейнере (сетевые адреса, переменные окружения, политику рестарта и т.д.)
```
```
docker logs container_name - посмотреть логи контейнера

docker container logs -f container_name - получить поток логов контейнера
```
```
docker version - посмотреть версию Docker
```
