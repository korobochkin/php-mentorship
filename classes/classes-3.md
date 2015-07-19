# PHP Mentorship. Part 3
Лог ключевых мыслей и ссылок из третьего занятия по PHP. Занятие проходило 18 и 19 июля 2015.

Мы так и не определились какой именно фреймвор брать Yii или Symfony. Я за второй, но вокруг него сложился некий ореол «сложности», хотя что именно там сложнее непонятно, ведь не нужно разбираться в высшей математике, чтобы использовать Symfony.

## Аудит кода
В плагине [reCAPTCHA Lightweight Adaptation](https://github.com/korobochkin/reCAPTCHA-Lightweight-Adaptation) мне посоветовали разбить функцию [Recaptcha_Lightweight_Adaptation_API::validate()](https://github.com/korobochkin/reCAPTCHA-Lightweight-Adaptation/blob/v1.0.0/plugin/inc/class-api.php#L82) для проверки данных на несколько более мелких, для лучшей читабельности кода. Второе замечание касалось «namespaces» — нужно попробовать переписать все классы с их использованием.

## Автозагрузка
Функция [`spl_autoload_register()`](http://php.net/manual/ru/function.spl-autoload-register.php) позволяет делать автозагрузчик — функция, которая вызывается при отсутствии какого-то класса и пытается сделать `require` или `include` определенного файла с недостающим классом. Автозагрузчиков может быть несколько и все они работают по очереди. [Живой пример](https://github.com/jbrinley/wp-forms/blob/0.4/classes/WP_Form_Plugin.php#L45).

## [Vagrant](https://www.vagrantup.com)
Система для работы с виртуальными машинами. Про ее использование и настройку можно почитать в официальной документации. Отмечу, что для WordPress есть готовый репозиторий [VVV](https://github.com/Varying-Vagrant-Vagrants/VVV) с уже полностью готовым Вагрантом для создания сайтов под WordPress.

Есть сайт [puphpet.com](https://puphpet.com), с помощью которого можно создавать конфигурации виртуальных машин через интерфейс с кнопочками и потом использовать эти файлы-конфигурации в Vagrant :)

[Vagrant для разработки под Laravel](http://laravel.su/docs/5.0/homestead)

# Git
[Видео](http://laravel.su/docs/5.0/homestead), по которому некоторые осваивают Git. Я бы также рекомендовал книжку про Git — [на английском](https://git-scm.com/book/en/v2), [на русском](https://git-scm.com/book/ru/v2). А для того чтобы не сходить с ума с командной строкой начать использовать [SourceTree](https://www.sourcetreeapp.com).
