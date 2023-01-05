### Docker commands
```
docker run image_name - запустить контейнер из образа (если образа нет локально, скачает его из Docker Hub)
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
