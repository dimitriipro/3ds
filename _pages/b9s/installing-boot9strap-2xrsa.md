---
title: "Установка boot9strap (2xrsa)" #
lang: ru
permalink: installing-boot9strap-2xrsa.html
author_profile: true
---
{% include toc title="Разделы" %}

## Что понадобится

* Свежая версия [SafeB9SInstaller](https://github.com/d0k3/SafeB9SInstaller/releases/latest)
* Свежая версия [boot9strap](https://github.com/SciresM/boot9strap/releases/latest) *(стандартный boot9strap; не `devkit-файл`, не `ntr-файл` и не `devkit-ntr-файл`)*
* Свежая версия [Luma3DS](https://github.com/AuroraWright/Luma3DS/releases/latest) *(`.7z`-архив)*
* Свежая версия [OCS](https://github.com/Pirater12/ocs/releases/latest)

## Инструкция

#### Часть I - Подготовительные работы

1. Выключите консоль
1. Вставьте SD-карту в компьютер
1. Скопируйте файл `boot.firm` из `.7z-архива` Luma3DS в корень SD-карты
1. Скопируйте `boot.3dsx` (OCS) в корень SD-карты
1. Создайте папку `boot9strap` в корне SD-карты
1. Скопируйте `boot9strap.firm` и `boot9strap.firm.sha` из `.zip-архива` с boot9strap в папку `/boot9strap/` в корне SD-карты
1. Скопируйте `arm9.bin` и `arm11.bin` из `.zip-архива` SafeB9SInstaller в корень SD-карты

    ![]({{ "/images/screenshots/boot9strap-2xrsa-file-layout.png" | absolute_url }})
    {: .notice--info}

1. Вставьте SD-карту обратно в консоль
1. Включите консоль

#### Часть II - Запуск SafeB9SInstaller

1. Запустите браузер на консоли и перейдите по ссылке:
  + `http://2xrsa.3ds.guide`
  + Если вы забыли включить Wi-Fi на New 3DS, New 2DS или Old 2DS, это можно сделать, вытащив батарею и отключив зарядное устройство на несколько секунд, а затем снова включить консоль
  + Если появляется ошибка "This service is not available in your region", поменяйте регион в Системных настройках (System Settings) на соответствующий тому, который был установлен при 2.1.0 CTRTransfer
  + Если вы забыли отключить Родительский контроль до начала процесса CTRTransfer или не можете получить доступ к настройкам сети, консоль подключится автоматически к беспроводной сети с именем `attwifi` без пароля
  + При возникновении другой ошибки, обратитесь к разделу [проблемы и их решения](troubleshooting#не-работает-эксплойт-на-основе-браузера)
1. Если эксплойт сработал, запустится SafeB9SInstaller

#### Часть III - Установка boot9strap

1. Дождитесь окончания всех проверок безопасности
1. При появлении запроса, введите указанную комбинацию кнопок для установки boot9strap
1. После завершения процесса, нажмите (A) для перезагрузки

#### Часть IV - Настройка Luma3DS

1. Устройство загрузится в меню настройки Luma3DS
  + Если после включения экран остаётся чёрным, то перейдите к разделу [проблемы и их решения](troubleshooting#черный-экран-при-загрузке-sysnand-после-установки-b9s)
1. Нажимая (A) выберите следующие пункты:    
  + **"Enable game patching"**
  + **"Show NAND or user string in System Settings"**
1. Если у вас **New 3DS**, вы *также* можете включить следующие опции:
  + **"New 3DS CPU" выбрать значение "Clock+L2(x)"**
    + Это увеличит частоту кадров в множестве игр, но может отразиться на стабильности других
    + Если какие-либо игры работают некорректно, отключите эту опцию
	
    ![]({{ "/images/screenshots/luma-settings.png" | absolute_url }})
	{: .text-center}
    {: .notice--info}
	
1. Нажмите (START), чтобы сохранить настройки и перезагрузиться
  + Если появляется ошибка, просто переходите к следующей странице

___

Помните, что пользователи *New 3DS*, делавшие CTRTransfer прошивки 2.1.0 *должны* [восстановить резервную копию NAND](godmode9-usage#nand_restore) перед выполнением раздела [завершение настройки](finalizing-setup).
{: .notice--danger}

Следующий шаг: [Завершение установки](finalizing-setup)
{: .notice--success}

