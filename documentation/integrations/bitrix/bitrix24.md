**Интеграция с Битрикс24**

Туториал по созданию вебхуков Битрикс24 для интеграции с callkeeper доступен по [ссылке](https://yadi.sk/i/mv-X2eNEueCC0Q). При этом, в правах доступа (таймкод на видео-инструкции: 4:30) **важно также поставить галочку у поля CRM.**

**Стандартный список значений который мы передаем вебхуком по звонку на указанный клиентом адрес**

* https://xxxYYYxxx.ru/rest/1/xxx5inncw4l0rxxx/crm.lead.add?
* fields[TITLE]=!%number2&
* fields[NAME]=&
* fields[SECOND_NAME]=&
* fields[LAST_NAME]=&
* fields[STATUS_ID]=NEW&
* fields[OPENED]=Y&
* fields[ASSIGNED_BY_ID]=1&
* fields[OPPORTUNITY]=12500&
* fields[PHONE][0][VALUE]=!%number2&
* fields[PHONE][0][VALUE_TYPE]=WORK&
* fields[ADDRESS_CITY]=!%city&
* fields[ADDRESS_REGION]=!%region&
* fields[ADDRESS_COUNTRY_CODE]=!%country&
* fields[SOURCE_DESCRIPTION]=Обратный звонок CallKeeper&
* fields[UTM_CAMPAIGN]=!%utm_current_campaign&
* fields[UTM_CONTENT]=!%utm_current_content&
* fields[UTM_MEDIUM]=!%utm_current_medium&
* fields[UTM_SOURCE]=!%utm_current_source&
* fields[UTM_TERM]=!%utm_current_term&
* fields[CURRENCY_ID]=RUB&
* fields[HAS_EMAIL]=N&
* fields[HAS_PHONE]=Y&
* fields[SOURCE_ID]=PHONE&
* params[REGISTER_SONET_EVENT]=Y`
