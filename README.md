# Fraud Detection Engine

![Production Ready](https://img.shields.io/badge/production-ready-brightgreen)
![Version](https://img.shields.io/badge/version-6.2-blue)
![Go Version](https://img.shields.io/badge/go-1.25-00ADD8)
![License](https://img.shields.io/badge/license-Apache%202.0-blue)

> **Pro-grade антифрод система на Golang для real-time скоринга транзакций**

---

## Описание

Fraud Detection Engine — готовая к продакшену антифрод система, разработанная для российского e-commerce и финтех рынка.

Сервис помогает бизнесу принимать решение по каждой транзакции в реальном времени: **пропустить**, **отправить на ручную проверку** или **заблокировать**.

## Ключевые характеристики

| Параметр | Значение |
|----------|----------|
| **Throughput** | 1000+ RPS |
| **P95 Latency** | 4.2ms |
| **P99 Latency** | 46ms |
| **Success Rate** | 100% |
| **Test Coverage** | 155+ tests |
| **Compliance** | 152-ФЗ |

## Возможности

### 🚀 Performance
- Real-time скоринг транзакций через REST API
- Высокая пропускная способность для production нагрузки
- Оптимизированная обработка с минимальной задержкой

### 🧠 Machine Learning
- ML-модели для определения мошеннических паттернов
- Извлечение признаков для точного скоринга
- Калибровка вероятностей

### 🔒 Безопасность
- 152-ФЗ compliance (PII masking)
- TLS/HTTPS шифрование
- API key аутентификация
- Аудит всех транзакций

### 👥 Multi-tenancy
- Изоляция данных между клиентами
- Персонализированные модели для каждого tenant
- Гибкая конфигурация правил

### 📊 Explainability
- Объяснение каждого решения
- Feature contributions для анализа
- Прозрачность для бизнеса и регуляторов

## Архитектура

```
Client → API Gateway → Auth → Idempotency → Scoring → Decision → Persist
```

- **Sync mode** — мгновенный ответ (200 OK)
- **Async mode** — асинхронная обработка (202 Accepted)
- **Idempotency** — защита от дублирующих запросов

## Быстрый старт

```bash
# Запуск сервера
go run cmd/server/main.go

# Тестовый запрос
curl -X POST http://localhost:8080/v1/score \
  -H "Content-Type: application/json" \
  -H "X-API-Key: your_key" \
  -d '{"transaction_id": "tx_001", "amount": 5000, "currency": "RUB"}'
```

## Технологический стек

- **Language:** Go 1.25+
- **Database:** PostgreSQL 16
- **Cache:** Redis 7
- **ML:** Random Forest (custom implementation)
- **Monitoring:** Prometheus + Grafana
- **Deployment:** Docker + Docker Compose

## Лицензия

Apache License 2.0 — свободное использование с указанием авторства.

---

## Для разработчиков

Исходный код доступен в приватном репозитории:

🔗 **https://github.com/turkprogrammer/Fraud-Detection-Engine**

Для получения доступа свяжитесь с автором.

---

## Контакты

- **Author:** Юсупов Роберт Рахимович
- **GitHub:** [@turkprogrammer](https://github.com/turkprogrammer)
- **Telegram:** [@turanellervarolsun](https://t.me/turanellervarolsun)
- **Portfolio:** [yusupov-tech.ru](https://yusupov-tech.ru)

---

<p align="center">
  <i>Built with ❤️ for Russian e-commerce & fintech</i>
</p>
