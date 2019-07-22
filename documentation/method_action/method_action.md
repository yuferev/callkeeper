# Метод Action

 
**Метод Action**— сценарий запуска обратного звонка при отправке заявок с сайта. Метод позволяет обрабатывать 99% заявок с форм вашего сайта.

## Принцип подключения и работы метода Action:

1.  Сотрудник клиента (технический специалист) прописывает в код формы URL-адрес сервера CalKeeper.
  
2.  Посетитель сайта заполняет форму. После нажатия кнопки «отправить» данные с формы отправляются браузером посетителя в сторону сервера CallKeeper.
    
3.  Сервер CallKeeper получает уведомление, происходит валидация номера (+7 и далее 10 цифр).
    
4.  На основании этих данных запускается сценарий обратного звонка в соответствии с настройками виджета.
    
5.  Параллельно сервер CallKeeper отправляет почтовое уведомление о заполненной форме на сервер клиента. Настройка получателей и формат отправки изменяется на стороне клиента (например, в CMS сайта).
    
6.  По завершении сценария обратного звонка клиент получает стандартное уведомление от CallKeeper со статусом.
    
7.  Вся информация по заявке отображается в личном кабинете с указанием названия формы, имени посетителя, UTM-меток и т.д.
    

## Примеры кода для работы метода Action и важные комментарии:

* Самый простой случай, когда нужно запустить только звонок:

 ```php 
<form method="POST"

action="https://api.callkeeper.ru/formReceiver?widgetHash=хххххххххххххххххххххххх">

<inputname="name">

<inputname="phone">

</form>
```
  

* Первый вариант: отправка серверу Callkeeper звонок:

```php   
<form method="POST"

action="https://api.callkeeper.ru/formReceiver?backUrl=you/action&isSend

&widgetHash=хххххххххххххххххххххххх8&responseMethod=POST">

<inputname="name">

<inputname="phone">

</form>
```  

* Ссылка, которая отвечает за обратный адрес. Например, если нужно вернуть данные обратно на сервер клиента:

``` php 
backUrl=you/action/form/path
```
   
* Параметр, с помощью которого клиент может получить от Callkeeper данные с формы:
```php
isSend
```

* Hash виджета. Полный вариант:
```php
widgetHash=хххххххххххххххххххххххх
```
  
* Метод, которым CalKeeper передает данные на сервер клиенту с формы— GET и POST (по умолчанию)
```php 
responseMethod=POST
```
* Флаг, который используется, если после отправки заявки, идет переадресация на другую страницу:
```php
isRedirect
```

* Адрес для отправки форм в CalKeeper:

```php
https://api.callkeeper.ru/formReceiver
```
  
* По умолчанию может обрабатываться номер телефона, имя пользователя и имя формы. Значения в атрибуте name могут быть любыми:

``` php
<form method="POST"

action="[https://api.callkeeper.ru/formReceiver](https://api.callkeeper.ru/formReceiver)?

backUrl=you/action&isSend&widgetHash=хххххххххххххххххххххххх8&responseMethod=POST"> <inputname="name">

<inputname="form_name">

<inputname="tel">

</form>
```
 
* Скрипт, с помощью которого можно собирать данные по посещению:

```php  
<form method="POST"

action="[https://api.callkeeper.ru/formReceiver](https://api.callkeeper.ru/formReceiver)?

backUrl=you/action&isSend&widgetHash=хххххххххххххххххххххххх8&responseMethod=POST">

<inputname="name">

<inputname="form_name">

<inputname="tel">

<script>document.querySelectorAll('[actionˆ="http://api.callkeeper.ru/"]').forEach(function(e){

e.setAttribute('action',e.getAttribute('action')+'&cookiesBasket='+CallKeeper.f.justCookies());

});</script>

</form>

 ``` 

* Скрипт, для того, чтобы отправлять запросы из javascript в обход браузера:

  
```php 
<form method="POST"

action="https://api.callkeeper.ru/formReceiver?

backUrl=you/action&isSend&widgetHash=хххххххххххххххххххххххх8&responseMethod=POST">

<inputname="name">

<inputname="form_name">

<inputname="tel">

<script>document.querySelectorAll('[actionˆ="https://api.callkeeper.ru/"]').forEach(function(e){

e.setAttribute('action',e.getAttribute('action')+'&cookiesBasket='+CallKeeper.f.justCookies());

});</script>

<script>

(function(){

var xhr=newXMLHttpRequest;

xhr.open('POST','https://api.callkeeper.ru/formReceiver?

backUrl=you/action&isSend&widgetHash=хххххххххххххххххххххххх8&responseMethod=POST’);

xhr.setRequestHeader(‘Content-Type’ , ‘application/x-www-form-urlencoded’);

xhr.send((function(){vardata='';[].map.call(document.forms['my-form'].elements,

(i)=>{returndata+=i.name+'='+i.value+'&';});

returndata.substring(0,data.length-1);})())

})()</script>

</form>
```
  

* Отправка любой формы по методу action с использованием id формы (formID-это Id формы):

  
```php 
<script>

var xhr=newXMLHttpRequest;

xhr.open("POST","https://api.callkeeper.ru/formReceiver? backUrl=you_real_back_url&isSend&widgetHash=you_widget_hash&responseMethod=POST&cookiesBasket="+ CallKeeper.f.justCookies()),

xhr.send(newFormData(document.getElementById(formID)));

</script>
```
  
 
* Если пользователь хочет получать события в datalayer, то нужно добавить следующий скрипт:

  
```php
window.dataLayer.push({

event: "callkeeper-call_order-ckaction",

eventCategory: "callkeeper",

eventAction: "call_order",

eventLabel: "ckaction"

});
```
