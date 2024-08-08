# Bitrix App Django Base

Базовый шаблон для создания приложений на Django с интеграцией в Bitrix.

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
