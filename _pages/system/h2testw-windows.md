---
title: H2testw (Windows)
permalink: /h2testw-windows.html
author_profile: true
---
{% include toc title="Разделы" %}

Этот дополнительный раздел содержит информацию о проверке SD-карты на ошибки с помощью F3.

В зависимости от размера SD-карты и скорости компьютера этот процесс может занять до нескольких часов!

Этот раздел предназначен для пользователей Windows. Если у вас не Windows, воспользуйтесь F3 [linux](f3-linux) или [F3X (mac)](f3x-mac){:target="_blank"}.

## Что понадобится

* Свежая версия [h2testw](http://www.heise.de/ct/Redaktion/bo/downloads/h2testw_1.4.zip){:target="_blank"}

## Инструкция

1. Скопируйте `h2testw.exe` из `.zip-архива` с h2testw на рабочий стол
1. Вставьте SD-карту в компьютер
1. Запустите `h2testw.exe`
1. Выберите "**English**"
1. Нажмите "**Select target**"
1. Выберите букву, соответствующую букве SD-карты
1. Убедитесь, что выбран пункт "all available space"
1. Нажмите "**Write + Verify**"
1. Дождитесь окончания проверки

___

Если в результате тестирования вы видите `Test finished without errors`, ваша SD-карта в порядке. Можете удалить все файлы с расширением `.h2w` с SD-карты
{: .notice--success}

При любом другом результате SD-карта скорее всего повреждена и её стоит заменить!
{: .notice--danger}

___

## Вернуться к [Началу](get-started)
{: .notice--success}