# Интеграция с системами

## Бизнес-интеграция ИИ-системы

### Принципы интеграции

**ИИ-система должна работать с вашими существующими системами, а не заменять их:**

#### 🔗 **Безболезненное подключение**
- **Не нарушает работу** существующих систем
- **Использует стандартные** протоколы и API
- **Постепенное внедрение** без остановки бизнеса
- **Обратная совместимость** со старыми версиями

#### 📊 **Единый источник истины**
- **Синхронизация данных** между системами
- **Актуальная информация** в реальном времени
- **Консистентность** данных во всех системах
- **Централизованное управление** доступом

#### 🛡️ **Безопасность и контроль**
- **Сохранение существующих** политик безопасности
- **Дополнительные уровни** защиты для ИИ
- **Аудит всех операций** с данными
- **Контроль доступа** на уровне пользователей

---

### Типы интеграций

#### **1. CRM-системы**
**Популярные системы:**
- **AmoCRM** - для продаж и маркетинга
- **Bitrix24** - комплексная CRM
- **Planfix** - корпоративная CRM

**Что ИИ может делать:**
- **Анализ клиентов** - сегментация и прогнозирование
- **Автоматизация продаж** - создание лидов и сделок
- **Персонализация** - индивидуальные предложения
- **Прогнозирование** - предсказание конверсии

**Пример интеграции:**
```
Клиент обращается → ИИ анализирует историю → Предлагает решение → Создает сделку в CRM → Отслеживает результат
```

#### **2. ERP-системы**
**Популярные системы:**
- **1С:ERP** - российская ERP
- **CoMindWare** - наиболее перспективная BPM-система

**Что ИИ может делать:**
- **Оптимизация процессов** - автоматизация рутины
- **Прогнозирование спроса** - планирование закупок
- **Анализ эффективности** - KPI и метрики
- **Управление запасами** - оптимизация складских остатков

**Пример интеграции:**
```
Запрос на анализ → ИИ получает данные из ERP → Анализирует тренды → Предлагает оптимизацию → Обновляет планы
```

#### **3. Системы документооборота**
**Популярные системы:**
- **Directum** - корпоративный документооборот
- **1С:Документооборот** - российское решение
- **Confluence** - Atlassian экосистема
- **DocHub** - документация и архитектура как код

**Что ИИ может делать:**
- **Автоматическая классификация** документов
- **Извлечение данных** из документов
- **Создание отчетов** на основе документов
- **Поиск и анализ** в документах

**Пример интеграции:**
```
Новый документ → ИИ анализирует содержимое → Классифицирует и индексирует → Создает связи с другими документами → Уведомляет заинтересованных
```

#### **4. Базы данных и аналитика**
**Популярные системы:**
- **PostgreSQL** - реляционные БД
- **MongoDB** - NoSQL базы данных
- **ClickHouse** - аналитические БД
- **Apache Superset** - визуализация данных

**Что ИИ может делать:**
- **Анализ больших данных** - выявление паттернов
- **Прогнозирование** - предсказание трендов
- **Автоматические отчеты** - генерация аналитики
- **Аномалии** - выявление отклонений

**Пример интеграции:**
```
Запрос аналитики → ИИ подключается к БД → Выполняет сложные запросы → Анализирует результаты → Создает понятный отчет
```

---

### Этапы интеграции

#### **Этап 1: Анализ и планирование (1-2 недели)**
**Задачи:**
- **Инвентаризация систем** - что у вас есть
- **Анализ API** - возможности интеграции
- **Планирование архитектуры** - как все соединить
- **Оценка рисков** - что может пойти не так

**Результат:** Детальный план интеграции

#### **Этап 2: Пилотная интеграция (2-3 недели)**
**Задачи:**
- **Подключение к одной системе** - тестирование
- **Создание прототипа** - проверка концепции
- **Тестирование безопасности** - проверка защиты
- **Обучение команды** - как работать с новой системой

**Результат:** Работающий прототип интеграции

#### **Этап 3: Полная интеграция (4-6 недель)**
**Задачи:**
- **Подключение всех систем** - комплексная интеграция
- **Настройка синхронизации** - автоматическое обновление
- **Тестирование производительности** - проверка скорости
- **Документирование** - инструкции для пользователей

**Результат:** Полностью интегрированная система

---

### Технические аспекты интеграции

#### **API и протоколы**

**REST API:**
```python
# Пример интеграции с CRM
import requests

class CRMIntegration:
    def __init__(self, base_url, api_key):
        self.base_url = base_url
        self.headers = {'Authorization': f'Bearer {api_key}'}
    
    def get_customer_data(self, customer_id):
        response = requests.get(
            f"{self.base_url}/customers/{customer_id}",
            headers=self.headers
        )
        return response.json()
    
    def create_lead(self, lead_data):
        response = requests.post(
            f"{self.base_url}/leads",
            json=lead_data,
            headers=self.headers
        )
        return response.json()
```

