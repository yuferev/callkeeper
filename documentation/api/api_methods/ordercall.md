# Новый метод API orderCall

Новый метод API **orderCall** - позволяет заказать звонок с упрощенным форматом данных

Большинство параметров остались неизменными, как при заказе методом **makeCalls**.

Отличие заключается в том, что метод **orderCall** принимает параметры без вложенных массивов, таких как *calls* и *utm* в методе **makeCalls**, что упрощает составление запроса.

Также метод **orderCall** в автоматическом режиме определяет тип источника перехода и правильно его обрабатывает без передачи дополнительных параметров.

Важное отличие в том, что вместо ключа *utm_type* используется ключ **referrer**, который содержит сведения об адресе сайта, с которого произошел переход (для простоты сюда можно просто скопировать содержимое js-переменной **document.referrer**). Это избавляет клиента, настраивающего интеграцию, от необходимости самому разбираться в том, что считается рекламным переходом, реферальным или поисковым.

Пример строки запроса, для передачи методом GET:

https://api.callkeeper.ru/orderCall?unique=any_string&apiak=XXXXXXXXXX&whash=xxxxxxxxxxxxxxx&utc=europe/moscow&opening_hours=10002000&notification=your@email.ru&tool_name=name&ga_client_id=1245784512.3256897854&ip_client=192.168.0.1&interval=5,10,15&client=71234567890&manager=0&text_to_manager=text_to_manager&info_to_manager=info_to_manager&external_service_identifier=123456&time_to_call=1522222222&site=callkeeper.ru&utm_source=utm_source&utm_medium=utm_medium&utm_campaign=utm_campaign&utm_content=utm_content&utm_term=utm_term&entry_point=my.site.ru/any/page/&user_agent=user_agent&referrer=yandex.ru

Пример php кода для заказа методом POST:

```php
$url_vars = [

"unique" => "any_string",

"apiak" => "XXXXXXXXXX",

"whash" => "xxxxxxxxxxxxxxx",

"utc" => "europe/moscow",

"opening_hours" => "10002000",

"notification" => "your@email.ru",

"tool_name" => "name",

"ga_client_id" => "1245784512.3256897854",

"ip_client" => "192.168.0.1",

"interval" => "5,10,15",

"referrer" =>  "yandex.ru",

"client" => "71234567890",

"manager" => "1",

"text_to_manager" => "text_to_manager",

"info_to_manager" => "info_to_manager",

"external_service_identifier" => "123456",

"time_to_call" => "1522222222",

"site" => "my.site.ru",

"utm_source" => "utm_source",

"utm_medium" => "utm_medium",

"utm_campaign" => "utm_campaign",

"utm_content" => "utm_content",

"utm_term" => "utm_term",

"entry_point" => "my.site.ru/any/page/",

"user_agent" => "user_agent"

];

$url = "https://api.callkeeper.ru/orderCall";

$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, $url);

curl_setopt($ch, CURLOPT_HEADER, false);

curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

curl_setopt($ch, CURLOPT_POST, true);

curl_setopt($ch, CURLOPT_POSTFIELDS, $url_vars);

curl_setopt($ch, CURLOPT_CONNECTTIMEOUT, 30);

$response = curl_exec($ch);

curl_close($ch);

```

### Все параметры и их значения

- "unique" => "any_string", //название компании, любая число-буквенная строка без спецсимволов

- "apiak" => "XXXXXXXXXX", //ключ сгенерированный в ЛК во вкладке Профиль

- "whash" => "xxxxxxxxxxxxxxx", //hash виджета, из которого будут взяты необходимые параметры для звонка, можно получить на странице редактирования виджета в ЛК

- "utc" => "europe/moscow", //временная зона в формате IANA Time Zone Database(Europe/Moscow) или в формате ±hhmm("UTC+03:00")

- "opening_hours" => "10002000", // время работы компании (время когда можно принимать звонки от клиентов).

- "notification" => "your@email.ru", //email для уведомлений о статусе звонка

- "tool_name" => "name", //название инструмента с которого был заказан звонок

- "ga_client_id" => "1245784512.3256897854", //уникальный идентификатор пользователя для отправки в Google Analytics

- "ip_client" => "192.168.0.1", // ip адрес клиента

- "interval" => "5,10,15", //интервалы для перезвона

- "referrer" =>  "yandex.ru", //содержит сведения о адресе сайта с которого произошел переход (для простоты сюда можно просто скопировать содержимое js переменной document.referrer)

- "client" => "71234567890", //номер телефона клиента, на который поступит звонок

- "manager" => "1", //номер телефона компании, на который поступит звонок, либо порядковый номер офиса, указанного в настройках виджета (важно: нумерация начинается с 0)

- "text_to_manager" => "text_to_manager", //произвольный текст, который будет проговариваться в начале каждого звонка

- "info_to_manager" => "info_to_manager", //дополнительный текст, который будет проговариваться только при нажатию кнопки на телефоне (указана в настройках виджета)

- "external_service_identifier" => "123456", //идентификатор внешнего сервиса

- "time_to_call" => "1522222222", //заказ отложенного звонка, передается желаемое время звонка в формате Timestamp

- "site" => "my.site.ru", //название сайта, которое будет отображено в информации о звонке.

- "utm_source" => "utm_source", //источник перехода по рекламе

- "utm_medium" => "utm_medium", //тип трафика

- "utm_campaign" => "utm_campaign", //обозначение рекламной кампании

- "utm_content" => "utm_content", //содержание кампании

- "utm_term" => "utm_term", //условие поиска кампании

- "entry_point" => "my.site.ru/any/page/", //адрес перехода пользователя

- "user_agent" => "user_agent", //название и версия Браузера и ОС клиента
