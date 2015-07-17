# PHP Mentorship. Part 3

Планируем что поделать на третьем занятии по PHP.

Поскольку в прошлый раз мы лишь познакомились со фреймворком, то будем продолжать с ним знакомиться. Возможно, переключимся на другой фреймворк (Symfony) для сравнения и просто чтобы посмотреть на тоже самое другими глазами (развиваем кругозор). Будем пробывать построить простенькую формочку, с помощью которой можно оставлять свой адрес эл. почты (см. `plans-2.md`).

Также мы не поговорили про удаление классов, если так вообще можно вызариться.

## Аудит

Пара моих простейших плагинов — [bbPress Permalinks with ID](https://github.com/korobochkin/bbpress-permalinks-with-id/blob/master/plugin/plugin.php) и [Mark User as Spammer](https://github.com/korobochkin/mark-user-as-spammer/blob/master/plugin/plugin.php). Качество кода, стилистика, может быть есть грубые ошибки или что-то в этом роде?

Начал делать [плагин-адаптацию сервиса Recaptcha](https://github.com/korobochkin/reCAPTCHA-Lightweight-Adaptation/tree/master/plugin) от Google. Сейчас собрал первую рабочую версию. Уже хочется попробывать переписать с `namespaces`. Что еще следует переписать и улучшить?

### Автозагрузка

Встретил `spl_autoload_register()` — работает на магии. Пример ниже подгружает файлы, как я понял, все, которые есть в папке и называются также как и имена классов, описываемых в этих классах. [Полный исходник](https://github.com/jbrinley/wp-forms/blob/master/classes/WP_Form_Plugin.php#L45).

```
public static function init( $plugin_file ) {
	self::$plugin_file = $plugin_file;
	spl_autoload_register(array(__CLASS__, 'autoloader'));
	add_action( 'init', array( 'WP_Form_Registrar', 'init' ), 11, 0 );
	add_action( 'plugins_loaded', array( 'WP_Form_Listener', 'init' ), 10, 0 );
}
public static function autoloader( $class ) {
	if ( strpos( $class, 'WP_Form' ) !== 0 ) {
		return;
	}
	$dir = self::plugin_path('classes');

  if ( strpos( $class, 'WP_Form_Element' ) === 0 ) {
		$dir .= '/elements';
	} elseif ( strpos( $class, 'WP_Form_View' ) === 0 ) {
		$dir .= '/views';
	} elseif ( strpos( $class, 'WP_Form_Decorator' ) === 0 ) {
		$dir .= '/views/decorators';
	}

	if ( file_exists("$dir/$class.php") ) {
		include_once("$dir/$class.php");
		return;
	}
}
```
