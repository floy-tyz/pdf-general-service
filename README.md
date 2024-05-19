# docker-engine
В большинстве случаев на одном сервере требуется запускать более одного проекта, в таком случае при использовании
docker появляется проблема - необходимо для каждого проекта иметь свой nginx, а порт 80 и 443 нельзя переиспользовать
более одного раза, тогда нам на помощь приходит обратное проксирование, которое так же можно осуществить в веб сервере
nginx.

Отличным образом может послужить nginxproxy/nginx-proxy, который на основе сокета от докера определяет запущенные контейнеры
и обнаруживает переменную среды VIRTUAL_HOST. При ее обнаружении он создает конфиг для nginx, который как раз таки выполняют
функцию обратного проксирования для сервиса.

<h3>docker-compose.yaml</h3>

В этом файле указываются
1) Версия docker-compose
2) Создаваемые сети для обмена данными между сетям

* На данный момент актуальная версия docker-compose 3.9