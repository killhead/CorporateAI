# Иконография для ИИ-раздела

## Общие принципы иконографии

### Стиль и стандарты
- **Стиль**: Современный, минималистичный, технологичный
- **Размеры**: 16px, 24px, 32px, 48px, 64px (основные размеры)
- **Формат**: SVG (векторная графика)
- **Цветовая схема**: Адаптивная под тему сайта

### Технические требования
- **Масштабируемость**: Без потери качества при изменении размера
- **Консистентность**: Единый стиль для всех иконок
- **Доступность**: Поддержка скринридеров
- **Производительность**: Оптимизированные SVG файлы

---

## 1. Основные иконки ИИ

### ИИ и технологии
```
🤖 AI/ИИ - Основная иконка искусственного интеллекта
🧠 Neural Network - Нейронная сеть
⚡ Processing - Обработка данных
🔍 Search - Поиск и анализ
📊 Analytics - Аналитика и метрики
💡 Intelligence - Интеллект и решения
```

### Бизнес-процессы
```
📋 Process - Бизнес-процессы
🔄 Automation - Автоматизация
📈 Growth - Рост и развитие
🎯 Target - Цели и результаты
⚙️ Settings - Настройки и конфигурация
📱 Integration - Интеграции
```

### Документы и данные
```
📄 Document - Документы
📁 Folder - Папки и структуры
🗄️ Database - Базы данных
📊 Chart - Графики и диаграммы
📝 Text - Текстовый контент
🔗 Link - Связи и интеграции
```

---

## 2. Иконки для разделов сайта

### Уровень 1 - Основы
```
🎓 Education - Обучение и понимание
❓ Question - Вопросы и ответы
🧮 Calculator - Калькуляторы
💰 Money - Стоимость и ROI
📚 Knowledge - База знаний
🎪 Demo - Демонстрации
```

### Уровень 2 - Решения
```
🎯 Solutions - Решения
📋 Phases - Фазы внедрения
⚙️ Implementation - Внедрение
⚠️ Risks - Риски и решения
📊 Comparison - Сравнения
🔧 Tools - Инструменты
```

### Уровень 3 - Практика
```
🏗️ Architecture - Архитектура
🔗 Integration - Интеграции
📊 Management - Управление
📈 Scaling - Масштабирование
🔧 Development - Разработка
📋 Planning - Планирование
```

---

## 3. Иконки для кейсов

### Клиентская поддержка
```
💬 Chat - Чат и общение
📞 Support - Поддержка клиентов
⏰ Time - Время и скорость
👥 Team - Команда
📈 Efficiency - Эффективность
🎯 Satisfaction - Удовлетворенность
```

### Пресейл и продажи
```
📊 Sales - Продажи
📋 Proposal - Предложения
📈 Conversion - Конверсия
💰 Revenue - Доходы
🎯 Target - Цели продаж
📱 CRM - Системы управления
```

### Документооборот
```
📄 Document - Документы
⚡ Speed - Скорость обработки
📋 Template - Шаблоны
🔍 Search - Поиск документов
📊 Report - Отчеты
📁 Archive - Архив
```

### Аналитика данных
```
📊 Data - Данные
🔍 Analysis - Анализ
📈 Chart - Графики
🎯 Insights - Инсайты
📱 Dashboard - Дашборды
🔗 Connection - Связи данных
```

---

## 4. Технические иконки

### Архитектура
```
🏗️ Architecture - Архитектура системы
🔗 API - API интерфейсы
🗄️ Database - Базы данных
🔐 Security - Безопасность
📡 Network - Сеть и коммуникации
⚡ Performance - Производительность
```

### Интеграции
```
🔗 Integration - Интеграции
📱 Mobile - Мобильные приложения
🌐 Web - Веб-интерфейсы
💬 Chat - Чат-боты
📧 Email - Электронная почта
📅 Calendar - Календари
```

### Разработка
```
💻 Code - Программирование
🔧 Development - Разработка
📝 Documentation - Документация
🧪 Testing - Тестирование
🚀 Deployment - Развертывание
📊 Monitoring - Мониторинг
```

---

## 5. Иконки для интерактивных элементов

### Калькуляторы
```
🧮 Calculator - Основной калькулятор
💰 ROI - Расчет ROI
⏰ Time - Расчет времени
👥 People - Расчет персонала
📊 Metrics - Метрики
🎯 Results - Результаты
```

### Тесты и опросы
```
❓ Question - Вопросы
✅ Answer - Ответы
📊 Results - Результаты
🎯 Score - Оценка
📈 Progress - Прогресс
🏆 Achievement - Достижения
```

