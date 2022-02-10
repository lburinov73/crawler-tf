# Конфигурация terraform для crawler Kubernetes кластера в Yandex Cloud

 - Требуется S3 хранилище для хранения tfstate файлов (см. ```backend.tf```)
 - В секрет ```S3_CREDENTIALS``` нужно сохранить в формате base64 креденшелы IAM пользователя с доступом к созданному S3 бакету, 
   (```cat credentials | base64 -i```
   (формат файла с креденшелами можно посмотреть в файле ```credentials.example```)
 - Параметры Яндекс облака задаются в файле ```terraform.tfvars```
 - В секрет ```SERVICE_ACCOUNT_KEY_FILE``` нужно сохранить ключ сервисного аккаунта YC в формате base64
   (```cat key.json | base64 -i```)
