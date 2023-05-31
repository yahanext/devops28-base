# Домашнее задание к занятию 1. «Типы и структура СУБД»

## Введение

Перед выполнением задания вы можете ознакомиться с 
[дополнительными материалами](https://github.com/netology-code/virt-homeworks/tree/virt-11/additional).

## Задача 1

Архитектор ПО решил проконсультироваться у вас, какой тип БД 
лучше выбрать для хранения определённых данных.

Он вам предоставил следующие типы сущностей, которые нужно будет хранить в БД:

- электронные чеки в json-виде,
```
Докумнториентированная бд типа mongodb набор данных всегда разный и чек лучше хранить как документ
```
- склады и автомобильные дороги для логистической компании,
```
графовые бд можно хранить взяимосвязи и направления между обьектами
```
- генеалогические деревья,
```
Иерархическая бд данные в виде древовидной структуры
```
- кэш идентификаторов клиентов с ограниченным временем жизни для движка аутенфикации,
```
бд ключ-значение memcached redis
```
- отношения клиент-покупка для интернет-магазина.
```
реляционные бд обеспечивают связность данных между таблицами,
можно накапливать статистику делать отчеты из различных приложений,
в нашем предприятии используется oracle база размером около 10Тб,
где можно извлечь данные практически обо всем начиная с заказа товара, доставки, продажи
и интеграция с другими бизнес системами
```

Выберите подходящие типы СУБД для каждой сущности и объясните свой выбор.

## Задача 2

Вы создали распределённое высоконагруженное приложение и хотите классифицировать его согласно 
CAP-теореме. Какой классификации по CAP-теореме соответствует ваша система, если 
(каждый пункт — это отдельная реализация вашей системы и для каждого пункта нужно привести классификацию):

- данные записываются на все узлы с задержкой до часа (асинхронная запись);
```
CA целостнсть данных есть, но не всегда одинаковы в конкретный момент времени
в узлах кластера впрос к конкретной реализации в реальной жизни
```
- при сетевых сбоях система может разделиться на 2 раздельных кластера;
```
CP есть устойчивость к разделению но с с вопросами к доступности
```
- система может не прислать корректный ответ или сбросить соединение.
```
AP как пример днс сервера, где не получение ответа от одного сервера не гарантирует запрос к другому
```
Согласно PACELC-теореме как бы вы классифицировали эти реализации?

## Задача 3

Могут ли в одной системе сочетаться принципы BASE и ACID? Почему?
```
нет т.к принципы противоречат друг другу и в реалиях все зависит от требований бизнеса
для бухучета одно для веб другое
```

## Задача 4

Вам дали задачу написать системное решение, основой которого бы послужили:

- фиксация некоторых значений с временем жизни,
- реакция на истечение таймаута.

Вы слышали о key-value-хранилище, которое имеет механизм Pub/Sub. 
Что это за система? Какие минусы выбора этой системы?
```
redis
из плюсов 
быстро просто недорого
но есть минусы
однопоточность
все хранится в озу и требовательна к памяти
нет разделения доступа
запросы не sql
```

---

### Как cдавать задание

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---

