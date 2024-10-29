# Итоговый проект

## 1. Краткое описание проекта
Проект представляет собой простейший планировщик задач с веб-интерфейсом и бэком на Go, клиент-серверное взаимодействие реализовано посредством REST API, в качестве СУБД выступает SQLite

Сервис позволяет создавать новые задачи с определенными правилами повторения, а также просматривать, редактировать и удалять их

## 2. Реализованные задачи со звездочкой
1. Возможность определять порт по переменной окружения
2. Возможность определять путь к базе данных по переменной окружения
3. Фильтры для метода получения листинга задач
4. Создание докер образа

## 3. Запуск кода
 - Для запуска сервера локально необходимо в терминале выполнить сборку проекта находясь в директории проекта
    ```sh
        go build -o task_manager_server
    ```
    а затем запустить проект
    ```sh
        ./task_manager_server
    ```
 - Для взаимодействия с сервером через веб-интерфейс необходимо при запущенном сервере открыть в браузере
http://localhost:7540/

## 4. Тестирование
- Конфигурация автотестов: в файле tests/settings.go установить параметры
    ```go
        var Port = 7540
        var DBFile = "../cmd/scheduler.db"
        var FullNextDate = false
        var Search = true
        var Token = ``
    ```
- Для запуска автотестов необходимо в терминале, находись в папке проекта, выполнить
    ```sh
            go test ./tests
    ```
- [Коллекция методов API для Postman](https://www.postman.com/timur-tikhomirov/workspace/yandex/request/)
