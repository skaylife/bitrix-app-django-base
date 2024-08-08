# Bitrix App Django Base

Базовый шаблон для создания приложений на Django с интеграцией в Bitrix.

#### Так выглядит 
![browser_nrGATREiMp](https://github.com/user-attachments/assets/26624c6f-9868-4d35-8a1e-0ab1d71ed9fc)

#### Ищем пункт разработчики
![browser_rV0EJ4q8ce](https://github.com/user-attachments/assets/0d6e4c08-c0c1-47f7-a494-e53b4f71063c)

#### Готовые сценарии > другое
![browser_5OvpKWdl6k](https://github.com/user-attachments/assets/903a8e41-5dbb-41f6-8cef-ad743b9c2ab9)

#### Другое > локальное приложение
![browser_wGKbsmpMUt](https://github.com/user-attachments/assets/3dc49400-82e2-4df0-9959-1500a1639355)

#### Настройки приложения указываем ip адрес
![browser_RIdedxXZxp](https://github.com/user-attachments/assets/e5c47673-b356-4c59-b9ed-fc62a9cc2c02)

#### После сохранения настроек > нажать на кнопку "перейти к приложению"
![browser_Djxf37qeX7](https://github.com/user-attachments/assets/7965f007-fcd9-4ff8-a6de-7233f086b57a)

#### Как выглядит приложение в итоге в Bitrix
![browser_etbw6GRfAG](https://github.com/user-attachments/assets/2cc3f32a-f72a-467c-93a7-27df9e00f2b0)


## Установка и настройка проекта

### 1. Создание виртуального окружения

1. Установка `virtualenv`, если он не установлен:
    ```bash
    pip install virtualenv
    ```

2. Создание виртуального окружения:
    ```bash
    virtualenv env
    ```
    Или:
    ```bash
    python -m venv env
    ```

3. Активация виртуального окружения:
    - На Windows:
      ```bash
      env\Scripts\activate
      ```
    - На macOS и Linux:
      ```bash
      source env/bin/activate
      ```

    Если вы не в папке проекта, а на уровень выше, используйте:
    ```bash
    core\env\Scripts\activate
    ```

    Если вы уже в проекте с Django, используйте:
    ```bash
    env\Scripts\activate
    ```

### 2. Установка Django и создание проекта

1. Установка Django:
    ```bash
    pip install django
    ```

2. Создание Django проекта с названием `core`:
    ```bash
    django-admin startproject core
    ```

3. Создание Django приложения:
    ```bash
    python manage.py startapp <название_приложения>
    ```

### 3. Запуск сервера разработки

1. Запуск сайта на Django:
    ```bash
    python manage.py runserver
    ```

2. Выход из виртуального окружения:
    ```bash
    deactivate
    ```

3. Сохранение установленных библиотек:
    ```bash
    pip freeze > requirements.txt
    ```

4. Установка зависимостей из `requirements.txt`:
    ```bash
    pip install -r requirements.txt
    ```

## Настройки для `settings.py`

Пример настроек для работы с Bitrix:

```python
# Разрешенные хосты для работы сайта
ALLOWED_HOSTS = ['*']  # Разрешаем все хосты для упрощения конфигурации

# Настройка для разрешения встраивания сайта в другие сайты
X_FRAME_OPTIONS = 'ALLOWALL'  # Разрешает встраивание сайта в iframe на любом домене

# Доверенные источники для защиты от CSRF-атак
CSRF_TRUSTED_ORIGINS = ['https://test-s20x.com']  # Разрешаем запросы с указанного домена

# Пример конфигурации промежуточного ПО
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    # 'django.middleware.csrf.CsrfViewMiddleware',  # Комментируем для отключения проверки CSRF
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]
```


# core 
## Описание проекта 
Проект Django с приложением app. 
## Установленные библиотеки 
asgiref==3.8.1
Django==5.1
sqlparse==0.5.1
tzdata==2024.1
