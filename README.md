
```markdown
# Jupyter Notebook с PySpark


В этом проекте используется образ `pyspark-notebook`, который предоставляет среду Jupyter с предустановленным **Apache Spark** и **PySpark**.

---

## Как запустить

Убедитесь, что у вас установлен Docker:
- На Linux: [Docker Engine](https://docs.docker.com/engine/install/)
- На Windows: [Docker Desktop](https://docs.docker.com/desktop/install/windows-install/)

### Для Linux

```bash
docker run -d \
  -p 8811:8888 \
  -v my_jupyter_volume:/home/jovyan \
  --restart unless-stopped \
  quay.io/jupyter/pyspark-notebook:2025-04-26 \
  start-notebook.sh --NotebookApp.token=''
```

### Для Windows (Docker Desktop)

```bash
docker run -d ^
  -p 8811:8888 ^
  -v my_jupyter_volume:/home/jovyan ^
  --restart unless-stopped ^
  quay.io/jupyter/pyspark-notebook:2025-04-26 ^
  start-notebook.sh --NotebookApp.token=''
```

> Примечание: В Windows символ `^` используется для переноса строки. Можно также запустить команду в одной строке.

---

## Доступ к Jupyter

После запуска откройте в браузере:

[http://localhost:8811](http://localhost:8811)

Токен отключён (`--NotebookApp.token=''`), поэтому вход будет без пароля.

---

## Сохранение данных

Данные сохраняются в Docker-томе `my_jupyter_volume`. Все ваши ноутбуки и файлы будут храниться там и не потеряются при перезапуске контейнера.

---

## Остановка контейнера

Чтобы остановить контейнер:

```bash
docker ps
docker stop <container_id>
```

---

## Образ

Используется официальный образ:  
[quay.io/jupyter/pyspark-notebook:2025-04-26](https://quay.io/repository/jupyter/pyspark-notebook)

---

## Примечание

Если при загрузке образа возникает ошибка `504 Gateway Time-out`, попробуйте:
- Подождать несколько минут и повторить команду,
- Или использовать альтернативный реестр: `docker pull jupyter/pyspark-notebook`.
```

