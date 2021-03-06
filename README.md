# Конфигурация terraform для crawler Kubernetes кластера в Yandex Cloud

 - Требуется S3 хранилище для хранения tfstate файлов<br/>
   (см. ```backend.tf```)
 - В секрет ```S3_CREDENTIALS``` нужно сохранить в формате base64 креденшелы IAM пользователя с доступом к созданному S3 бакету<br/>
   ```cat credentials | base64 -i```<br/>
   (формат файла с креденшелами можно посмотреть в файле ```credentials.example```)
 - Параметры Яндекс облака и kubernetes кластера задаются в файле ```terraform.tfvars```
 - В секрет ```SERVICE_ACCOUNT_KEY_FILE``` нужно сохранить ключ сервисного аккаунта YC в формате base64<br/>
   ```cat key.json | base64 -i```

## Применение конфигурации

Для создания кластера (или изменения его параметров) можно использовать Action Terraform Apply<br/>
(см. файл ```.github/workflows/terraform-apply.yml```)

Для удаления кластера можно использовать Action Terraform Destroy<br/>
(см. файл ```.github/workflows/terraform-destroy.yml```)

