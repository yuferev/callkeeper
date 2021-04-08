## Метод получения звонков пользователя

https://ckct.ru/api/index.php?format/version/api_key/call/get/page/time_start/time_end

* format  — формат возвращаемых данных, может быть равен: xml, json, plain,  csv
* version — версия  API
* api_key  — API ключ  пользователя
* page — порядковый номер страницы (начинается с  0)
* time_start  — время начала интервала (формат  timestamp)
* time_end  — время конца интервала (формат  timestamp)

## Формат ответа в JSON


{
  "inbound":
    {





"requestedType":"json", "requestedEntity":"call", "requestedMethod":"get", "requestedVersion":"v3", "requestedParams":
  {

          "requirePage":0, "startDate":0, "endDate":1563279164
        },





    },
  "info":
    {


"pageLength":1000, "totalLength":2490, "ofPages":3, "contentLength":722709



"entities":
  {

          "call":["get"],
          "callrole":["get"],
          "phone":["get"],
          "user":["get"],
          "campaign":["get"],
          "tag":["get"]
        },



},
"payload":
[


"types":["json","plain","csv","xml"], "versions":["v3"]



{

        "city":"-",
        "site":"-",
        "state":"720/200", "callId":1337486,
        "device":"-", "record":null, "region":"-",
        "tagsId":[],
        "utmTerm":"-", "audition":"Не  прослушано",
        "callType":"Динамический  коллтрекинг", "clientIp":"-",
        "duration":0, "timeStart":null, "utmMedium":"-",
        "utmSource":"-", "campaignId":559, "officeName":"Тестовый",

        "routePhone":"79999999999", "sourceType":"-",
        "utmContent":"-", "clientPhone":"79999999999", "officePhone":"79999999999", "utmCampaign":"-", "campaignName":"Тест",
        "stateDescription":"Неизвестная ошибка оператора связи"
      }
    ]
}

## inbound  — информация о текущем  запросе

inbound.requestedType — запрошенный тип inbound.requestedEntity — вызванная сущность inbound.requestedMethod — вызванный метод inbound.requestedVersion — использованная версия API  inbound.requestedParams.requirePage — отображаемая  страница inbound.requestedParams.startDate — начало периода inbound.requestedParams.endDate — конец  периода
inbound.pageLength — максимальное количество звонков на одной странице inbound.totalLength — общее количество звонков за указанный в запросе период inbound.ofPages — всего страниц
inbound.contentLength — длина контента на странице

## info  — информация о возможных запросах к API

info.entities — каждое название свойства объекта соответствует названию сущности API, а значение соответствует методам этой сущности
info.types — возможные форматы ответа
info.versions — возможные версии API

## payload  — запрашиваемые данные о звонках

payload[].city — город клиента
payload[].site — сайт
payload[].device — устройство пользователя payload[].clientIp — IP клиента payload[].region — регион
payload[].clientPhone — номер телефона клиента payload[].officePhone — номер телефона офиса payload[].routePhone — номер коллтрекинга  payload[].callId — идентификатор звонка payload[].timeStart — дата начала звонка payload[].duration — продолжительность звонка payload[].state — статус звонка payload[].stateDescription — описание статуса payload[].record — запись звонка
payload[].audition — статус о прослушивании звонка в ЛК
payload[].callType — тип звонка payload[].sourceType — тип источника payload[].campaignId — id кампании payload[].campaignName — название кампании payload[].officeName — название офиса payload[].tagsId — массив id тегов payload[].utmSource — utm_source  payload[].utmMedium — utm_medium  payload[].utmCampaign — utm_campaign  payload[].utmTerm — utm_term  payload[].utmContent — utm_content