### Демо и примеры
```
🎪 Demo - Демонстрации
💬 Chat - Чат-бот
📊 Dashboard - Дашборд
📱 App - Приложение
🌐 Website - Веб-сайт
📄 Document - Документ
```

---

## 6. Создание иконок

### Техническая реализация
```javascript
// Генератор иконок
class IconGenerator {
    constructor() {
        this.svgNamespace = 'http://www.w3.org/2000/svg';
        this.defaultSize = 24;
    }
    
    createIcon(iconType, size = this.defaultSize, color = 'currentColor') {
        const svg = document.createElementNS(this.svgNamespace, 'svg');
        svg.setAttribute('width', size);
        svg.setAttribute('height', size);
        svg.setAttribute('viewBox', '0 0 24 24');
        svg.setAttribute('fill', 'none');
        svg.setAttribute('stroke', color);
        svg.setAttribute('stroke-width', '2');
        svg.setAttribute('stroke-linecap', 'round');
        svg.setAttribute('stroke-linejoin', 'round');
        
        const path = this.getIconPath(iconType);
        if (path) {
            svg.innerHTML = path;
        }
        
        return svg;
    }
    
    getIconPath(iconType) {
        const iconPaths = {
            'ai': '<path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>',
            'brain': '<path d="M9.5 2C6.5 2 4 4.5 4 7.5S6.5 13 9.5 13 15 10.5 15 7.5 12.5 2 9.5 2z"/><path d="M9.5 13c-2.5 0-4.5 2-4.5 4.5S7 22 9.5 22s4.5-2 4.5-4.5S12 13 9.5 13z"/>',
            'search': '<circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/>',
            'chart': '<path d="M3 3v18h18"/><path d="m9 9 3 3 3-3 3 3"/>',
            'document': '<path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14,2 14,8 20,8"/>',
            'automation': '<path d="M12 2v4M12 18v4M4.93 4.93l2.83 2.83M16.24 16.24l2.83 2.83M2 12h4M18 12h4M4.93 19.07l2.83-2.83M16.24 7.76l2.83-2.83"/>'
        };
        
        return iconPaths[iconType] || '';
    }
    
    createAnimatedIcon(iconType, animationType = 'pulse') {
        const icon = this.createIcon(iconType);
        icon.classList.add(`icon-${animationType}`);
        return icon;
    }
}
```

### CSS стили для иконок
```css
/* Базовые стили иконок */
.icon {
    display: inline-block;
    vertical-align: middle;
    transition: all 0.3s ease;
}

.icon:hover {
    transform: scale(1.1);
    filter: brightness(1.2);
}

/* Размеры иконок */
.icon-sm { width: 16px; height: 16px; }
.icon-md { width: 24px; height: 24px; }
.icon-lg { width: 32px; height: 32px; }
.icon-xl { width: 48px; height: 48px; }

/* Анимации иконок */
.icon-pulse {
    animation: pulse 2s infinite;
}

.icon-spin {
    animation: spin 1s linear infinite;
}

.icon-bounce {
    animation: bounce 1s infinite;
}

@keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.5; }
}

@keyframes spin {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
}

@keyframes bounce {
    0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
    40% { transform: translateY(-10px); }
    60% { transform: translateY(-5px); }
}

/* Цветовые варианты */
.icon-primary { color: #2563EB; }
.icon-success { color: #10B981; }
.icon-warning { color: #F59E0B; }
.icon-danger { color: #EF4444; }
.icon-info { color: #06B6D4; }
```

