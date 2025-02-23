---
permalink: /
title: 3DS Hack Guide
author_profile: true
header:	
  overlay_color: "#5e616c"
  overlay_image: images/home-page-feature.jpg
  overlay_filter: 0.5
  caption:
excerpt: 'Полное руководство по прошивке 3DS<br />**Последнее изменение:** 9 июня'
---

{% include toc title="Разделы" %}

Вдумчиво прочитайте каждую вступительную страницу инструкции (включая эту!) перед тем, как начать. Ознакомьтесь с [FAQ](faq){:target="_blank"} и пройдитесь по руководству, мысленно выполняя шаги, соответствующие вашей конфигурации. 
{: .notice--warning}

Это руководство - форк, созданный из-за несогласия в некоторых решениях в оригинальном гайде, например, об отказе от внешних ссылок на русскоязычные инструкции. Форк будет развиваться параллельно основному гайду и будет заимствовать местами формулировки и строки оттуда. Все, кто переводил тот гайд, отмечены в [соответствующем разделе](credits){:target="_blank"}.
{: .notice--success}

Руководству необходима *ваша* помощь в раздаче [этих](https://3ds.hacks.guide/rss.xml){:target="_blank"} файлов!
{: .notice--info}

Это руководство применимо _только_ для консолей, продающихся в рознице. Приставки для разработчиков невозможно прошить по этой инструкции!    
Если у вас версия для разработчиков ("PANDA"), воспользуйтесь [этой инструкцией](https://panda.hacks.guide/){:target="_blank"} (англ.)
{: .notice--danger}

Некоторые ссылки из этого руководства ведут в [группу вконтакте](http://vk.com/nincfw){:target="_blank"}. Если вы имеете затруднения с доступом к этому ресурсу, воспользуйтесь [бесплатным VPN](http://zaborona.help){:target="_blank"}
{: .notice--warning}

## Я не хочу прошивать приставку сам

+ Вы можете обратиться к специалистам. Ряд рекомендуемых мною специалистов, ранжированных по городам и странам указаны [здесь](https://docs.google.com/document/d/1vLjiqBK1dGMuVQxlep7J2EFffOd-2dDTh_id6I2KTig/edit?usp=sharing){:target="_blank"}
+ Вы можете купить уже прошитую приставку [у меня, если живете в Украине](https://3dscfw.olx.ua/){:target="_blank"}, или же у ребят из списка выше
+ Если у вас возникли трудности при прошивке, или нужна помощь в выборе приставки - обращайтесь в [официальную группу](http://vk.com/nincfw){:target="_blank"} этого руководства.

## Что такое Homebrew? 

Под словом [**Homebrew (хомбрю)**](https://ru.wikipedia.org/wiki/homebrew_(%D0%BA%D0%BE%D0%BC%D0%BF%D1%8C%D1%8E%D1%82%D0%B5%D1%80%D0%BD%D1%8B%D0%B5_%D0%B8%D0%B3%D1%80%D1%8B){:target="_blank"}) обычно подразумевают программное обеспечение не авторизованное Nintendo. В качестве примера можно привести разные самописные игры, программы для бэкапа и редактирования сохранений и эмуляторы консолей предыдущих поколений.

Во многих случаях запуск Homebrew на 100% бесплатен и использует только приложение Звук Nintendo 3DS. Существуют также и различные эксплойты в коммерческих играх и браузере, позволяющие запускать Homebrew.

## Что такое кастомная прошивка (CFW)?

**Кастомная прошивка** ("CFW", "кастом") позволяет пользоваться всеми возможностями приставки и делать вещи не доступные простым пользователям хомбрю. Например, можно устанавливать неподписанное ПО и запускать его прямо с домашнего экрана. 

Кастомную прошивку можно установить на любую приставку с версией прошивки {% include /vars/sys_version.txt %} или ниже, однако, в некоторых случаях могут понадобиться дополнительные технические средства. Подробнее об этом вы узнаете, читая руководство.

Больше информации о boot9strap [в этом документе](https://arxiv.org/abs/1802.00359).

Со списком всех вычисленных подписей sighax можно ознакомиться [здесь](https://gist.github.com/SciresM/cdd2266efb80175d37eabbe86f9d8c52).

## Что устанавливается в этом руководстве?

Конечная цель этого руководства - это установка на не взломанную 3DS кастомной прошивки с boot9strap. В некоторых случаях мы используем Homebrew как промежуточный шаг для достижения конечной цели - кастомной прошивки.

boot9strap - новейший и наилучший метод запуска кастомной прошивки. Благодаря ему можно получить практически неограниченный доступ к системе спустя несколько миллисекунд после загрузки, что похоже на эффект BootMii для Wii.

boot9strap имеет множество преимуществ перед другими методами запуска кастомных прошивок. Поэтому он рекомендован к использованию в этом руководстве вместо устаревших программ и методов запуска кастомных прошивок (например, menuhax или rxTools).

Для получения информации о том, как работает boot9strap, пожалуйста, посмотрите [эту презентацию](https://sciresm.github.io/33-and-a-half-c3/){:target="_blank"} (англ.) от [SciresM](https://github.com/SciresM/){:target="_blank"}.

Для списка каждой вычисленной sighax подписи (платформа, на которой базируется boot9strap), обратитесь к [этому gist](https://gist.github.com/SciresM/cdd2266efb80175d37eabbe86f9d8c52){:target="_blank"} (англ.).

## Что же можно делать на кастомной прошивке?

+ Играть в любые игры, доступные на картриджах или в eShop, вне зависимости от региона
+ Делать все то же самое, что вы могли бы сделать на официальной прошивке, в том числе играть онлайн
+ Настраивать внешний вид меню Home с помощью кастомных [тем](themes){:target="_blank"} и [значков](badges){:target="_blank"} и сплэш-скринов ([1](https://3dsthemesarchive.site/?type=splashes){:target="_blank"}, [2](https://themeplaza.eu/?category=splashes&query=&sort=newest){:target="_blank"})
+ Использовать патчи на легально купленных играх, например, любительские переводы и модификации. 
+ Делать скриншоты игр и приложений
+ Делать резервные копии, редактировать и восстанавливать сохранения для игр 3DS и DS
+ Играть в игры от приставок предыдущих поколений с помощью эмуляторов (на New 3DS производительность выше)
+ Устанавливать Homebrew-приложения и делать их доступными прямо из меню Home
+ Сохранять игры с картриджей в формате, который впоследствии можно [установить прямо в систему и играть](godmode9-usage#%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BC%D0%BF%D0%B0-%D0%BA%D0%B0%D1%80%D1%82%D1%80%D0%B8%D0%B4%D0%B6%D0%B0){:target="_blank"} не используя картридж. 
+ Только New 3DS и New 2DS: [транслировать геймплей](https://vk.com/3ds_cfw?w=wall-125012133_111%2Fall){:target="_blank"} на компьютер по беспроводной сети с помощью NTR CFW
+ Использовать старые флешкатриджи для Nintendo DS, которые были давно заблокированы или не работали на Nintendo 3DS
+ Безопасно обновляться до актуальных версий прошивок без боязни потерять доступ к Homebrew
+ [Конвертировать 3DS-ромы в CIA](godmode9-usage#convert_3ds){:target="_blank"}
+ Использовать [читы](cheats) в играх

## Что нужно знать перед тем, как начать?

+ **Перед тем, как начинать прошивку, следует понимать риск взлома 3DS: КАЖДЫЙ раз, модифицируя прошивку консоли, вы рискуете получить НЕВОССТАНОВИМЫЙ брик. Вероятность этого крайне низкая, но шанс всё равно есть. Так что убедитесь, что вы СТРОГО следуете всем указаниям.**
+ New 2DS XL, New 3DS и New 3DS XL - одно и то же. Разный формфактор, но суть одна. Одни и те же инструкции по прошивке. В гайде они обобщены под названием New3DS
+ 2DS, 3DS и 3DS XL - одно и то же. Разный формфактор, но суть одна. Одни и те же инструкции по прошивке. В гайде они обобщены под названием Old3DS
+ Для простоты всё вышеназванное называем просто 3DS 
+ Если ранее вы уже взламывали свою 3DS для получения EmuNAND и хотите перенести его содержимое в SysNAND с кастомной прошивкой, просто следуйте руководству, пока не дойдете до пункта о восстановлении EmuNAND в разделе [Завершение установки](finalizing-setup){:target="_blank"}.
+ Инструкция предназначена для всех приставок семейства 3DS любых регионов на прошивке {% include /vars/sys_version.txt %} или ниже
+ Если всё пройдет по плану, вы ничего не потеряете и всё останется в первоначальном состоянии (игры, сохранения, NNID).
+ Держите консоль подключенной к зарядному устройству на протяжении всего процесса, чтобы избежать потери данных или поломки, в случае внезапного отключения консоли
+ SD-карта должна использовать [MBR, а не GPT](https://allerror.ru/zhelezo/v-chyom-raznica-mezhdu-gpt-i-mbr-pri-sozdanii-razdelov-na-diske.html){:target="_blank"} (SD-карта, входящая в комплект, уже использует MBR).
+ Если вам нужно отформатировать новую SD-карту, отформатируйте её согласно [инструкции](http://customfw.xyz/format_sd){:target="_blank"}

___

<center><a href="get-started" style="margin:20px auto; text-align:center; display:block; width:200px;" class="btn btn--short">Начнем!!</a></center>
{: .notice--success}
