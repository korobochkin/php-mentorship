# PHP Mentorship. Part 8

Планируем что поделать на восьмом занятии по PHP.

Правильно ли я сгенерировал названия бандла? https://github.com/entership/first_flight/commit/c50ad5182e7c37d252125a6881742e32ff0a1da2

— Как сгенерировать команду автоматичвески?
— Никак (досрочный ответ).

Сдается мне, что тут есть какая-то уязвимость. И судя по коду в исходниках настолько все плохо, что переводы JS-ов не предусмотрены.

```
$('#tabs_dropdown_span').html('Jump to page <select id="tabs_dropdown_select" onchange="if (this.options[this.selectedIndex].value != -1) { window.location.href = this.options[this.selectedIndex].value; }"><\/select>');
for (page = 1; page <= 2; page++) {
	var page_link = 'thumbnails.php?album=542&amp;page=%d';
	var selected = '';
	if (page == 1) {
		selected = ' selected="selected"';
	}
	$('#tabs_dropdown_select').append('<option value="' + page_link.replace( /%d/, page ) + '"' + selected + '>' + page + '<\/option>');
}
```

Другие вопросы доступны в виде TODO-блоков внутри проекта. 