### Интерактивные иконки
```javascript
// Интерактивные иконки
class InteractiveIcon {
    constructor(iconElement) {
        this.icon = iconElement;
        this.initInteractivity();
    }
    
    initInteractivity() {
        // Hover эффекты
        this.icon.addEventListener('mouseenter', this.handleHover.bind(this));
        this.icon.addEventListener('mouseleave', this.handleHoverEnd.bind(this));
        
        // Click события
        this.icon.addEventListener('click', this.handleClick.bind(this));
    }
    
    handleHover(event) {
        this.icon.style.transform = 'scale(1.1) rotate(5deg)';
        this.showTooltip();
    }
    
    handleHoverEnd(event) {
        this.icon.style.transform = 'scale(1) rotate(0deg)';
        this.hideTooltip();
    }
    
    handleClick(event) {
        // Добавление ripple эффекта
        this.createRippleEffect(event);
        
        // Выполнение действия
        const action = this.icon.dataset.action;
        if (action) {
            this.executeAction(action);
        }
    }
    
    createRippleEffect(event) {
        const ripple = document.createElement('span');
        ripple.classList.add('icon-ripple');
        
        const rect = this.icon.getBoundingClientRect();
        const size = Math.max(rect.width, rect.height);
        const x = event.clientX - rect.left - size / 2;
        const y = event.clientY - rect.top - size / 2;
        
        ripple.style.width = ripple.style.height = size + 'px';
        ripple.style.left = x + 'px';
        ripple.style.top = y + 'px';
        
        this.icon.appendChild(ripple);
        
        setTimeout(() => {
            ripple.remove();
        }, 600);
    }
    
    showTooltip() {
        const tooltip = document.createElement('div');
        tooltip.className = 'icon-tooltip';
        tooltip.textContent = this.icon.dataset.tooltip || '';
        
        document.body.appendChild(tooltip);
        
        const rect = this.icon.getBoundingClientRect();
        tooltip.style.left = rect.left + 'px';
        tooltip.style.top = (rect.bottom + 5) + 'px';
    }
    
    hideTooltip() {
        const tooltip = document.querySelector('.icon-tooltip');
        if (tooltip) {
            tooltip.remove();
        }
    }
    
    executeAction(action) {
        switch(action) {
            case 'copy':
                this.copyToClipboard();
                break;
            case 'share':
                this.shareContent();
                break;
            case 'download':
                this.downloadFile();
                break;
            default:
                console.log('Action not implemented:', action);
        }
    }
}
```

---

## 7. Иконки для разных состояний

### Статусы и состояния
```
✅ Success - Успешное выполнение
❌ Error - Ошибка
⚠️ Warning - Предупреждение
ℹ️ Info - Информация
⏳ Loading - Загрузка
🔒 Locked - Заблокировано
```

### Прогресс и этапы
```
🔄 Progress - Прогресс выполнения
📊 Status - Статус процесса
🎯 Milestone - Достижение цели
🏁 Finish - Завершение
🚀 Launch - Запуск
📈 Growth - Рост
```

### Интерактивные состояния
```
👆 Hover - При наведении
👆 Active - При активации
👆 Disabled - Отключено
👆 Selected - Выбрано
👆 Focused - В фокусе
👆 Pressed - Нажато
```

---

## 8. Адаптивность иконок

### Responsive иконки
```css
/* Адаптивные размеры иконок */
@media (max-width: 768px) {
    .icon-lg { width: 24px; height: 24px; }
    .icon-xl { width: 32px; height: 32px; }
}

@media (max-width: 480px) {
    .icon-md { width: 20px; height: 20px; }
    .icon-lg { width: 24px; height: 24px; }
}

/* Темная тема */
@media (prefers-color-scheme: dark) {
    .icon {
        filter: invert(1);
    }
    
    .icon-primary { color: #60A5FA; }
    .icon-success { color: #34D399; }
    .icon-warning { color: #FBBF24; }
    .icon-danger { color: #F87171; }
}
```

### Оптимизация производительности
```javascript
// Ленивая загрузка иконок
class LazyIconLoader {
    constructor() {
        this.observer = new IntersectionObserver(this.handleIntersection.bind(this));
        this.init();
    }
    
    init() {
        const iconPlaceholders = document.querySelectorAll('[data-icon]');
        iconPlaceholders.forEach(placeholder => {
            this.observer.observe(placeholder);
        });
    }
    
    handleIntersection(entries) {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                this.loadIcon(entry.target);
                this.observer.unobserve(entry.target);
            }
        });
    }
    
    loadIcon(placeholder) {
        const iconType = placeholder.dataset.icon;
        const iconGenerator = new IconGenerator();
        const icon = iconGenerator.createIcon(iconType);
        
        placeholder.appendChild(icon);
        placeholder.classList.add('icon-loaded');
    }
}
```

---

## Контроль качества

### Критерии оценки иконок
- **Четкость**: Иконки должны быть четкими в любом размере
- **Понятность**: Смысл иконки должен быть очевиден
- **Консистентность**: Единый стиль для всех иконок
- **Доступность**: Поддержка скринридеров и альтернативного текста

### Тестирование
- **Различные размеры**: Проверка качества в разных размерах
- **Различные устройства**: Тестирование на разных экранах
- **Доступность**: Проверка с скринридерами
- **Производительность**: Оптимизация размера файлов

---

### Что делать дальше
- [Анимированные элементы](/ai/visual/animations)
- [Инфографика](/ai/visual/infographics)
- [Получить консультацию](/ai/request)
