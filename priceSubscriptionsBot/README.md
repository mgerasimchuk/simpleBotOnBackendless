# "Исходники" n1PriceSUbscriptionsBot на codeless

Данный бот при получении сообщения с ссылкой на объявление, например - `https://novosibirsk.n1.ru/view/27028105/`,
сохраняет информацию о цене объявления, и при ее изменении, он уведомляет пользователя об этом.

## Функции хелперы

### getChatId - Выдерает идентификтаор чата, из данных, приходящих от телеграм
![getChatId](images/getChatId.png)

### sendMessage - Отправляет сообщение в телеграм
![sendMessage](images/sendMessage.png)

### getOfferIdFromUrl Вычленяем идентификатор объявления из урла

Смысл функции прост, чтобы вычленить id, нам надо найти cтартовую позиция подстроки `n1.ru/view/`,
после этого обрезаем ее слева, и далее находим первый символ `/` или если его нет, то позицией окончания строки,
будет длина этой строки.
Ну и все, берем substring и получаем идентификатор.  
(надеюсь понятно объяснил)

![getOfferIdFromUrl](images/getOfferIdFromUrl.png)

### getOffer - Ходим в n1 и получаем данные по объявлению
![getOffer](images/getOffer.png)

### getOfferPrice
![getOfferPrice](images/getOfferPrice.png)

## Главные методы

### offerPriceChecker (нажмите кнопку deploy, а не save, деплой сделает сразу запуск таймера)
![offerPriceChecker](images/offerPriceChecker.png)

### incoming - Обрабатывает все сигналы, которые приходят от серверов telegram(обрабатывает все входящие сообщения от пользователя)
![incoming](images/incoming.png)

## Остальное

### Структура таблицы Subscriptions - тут будут сохранятся все подписки на объявления
![db](images/db.png)

### Таймеры
![timers](images/timers.png)
