# Анализатор журнала запросов

Найди маршруты с ошибками за время инцидента по журналу, который целиком не помещается в память.

**Этап 03** · Java 21 · Collections · Stream API

[Этап 03](https://github.com/1ommyFi7in/java-backend-roadmap/blob/main/%D0%9E%D0%B2%D0%B5%D1%80%D0%B2%D1%8C%D1%8E.md#03-%D0%BA%D0%BE%D0%BB%D0%BB%D0%B5%D0%BA%D1%86%D0%B8%D0%B8-stream-api-%D0%B8-%D0%BF%D0%B0%D1%82%D1%82%D0%B5%D1%80%D0%BD%D1%8B) · [Техническое задание](SPECIFICATION.md) · [Весь маршрут](https://github.com/1ommyFi7in/java-backend-roadmap)

> [!NOTE]
> Учебное задание. В репозитории находятся постановка, примеры и критерии приёмки. Реализацию добавляй по мере прохождения этапа.

## Результат этапа

| Что собрать | Что отработать |
| --- | --- |
| CLI с двумя режимами, входные фикстуры и сравнение отчётов. | Потоковое чтение, группировка, Strategy, детерминированная выдача. |

## Как выглядит результат

```text
2026-01-15T09:00:00Z;/orders;200;30
2026-01-15T09:01:00Z;/orders;503;70
2026-01-15T09:02:00Z;/products;200;20
bad line
```

```text
> analyze requests.log --mode stream
REQUESTS 3
ERRORS 1
SKIPPED 1
TOP /orders 2
TOP /products 1
AVG /orders 50.00 ms
AVG /products 20.00 ms
```

В stderr появится `line 4: invalid format`.

## Проверка перед сдачей

- [ ] Сравнить режимы на примере, пустом файле, границе периода и равных частотах. Ручной расчёт по контрольному файлу из 20 строк совпадает с отчётом.

## Начать работу

```sh
git clone https://github.com/1ommyFi7in/java-request-log-analyzer.git
cd java-request-log-analyzer
```

Открой [техническое задание](SPECIFICATION.md), подготовь входные данные и начни с основного сценария. Команды запуска и проверок добавь после первого рабочего прогона.

[← Библиотека с выдачей книг](https://github.com/1ommyFi7in/java-library-lending) · [Подготовка рабочего цикла →](https://github.com/1ommyFi7in/java-maven-workspace)
