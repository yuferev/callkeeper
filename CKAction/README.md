# CKAction
Это специальный endpoint API CallKeeper для простого запуска звонков с форм на сайте.

```
https://api.callkeeper.ru/formReceiver
```

Пример [в конце](#пример-обработчика-формы).

## Параметры запроса:

- [isSend](#issend)
- [backUrl](#backurl)
- [widgetHash](#widgethash)
- [responseMethod](#responsemethod)
- [cookiesBasket](#cookiesbasket)
- [phone](#phone)
- [form_name](#form_name)

### `isSend`
* *(Empty)*

Если передан в запросе, то данные с формы после запуска звонка будут переданы внешнему обработчику по адресу `backUrl`.

### `backUrl`
* *(String)*

Адрес страницы, куда CallKeeper должен передать данные из формы после запуска звонка.

Пример: `backUrl = 'https://mysite.ru/form/email.php'`

### `widgetHash`
* *(String)*

Идентификатор виджета CallKeeper.

Пример: `widgetHash = '7682e50360c12bce7ccf5d14c2330bf2'`

### `responseMethod`
* *(String) ['POST | 'GET']*

Метод, которым CallKeeper передает данные с формы по адресу `backUrl`.

Пример: `responseMethod = 'GET'`

### `cookiesBasket`
* *(String)*

Данные по визиту.

Пример: `cookiesBasket = 'current:::typ=utm|||src=actioncall|||mdm=cpc|||cmp=lpnoscript|||cnt=(none)|||trm=(none)^#^#session:::cpg=https://example.com/example/^#^#'`

> Если на сайте подключен скрипт CallKeeper, то проще использовать специальный метод
> ```
> cookiesBasket = CallKeeper.f.justCookies()
> ```

### `phone`
* *(String)*

Номер телефона клиента.

Пример: `phone = '79998886655'`

### `tel`
* *Alias [phone](#phone)*

### `telephone`
* *Alias [phone](#phone)*

### `number`
* *Alias [phone](#phone)*

### `phone_number`
* *Alias [phone](#phone)*

### `form_name`
* *(String)*

Название формы, которые будет проговариваться при звонке.

### `form_title`
* *Alias [form_name](#form_name)*


## Пример обработчика формы

```js
var callkeeperUrl = '//api.callkeeper.ru/formReceiver';
var phone = '79998887766'; //номер телефона из поля формы
var backUrl = window.location.href; //здесь может быть любой стандартный обработчик. Например, отправка заявки на почту
var form_title = 'Заказ звонка'; //название формы, которе будет проговариваться при звонке
var cookiesBasket = window.CallKeeper ? CallKeeper.f.justCookies() : encodeURIComponent('current:::typ=utm|||src=actioncall|||mdm=cpc|||cmp=lpnoscript|||cnt=(none)|||trm=(none)^#^#session:::cpg=https://example.com/example/^#^#'); // в случае если код CallKeeper не подключен - статичные cookies
var widgetHash = 'xxxxxxxxxxxxxxxxx';
var args = 'isSend&widgetHash='+widgetHash+'&phone='+phone+'&backUrl='+backUrl+'&cookiesBasket='+cookiesBasket+'&form_title='+form_title;

$.post( callkeeperUrl, args, function( data ) {
	console.log(data);
});
```

## Рекомендация по использованию dataLayer совместно с ckAction:

Чтобы получать события заказа звонка в dataLayer, необходимо после отправки запроса ckAction вызывать следующий код:

```js
window.dataLayer.push({
    event: 'callkeeper-call_order-ckaction',
    eventCategory: 'callkeeper',
    eventAction: 'call_order',
    eventLabel: 'ckaction'
});
```

При условии того что на сайте установлен GTM после выполнения данного кода в объекте dataLayer должно появится следующее поле

![Рис 1](images/ckAction_1)

[Вернуться](/README.md)
