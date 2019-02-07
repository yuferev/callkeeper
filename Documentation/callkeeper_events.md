# События CallKeeper

Перечень событий, генерируемых объектом CallKeeper на сайте пользователя:

## События отправляемые для Яндекс метрики:
 
-   callkeeper-open-widget — Открыто окно виджета.
    
-   callkeeper-close-widget — Закрытие окна по другим сценариям.
    
-   callkeeper-call_order-widget — Заказан звонок с виджета.
    
-   callkeeper-open-portable — Открыто окно мобильного callback.
    
-   callkeeper-close-portable — Закрытие мобильного callback.
    
-   callkeeper-call_order-portable — Заказан звонок с мобильного виджета.
    
-   callkeeper-t2c-portable — Нажатие на пункт меню tap2call.
    
-   callkeeper-open-lg — Открытие лидогенератора.
    
-   callkeeper-close-lg — Закрытие лидогенератора.
    
-   callkeeper-call_order-lg — Заказан звонок с лидогенератора.
    
-   callkeeper-call_order-iform — звонок с iForm.
    
-   callkeeper-open-form — Открытие формы «Задать вопрос».
    
-   callkeeper-close-form — Закрытие формы «Задать вопрос».
    
-   callkeeper-call_order-form — Заказан звонок с формы «Задать вопрос».
    
-   callkeeper-telegram-mobile — Открыто приложение Telegram.
    
-   callkeeper-t2c-mobile — Прямой звонок мобильная версия.
    
-   callkeeper-yandexmap-mobile — Открыто приложение Яндекс.Карты мобильная версия.
    
-   callkeeper-yandexnav-mobile — Открыто приложение Яндекс.Навигатор.
    
-   callkeeper-googlemap-mobile — Открыто приложение Google.Карты.
    
-   callkeeper-facebook-mobile — Открыто приложение Facebook.
    
-   callkeeper-vk-mobile — Открыто приложение Vkontakte.
    
-   callkeeper-viber-mobile — Открыто приложение Viber.
    
-   callkeeper-whatsapp-mobile — Открыто приложение WhatsApp.
    
-   callkeeper-call_order-mobile — Заказан звонок в новой мобильной версии.
    
-   callkeeper-open-mobile— Открыт виджет мобильного приложения
    
-   callkeeper-close-mobile — Закрыт виджет мобильного приложения
    
-   callkeeper-link_1-mobile Нажата ссылка спецпредложения в мобильной версии. Порядковый номер выставляется в зависимости от количества установленных на виджете ссылок на спецпредложения
    
-   callkeeper-call_order-formaction — заказан звонок через инструмент formAction
    
-   callkeeper-call_order-ckapp – заказан звонок с CKAPP
    
-   callkeeper-open-ckapp – открыта страница CKAPP
    

## События, отправляемые для Google analytics с сервера

#### категория (eventCategory)

-   callkeeper
    
#### действия (eventAction)

-   call
    
-   call_unique
    
-   call_target
    
-   call_unique/target
    

#### лейбл (eventLabel)

-   widget
    
-   mobile
    
-   carfin
    
-   iform
    
-   active+
    
-   form
    
-   lg
    
-   integration
    
-   facebook
    
-   api
    
-   manual
    
-   ckaction
    
-   vkontakte
    
-   formaction
    

## События, отправляемые для Google analytics с сайта клиента

#### категория (eventCategory)

-   callkeeper
    

#### действия (eventAction)

-   open
    
-   close
    
-   call_order
    
-   t2c
    
-   telegram
    
-   yandexmap
    
-   yandexnav
    
-   googlemap
    
-   facebook
    
-   vk
    
-   viber
    
-   whatsapp
    
-   link_(1 or 2 or 3 ...)
    

  

#### лейбл (eventLabel)

-   widget
    
-   mobile
    
-   portable
    
-   iform
    
-   form
    
-   lg
    
