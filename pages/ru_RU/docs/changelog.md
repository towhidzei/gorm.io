---
title: Список изменений
layout: страница
---

## v2.0 - 2020.08

GORM 2.0 переписан с нуля, представляет некоторые изменения несовместимых API и много улучшений

* Улучшение производительности
* Модульность
* Поддержка Context, Batch Insert, Prepared Statment Mode, DryRun Mode, Join Preload, Find To Map, Create From Map, FindInBatches
* Поддержка Вложенных транзакция/SavePoint/RollbackTo
* Named Argument, Group Conditions, Upsert, Locking, Optimizer/Index/Comment Hints supports, SubQuery improvements
* Поддержка полноправных связей, улучшение таблиц, режим ассоциации для пакетных данных
* Поддержка нескольких полей для времени создания/обновления, которые добавляют поддержку UNIX (nano) секунд
* Поддержка прав доступа полей: только для чтения, только для записи, только для создания, только для обновления, игнорируется
* Новая система плагинов: несколько баз данных, чтение/запись поддержка разделения с плагином База данных Resolver, интеграция Prometheus ...
* Новый Hooks API: единый интерфейс с плагинами
* Новый мигратор: позволяет создавать внешние ключи для связей, поддержка constraints/checker, расширенная поддержка индексов
* Новый логгер: контекстная поддержка, улучшено расширение
* Стратегия именования: правила для имени таблицы, имени поля, имяени таблицы join, foreign key, checker, index
* Улучшенная поддержка настраиваемых типов данных (например, JSON)

[GORM 2.0 Информация по релизу](v2_release_note.html)

## v1.0 - 2016.04

[GORM V1 Документация](https://v1.gorm.io)

Критические изменения:

* `gorm.Open` возвращает `*gorm.DB` вместо `gorm.DB`
* Обновление будет обновлять только измененные поля
* Мягкое удаление будет только обновлять поле `deleted_at IS NULL`
* Новая логика ToDBName Общие правила из [golint](https://github.com/golang/lint/blob/master/lint.go#L702) такие как `HTTP`, `URI` были преобразованы в нижний регистр, поэтому `HTTP`в БД будет `http`, но не `h_t_t_p`, для некоторых других правил которых нет в списке, таких как `SKU`, имя в БД было `s_k_u`, это исправлено на `sku`
* Ошибка `RecordNotFound` была переименована в `ErrRecordNotFound`
* `mssql` диалект был переименован в `github.com/jinzhu/gorm/dialects/mssql`
* `Hstore` был перемещен в пакет `github.com/jinzhu/gorm/dialects/postgres`