**Webhook интеграции:**
```python
# Получение уведомлений от систем
@app.route('/webhook/crm', methods=['POST'])
def crm_webhook():
    data = request.json
    
    if data['event'] == 'new_lead':
        # Обработка нового лида
        ai_analyze_lead(data['lead'])
    
    elif data['event'] == 'deal_closed':
        # Анализ закрытой сделки
        ai_analyze_deal(data['deal'])
    
    return {'status': 'success'}
```

**База данных интеграции:**
```sql
-- Создание таблицы для синхронизации
CREATE TABLE system_integrations (
    id SERIAL PRIMARY KEY,
    system_name VARCHAR(100) NOT NULL,
    entity_type VARCHAR(50) NOT NULL,
    external_id VARCHAR(100) NOT NULL,
    internal_id VARCHAR(100) NOT NULL,
    last_sync TIMESTAMP DEFAULT NOW(),
    sync_status VARCHAR(20) DEFAULT 'success'
);

-- Индекс для быстрого поиска
CREATE INDEX idx_system_integrations 
ON system_integrations(system_name, entity_type, external_id);
```

#### **Синхронизация данных**

**Реал-тайм синхронизация:**
```python
# Периодическая синхронизация
import schedule
import time

def sync_crm_data():
    """Синхронизация данных с CRM каждые 5 минут"""
    try:
        # Получение новых данных
        new_data = crm_client.get_recent_changes()
        
        # Обработка через ИИ
        for item in new_data:
            ai_process_crm_item(item)
        
        # Обновление статуса синхронизации
        update_sync_status('crm', 'success')
        
    except Exception as e:
        update_sync_status('crm', 'error', str(e))

# Планирование синхронизации
schedule.every(5).minutes.do(sync_crm_data)

while True:
    schedule.run_pending()
    time.sleep(1)
```

**Пакетная синхронизация:**
```python
# Ночная синхронизация больших объемов данных
def nightly_sync():
    """Полная синхронизация всех систем ночью"""
    systems = ['crm', 'erp', 'documents', 'analytics']
    
    for system in systems:
        try:
            # Полная выгрузка данных
            full_data = get_full_data_export(system)
            
            # Обработка через ИИ
            ai_process_bulk_data(system, full_data)
            
            # Обновление индексов
            update_search_indexes(system)
            
        except Exception as e:
            log_error(f"Sync failed for {system}: {e}")
```

---

### Безопасность интеграции

#### **Аутентификация и авторизация**

**API ключи:**
```python
# Безопасное хранение ключей
import os
from cryptography.fernet import Fernet

class SecureConfig:
    def __init__(self):
        self.cipher = Fernet(os.environ['ENCRYPTION_KEY'])
    
    def get_api_key(self, system_name):
        encrypted_key = os.environ[f'{system_name.upper()}_API_KEY']
        return self.cipher.decrypt(encrypted_key.encode()).decode()
    
    def store_api_key(self, system_name, api_key):
        encrypted_key = self.cipher.encrypt(api_key.encode())
        os.environ[f'{system_name.upper()}_API_KEY'] = encrypted_key.decode()
```

**OAuth 2.0 интеграция:**
```python
# OAuth 2.0 для безопасного доступа
from oauthlib.oauth2 import WebApplicationClient

class OAuthIntegration:
    def __init__(self, client_id, client_secret):
        self.client = WebApplicationClient(client_id)
        self.client_secret = client_secret
    
    def get_authorization_url(self, redirect_uri):
        return self.client.prepare_request_uri(
            'https://api.example.com/oauth/authorize',
            redirect_uri=redirect_uri,
            scope=['read', 'write']
        )
    
    def exchange_code_for_token(self, authorization_response, redirect_uri):
        token_url, headers, body = self.client.prepare_token_request(
            'https://api.example.com/oauth/token',
            authorization_response=authorization_response,
            redirect_uri=redirect_uri,
            client_secret=self.client_secret
        )
        return requests.post(token_url, headers=headers, data=body)
```

#### **Шифрование данных**

**Шифрование в покое:**
```python
# Шифрование чувствительных данных
from cryptography.fernet import Fernet

class DataEncryption:
    def __init__(self):
        self.key = Fernet.generate_key()
        self.cipher = Fernet(self.key)
    
    def encrypt_sensitive_data(self, data):
        """Шифрование чувствительных данных перед сохранением"""
        if isinstance(data, dict):
            encrypted_data = {}
            for key, value in data.items():
                if self.is_sensitive_field(key):
                    encrypted_data[key] = self.cipher.encrypt(
                        str(value).encode()
                    ).decode()
                else:
                    encrypted_data[key] = value
            return encrypted_data
        return data
    
    def decrypt_sensitive_data(self, data):
        """Расшифровка данных при чтении"""
        if isinstance(data, dict):
            decrypted_data = {}
            for key, value in data.items():
                if self.is_sensitive_field(key):
                    decrypted_data[key] = self.cipher.decrypt(
                        value.encode()
                    ).decode()
                else:
                    decrypted_data[key] = value
            return decrypted_data
        return data
    
    def is_sensitive_field(self, field_name):
        """Определение чувствительных полей"""
        sensitive_fields = ['password', 'token', 'secret', 'key', 'credit_card']
        return any(sensitive in field_name.lower() for sensitive in sensitive_fields)
```

