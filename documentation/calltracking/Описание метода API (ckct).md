# Метод получения звонков пользователя

https://ckct.ru/api/index.php?{{format}}/{{version}}/{{api_key}}/call/get/{{page}}/{{time_start}}/{{time_end}}
______
## Где:

- format - формат возвращаемых данных, может быть равен: `xml`, `json`, `plain`, `csv`
- version - версия апи, пока существует только `v1`
- api_key - апи ключ пользователя
- page - порядковый номер страницы (начинается с 0)
- time_start - время начала интервала (формат timestamp)
- time_end - время конца интервала (формат timestamp)

## Формат ответа в json такой:

```
{
"inbound":
{
"requestedType":"json",
"requestedEntity":"call",
"requestedMethod":"get",
"requestedVersion":"v1",
"requestedParams":
{
"requirePage":0,
"startDate":0,
"endDate":1563279164
},
"pageLength":1000,
"totalLength":2490,
"ofPages":3,
"contentLength":722709
},
"info":
{
"entities":
{
"call":["get"],
"callrole":["get"],
"phone":["get"],
"user":["get"],
"campaign":["get"],
"tag":["get"]
},
"types":["json","plain","csv","xml"],
"versions":["v1"]
},
"payload": 
[
{
"city":"-",
"site":"-",
"state":"720/200",
"callId":1337486,
"device":"-",
"record":null,
"region":"-",
"tagsId":[],
"utmTerm":"-",
"audition":"Не прослушано",
"callType":"Динамический коллтрекинг",
"clientIp":"-",
"duration":0,
"timeStart":null,
"utmMedium":"-",
"utmSource":"-",
"campaignId":559,
"officeName":"Тестовый",
"routePhone":"79999999999",
"sourceType":"-",
"utmContent":"-",
"clientPhone":"79999999999",
"officePhone":"79999999999",
"utmCampaign":"-",
"campaignName":"Тест",
"stateDescription":"Неизвестная ошибка оператора связи"
}
]
}

```
### inbound - информация о текущем запросе

- inbound.requestedType - запрошенный тип
- inbound.requestedEntity - вызванная сущность 
- inbound.requestedMethod - вызванный метод апи
- inbound.requestedVersion - использованная версия апи
- inbound.requestedParams.requirePage - отображаемая страница
- inbound.requestedParams.startDate - начало периода
- inbound.requestedParams.endDate - конец периода
- inbound.pageLength - максимальное количество звонков на одной странице
- inbound.totalLength - общее количество звонков за указанный в запросе период
- inbound.ofPages - всего страниц
- inbound.contentLength - длина контента на странице

### info - информация о возможных запросах к АПИ

- info.entities - каждое название свойства объекта соответствует названию сущности апи, а значение соответствует методам этой сущности.
- info.types - возможные форматы ответа
- info.versions - возможные версии АПИ

### payload - запрашиваемые данные, в данном случае звонки					
- payload[].city - город клиента
- payload[].site - сайт
- payload[].state - статус звонка
- payload[].callId - идентификатор звонка 
- payload[].device - устройство
- payload[].record - запись звонка
- payload[].region - регион
- payload[].tagsId - массив id тэгов
- payload[].utmTerm - utm_term
- payload[].audition - прослушана-ли запись звонка из ЛК КТ
- payload[].callType - тип звонка
- payload[].clientIp - ip клиента
- payload[].duration - продолжительность звонка
- payload[].timeStart - дата начала звонка
- payload[].utmMedium - utm_medium
- payload[].utmSource - utm_source
- payload[].campaignId - id кампании
- payload[].officeName - название офиса
- payload[].routePhone - номер коллтрекинга
- payload[].sourceType - тип источника
- payload[].utmContent - utm_content
- payload[].clientPhone - номер телефона клиента
- payload[].officePhone - номер телефона офиса
- payload[].utmCampaign - utm_campaign
- payload[].campaignName - название кампании
- payload[].stateDescription - описание статуса
