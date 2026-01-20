# Wireguard-Subnet
Wireguard сервер, нацеленный на создание общей подсети и коммуникации между участниками.
## Настройка
Файл конфигурации находится: `./.env`
Шаблон конфигурации - `./template.env`
### wireguard-1
- `WIREGUARD1_CONTAINER_NAME`
    Название контейнера

- `WIREGUARD1_PORT`
    Порт на котором будет слушать wireguard

- `WIREGUARD1_PEERS`
    Имена пользователей, разделенные запятой

- `WIREGUARD1_CONFIG_PATH`
    Путь для конфигурации wireguard

- `WIREGUARD1_MODULES_PATH`
    Путь для модулей wireguard

### wireguard-2
- `WIREGUARD2_CONTAINER_NAME` 
    Название контейнера

- `WIREGUARD2_PORT` 
    Порт на котором будет слушать wireguard

- `WIREGUARD2_PEERS` 
    Имена пользователей, разделенные запятой

- `WIREGUARD2_CONFIG_PATH`
    Путь для конфигурации wireguard

- `WIREGUARD2_MODULES_PATH`
    Путь для модулей wireguard

## Запуск
1. Убедитесь что вы используете Docker V2
2. Запустить сервис номер 1
```sh
docker compose up wireguard-1 -d
```
3. Запустить сервис номер 2
```sh
docker compose up wireguard-2 -d
```

## Добавление пользователей

Чтобы добавить пользователя:

1. Отредактируйте файл конфигурации, и добавьте имя пользователя в переменную `WIREGUARD1_PEERS` или `WIREGUARD1_PEERS`, в зависимости от того в какой сервис вы хотите добавить пользователя
2. Перезапустите сервис
```sh
docker compose restart имя-сервиса
```

## Где найти конфигурации?

Конфигурации можно найти по пути `WIREGUARD*_CONFIG_PATH`