**Шифрование в движении:**
```python
# HTTPS для всех API вызовов
import requests
from requests.adapters import HTTPAdapter
from urllib3.util.retry import Retry

class SecureAPIClient:
    def __init__(self):
        self.session = requests.Session()
        
        # Настройка SSL/TLS
        self.session.verify = True
        
        # Настройка повторных попыток
        retry_strategy = Retry(
            total=3,
            backoff_factor=1,
            status_forcelist=[429, 500, 502, 503, 504]
        )
        adapter = HTTPAdapter(max_retries=retry_strategy)
        self.session.mount("http://", adapter)
        self.session.mount("https://", adapter)
    
    def make_secure_request(self, method, url, **kwargs):
        """Безопасный API запрос с SSL/TLS"""
        try:
            response = self.session.request(method, url, **kwargs)
            response.raise_for_status()
            return response
        except requests.exceptions.SSLError as e:
            log_error(f"SSL Error: {e}")
            raise
        except requests.exceptions.RequestException as e:
            log_error(f"Request Error: {e}")
            raise
```

---

### Мониторинг интеграций

#### **Метрики производительности**

**Время отклика:**
```python
# Мониторинг времени отклика API
import time
from prometheus_client import Histogram

api_response_time = Histogram(
    'api_response_time_seconds',
    'API response time in seconds',
    ['system', 'endpoint']
)

def monitor_api_call(system, endpoint):
    def decorator(func):
        def wrapper(*args, **kwargs):
            start_time = time.time()
            try:
                result = func(*args, **kwargs)
                duration = time.time() - start_time
                api_response_time.labels(system=system, endpoint=endpoint).observe(duration)
                return result
            except Exception as e:
                duration = time.time() - start_time
                api_response_time.labels(system=system, endpoint=endpoint).observe(duration)
                raise
        return wrapper
    return decorator

# Использование декоратора
@monitor_api_call('crm', 'get_customers')
def get_customers():
    return crm_client.get_customers()
```

**Статус синхронизации:**
```python
# Мониторинг статуса синхронизации
from prometheus_client import Gauge, Counter

sync_status = Gauge('system_sync_status', 'Sync status by system', ['system'])
sync_errors = Counter('system_sync_errors_total', 'Total sync errors', ['system'])

def update_sync_metrics(system, status, error=None):
    """Обновление метрик синхронизации"""
    if status == 'success':
        sync_status.labels(system=system).set(1)
    else:
        sync_status.labels(system=system).set(0)
        if error:
            sync_errors.labels(system=system).inc()
```

#### **Алерты и уведомления**

**Система алертов:**
```python
# Автоматические алерты при проблемах
import smtplib
from email.mime.text import MIMEText

class IntegrationAlerts:
    def __init__(self):
        self.smtp_server = os.environ['SMTP_SERVER']
        self.smtp_port = int(os.environ['SMTP_PORT'])
        self.email = os.environ['ALERT_EMAIL']
        self.password = os.environ['EMAIL_PASSWORD']
    
    def send_alert(self, system, error, details):
        """Отправка алерта при проблемах с интеграцией"""
        subject = f"Integration Alert: {system}"
        body = f"""
        System: {system}
        Error: {error}
        Details: {details}
        Time: {datetime.now()}
        """
        
        msg = MIMEText(body)
        msg['Subject'] = subject
        msg['From'] = self.email
        msg['To'] = self.email
        
        with smtplib.SMTP(self.smtp_server, self.smtp_port) as server:
            server.starttls()
            server.login(self.email, self.password)
            server.send_message(msg)
    
    def check_integration_health(self):
        """Проверка здоровья всех интеграций"""
        systems = ['crm', 'erp', 'documents', 'analytics']
        
        for system in systems:
            try:
                # Проверка доступности системы
                response = self.test_connection(system)
                if not response['success']:
                    self.send_alert(system, 'Connection Failed', response['error'])
            except Exception as e:
                self.send_alert(system, 'Unexpected Error', str(e))
```

---

### Что делать дальше
- [Архитектура ИИ-решений](/ai/practice/architecture)
- [Управление проектом](/ai/practice/management)
- [Масштабирование](/ai/practice/scaling)
- [Получить консультацию](/ai/request)
