# PHP Mentorship. Part 5
Пятое занятие по PHP. Снова возвращаемся к фреймворкам и некоторые упоминания об Docker. Занятие проходило в среду, 16 сентября 2015.

## Docker

Будущее за ним и все такое. В двух словах — система виртуализации на уровне операционной системы. Это значит, что приложения можно запускать в отдельных изолированных пространствах со своими собственными прибамбасами — диски, сетевые настройки и т. п. Более подробно, видимо, будем рассматривать как-нибудь в будущем. Сам Арсений уже активно это использует.

## Symfony2. Фреймворк

Мы продолжаем знакомиться с фреймворком Symfony2. На занятии была предпринята попытка объяснить базовые понятия фреймворка и показать в общих чертах где что лежит.

Были затронуты [Bundles](https://symfony.com/doc/current/book/bundles.html) — компоненты, из которых состоит весь фреймворк. Это что-то вроде плагинов. Даже само ядро Symfony это отдельный Bundle.

[Шаблоны](https://symfony.com/doc/current/book/templating.html). Во фреймворке используется Twig для рендера HTML-чика, если можно так выразиться.

### Инструменты

Не стоит забывать, что вместе с Symfony можно получить инструмент для командой строки, который упростит жизнь. Например, там будет встроенный PHP-сервер или можно создать дефолтный бандл для своих задач.

### Полезные ссылки

 * [Официальная документация](https://symfony.com/doc/current/book/index.html). Доступна на английском, французском и итальянском.
 * [Пошаговые уроки по созданию блога на Symfony](http://tutorial.symblog.co.uk).