-   formaction
    
-   ckapp
    

## События, отправляемые для dataLayer с сайта клиента

#### имя события

-   callkeeper-open-widget
    
-   callkeeper-close-widget
    
-   callkeeper-call_order-widget
    
-   callkeeper-open-portable
    
-   callkeeper-close-portable
    
-   callkeeper-call_order-portable
    
-   callkeeper-t2c-portable
    
-   callkeeper-open-lg
    
-   callkeeper-close-lg
    
-   callkeeper-call_order-lg
    
-   callkeeper-call_order-iform
    
-   callkeeper-open-form
    
-   callkeeper-close-form
    
-   callkeeper-call_order-form
    
-   callkeeper-telegram-mobile
    
-   callkeeper-t2c-mobile
    
-   callkeeper-yandexmap-mobile
    
-   callkeeper-yandexnav-mobile
    
-   callkeeper-googlemap-mobile
    
-   callkeeper-facebook-mobile
    
-   callkeeper-vk-mobile
    
-   callkeeper-viber-mobile
    
-   callkeeper-whatsapp-mobile
    
-   callkeeper-call_order-mobile
    
-   callkeeper-open-mobile
    
-   callkeeper-close-mobile
    
-   callkeeper-call_order-formaction
    
-   callkeeper-link_(1 or 2 or 3 ...)-mobile
    
-   callkeeper-call_order-ckapp
    
-   callkeeper-open-ckapp
    

#### категория (eventCategory)

-   callkeeper
    

#### действия (eventAction)

-   open
    
-   close
    
-   call_order
    
-   t2c
    
-   telegram
    
-   yandexmap
    
-   yandexnav
    
-   googlemap
    
-   facebook
    
-   vk
    
-   viber
    
-   whatsapp
    

#### лейбл (eventLabel)

-   widget
    
-   mobile
    
-   portable
    
-   iform
    
-   form
    
-   lg
    
-   formaction
    
-   ckapp
    

## Расшифровка событий

#### Категория:

-   callkeeper
    

#### Действия:

-   call = заказан звонок
    
-   call_order = заказан звонок
    
-   open = открыт один из инструментов CallKeeper;
    
-   close = закрыто окно инструмента;
    
-   t2f = нажата кнопка прямого набора номера (tap to call)
    
-   telegram = открыто соответствующее приложение (мобильная версия)
    
-   yandexmap = открыто соответствующее приложение (мобильная версия)
    
-   yandexnav = открыто соответствующее приложение (мобильная версия)
    
-   googlemap = открыто соответствующее приложение (мобильная версия)
    
-   facebook = открыто соответствующее приложение (мобильная версия)
    
-   vk = открыто соответствующее приложение (мобильная версия)
    
-   whatsapp = открыто соответствующее приложение (мобильная версия)
    
-   link_1 = нажата ссылка спецпредложения в мобильной версии. Порядковый номер выставляется в зависимости от количества установленных на виджете ссылок на спецпредложения
    
-   call_unique = уникальный звонок
    
-   call_target = целевой звонок
    
-   call_unique/target = звонок уникальный/целевой
    
#### Лейблы:

-   carfin = звонок с карфина
    
-   active+ = звонок с виджета active+
    
-   form = звонок с формы
    
-   zapier = звонок через zapier
    
-   integration = звонок через инстаграцию (adds progressive)
    
-   api = звонок через api
    
-   manual = звонок запущенный вручную
    
-   facebook = звонок через facebook
    
-   ckaction = звонок через 'ckaction'
    
-   vkontakte = звонок через вконтакте
    
-   formaction = звонок через форму 'formaction'
    
-   widget = звонок через виджет
    
-   mobile = звонок через мобильную версию
    
-   portable = звонок через старую мобильную версию
    
-   iform = звонок через iform
    
-   lg = звонок через лидогенератор
    
-   ckapp = звонок через Ad progressive pages