## Part 1.

* Взять официальный докер образ с nginx и выкачать его при помощи docker pull
![](Screenshots/1.png)

* Проверить наличие докер образа через docker images
![](Screenshots/2.png)

* Запустить докер образ через docker run -d [image_id|repository]
![](Screenshots/3.png)

* Проверить, что образ запустился через docker ps
![](Screenshots/4.png)

* Посмотреть информацию о контейнере через docker inspect [container_id|container_name]

* По выводу команды определить и поместить в отчёт размер контейнера, список замапленных портов и ip контейнера
![](Screenshots/5.png)
![](Screenshots/6.png)
![](Screenshots/7.png)

* Остановить докер образ через docker stop [container_id|container_name]

* Проверить, что образ остановился через docker ps
![](Screenshots/8.png)

* Запустить докер с замапленными портами 80 и 443 на локальную машину через команду run
![](Screenshots/9.png)

* Проверить, что в браузере по адресу localhost:80 доступна стартовая страница nginx
![](Screenshots/10.png)

* Перезапустить докер контейнер через docker restart [container_id|container_name]
![](Screenshots/11.png)

## Part 2.
* Прочитать конфигурационный файл nginx.conf внутри докер образа через команду exec
![](Screenshots/12.png)
![](Screenshots/13.png)

* Создать на локальной машине файл nginx.conf.   
Настроить в нем по пути /status отдачу страницы статуса сервера nginx
![](Screenshots/14.png)

* Скопировать созданный файл nginx.conf внутрь докер образа через команду docker cp
![](Screenshots/15.png)

* Перезапустить nginx внутри докер образа через команду exec
![](Screenshots/16.png)

* Проверить, что по адресу localhost:80/status отдается страничка со статусом сервера nginx
![](Screenshots/17.png)

* Экспортировать контейнер в файл container.tar через команду export
![](Screenshots/18.png)

* Остановить контейнер
![](Screenshots/19.png)

* Удалить образ через docker rmi [image_id|repository], не удаляя перед этим контейнеры
![](Screenshots/20.png)

* Удалить остановленный контейнер
![](Screenshots/21.png)

* Импортировать контейнер обратно через команду import
![](Screenshots/22.png)

* Запустить импортированный контейнер
![](Screenshots/23.png)

* Проверить, что по адресу localhost:80/status отдается страничка со статусом сервера nginx
![](Screenshots/24.png)
![](Screenshots/25.png)

## Part 3.

* Запускаем nginx контейнер с портом 81.  
![](Screenshots/26.png)
* Устанавливаем в него: apt install libfcgi-dev, apt install spawn-fcgi, apt install gcc
* Перекидываем нужные нам файлы в контейнер (nginx.conf обязательно перекинуть в папку nginx)
* Даём права скрипту и запускаем run.sh    
![](Screenshots/27.png)
![](Screenshots/29.png)

## Part 4.
* С помощью команды: "docker build -t hello_oworld:1.0 ."     
создаём образ и запускаем его
![](Screenshots/31.png)
docker run -p 80:81 -d hello_world:1.0
![](Screenshots/32.png)

## Part 5.
* Устанавливаем dockle через brew.    
* Запускаем диагностику образа командой:    
 dockle -ak NGINX_GPGKEY hello_world:1.0   
![](Screenshots/33.png)

## Part 6.
docker-compose build
![](Screenshots/28.png)

docker-compose up
![](Screenshots/34.png)
![](Screenshots/35.png)
![](Screenshots/36.png)
