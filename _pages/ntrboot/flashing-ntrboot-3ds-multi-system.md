---
title: "Прошивка ntrboot (несколько 3DS)"
lang: ru
permalink: flashing-ntrboot-3ds-multi-system.html
author_profile: true
---
{% include toc title="Разделы" %}
Прежде чем продолжить, убедитесь что вы прочитали всю информацию на странице [ntrboot](ntrboot)

Обратите внимание, что флешкартридж R4i Gold 3DS RTS не сможет использоваться для своих стандартных функций (например запуск файлов `.nds`), пока эксплойт ntrboot установлен на нем. Это не относится к Acekard 2i.

В конце инструкций по установке ntrboot boot9strap есть дополнительные шаги, чтобы по окончанию удалить эксплойт ntrboot с флешкартриджа.

{% capture notice-1 %}   
Этот метод требует временный доступ ко второй консоли семейства 3DS с установленной кастомной прошивкой и b9s (если у вас a9lh, то вы не сможете запустить инсталлер, [переходите на boot9strap](a9lh-to-b9s)). Метод совместим ТОЛЬКО со следующими флешкартриджами **(даже не спрашивайте про другие; совместимы только конкретно эти типы картриджей)**:

  + [Acekard 2i](http://www.nds-card.com/ProShow.asp?ProID=160) (HW-44, HW-81), жители РФ могут купить [здесь](https://www.avito.ru/moskva/igry_pristavki_i_programmy/fleshkartridzh_fleshka_acekard_2i_dlya_nintendo_ds_544116629)
  + [R4i Gold 3DS RTS](http://www.nds-card.com/ProShow.asp?ProID=149) (A5/A6/A7), жители РФ могут купить [здесь](https://www.avito.ru/moskva/igry_pristavki_i_programmy/fleshkartridzh_r4i_gold_dlya_nintendo_ds_dsi_3ds_2ds_604415936)
  + [R4i Ultra](http://r4ultra.com)
  + [R4i Gold 3DS Starter](http://r4ids.cn)
  + [R4 3D Revolution](http://r4idsn.com)
  + [Infinity 3 R4i](http://r4infinity.com)
  + DSTT ([лишь некоторые из них!](https://gist.github.com/Hikari-chin/6b48f1bb8dd15136403c15c39fafdb42))
  
{% endcapture %}
<div class="notice--warning">{{ notice-1 | markdownify }}</div>

Обратите внимание, что в некоторых редких случаях процесс прошивки может **брикнуть** поддельный флешкартридж и навсегда сделать его нерабочим. Это маловероятно, но тем не менее поддерживаются только оригинальные флешкартриджи из списка. Чтобы уменьшить вероятность получения поддельного картриджа, рекомендуется использовать проверенный сайт для покупки флешкартриджа (например [NDS Card](http://www.nds-card.com/))
{: .notice--danger}

#### Что понадобится

* Флешкартридж, совместимый с ntrboot
* Две консоли семейства 3DS 
	+ **Исходная 3DS**: консоль семейства 3DS с boot9strap
	+ **Целевая 3DS**: консоль с официальной прошивкой
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(`ntr` boot9strap; не `devkit-файл`)*
* Свежая версия [ntrboot_flasher](https://github.com/kitling/ntrboot_flasher/releases/latest)

#### Инструкция

##### Часть I - Подготовительные работы

1. Выключите **исходную 3DS**
1. Вставьте SD-карту **исходной 3DS** в компьютер
1. Создайте папку `ntrboot` в корне SD-карты
1. Скопируйте `boot9strap_ntr.firm` и `boot9strap_ntr.firm.sha` из `.zip-архива` boot9strap в папку `/ntrboot/` в корне SD-карты
1. Скопируйте `ntrboot_flasher.firm` из `.zip-архива` ntrboot_flasher в папку `/luma/payloads/` на SD-карте **исходной 3DS**
1. Вставьте SD-карту **исходной 3DS** обратно в **исходную 3DS**
1. Вставьте ваш DS / DSi флешкартридж, совместимый с ntrboot, в **исходную 3DS**

##### Часть II - Прошивка ntrboot

1. Запустите Luma3DS chainloader, держа нажатой кнопку (START) во время загрузки на **исходной 3DS**
1. Выберите "ntrboot_flasher"
1. Прочтите предупреждение на красном экране
1. Нажмите (A), чтобы продолжить
1. Выберите ваш флешкартридж
	+ Если вашего флешкартриджа нет в списке на верхнем экране, прочтите информацию о каждой из опций на нижнем экране
1. Выберите "Dump Flash"
1. Дождитесь окончания процесса
1. Нажмите (A), чтобы продолжить
1. Нажмите (A) для возврата в главное меню
1. Выберите "Inject Ntrboot"
1. Нажмите (A) чтобы выбрать "retail unit ntrboot"
1. Дождитесь окончания процесса
1. Нажмите (A) для возврата в главное меню
1. Выберите "Exit" чтобы выключить **исходную 3DS**

___

Следующий шаг: [Установка boot9strap (ntrboot)](installing-boot9strap-ntrboot)
{: .notice--success}