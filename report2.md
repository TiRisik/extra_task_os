---
## Front matter
title: "Второй раздел курса Введение в Linux"
subtitle: "Дополнительное задание"
author: "Тарутина Кристина Олеговна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Изучить материалы курса, пройти тестовые и интерактивные задания


# Выполнение лабораторной работы

Приступаю к выполнению задания 1. Выбираю все четыре варианта, так как на сервере можно хранить конфеденциальные и общедоступные данные, большие объёмы данных, а также выполнять сложные вычисления(рис. @fig:001).

![Знакомство с сервером: Задание 1](image/image1.png){#fig:001 width=70%}

Приступаю к выполнению задания 2. В видеоматериалах говорится, что спокойно можно пересылать публичный ключ, так как помимо него есть ещё второй ключ, который как раз таки пересылать не стоит. Публичный ключ хранится в id_rsa.pub(рис. @fig:002)

![Знакомство с сервером: Задание 2](image/image2.png){#fig:002 width=70%}

Приступаю к выполнению задания 3. Запускаю терминал. Захожу на сервер
ssh box@server1.stepik-local(рис. @fig:003)
Ввожу указанный в задании пароль. С помощью ниже указанных команд перехожу в нужную директорию
pwd
cd ../
cd srv
cd files_in_server
Дальше вывожу в консоль содержимое файла и выхоу из сервера
cat secret
exit
и наконец указанный в файле текст записываю в другой файл уже на компьютере
echo "I hacked ssh!" > /home/box/secret

![Знакомство с сервером: Задание 3](image/image3.png){#fig:003 width=70%}

Приступаю к выполнению задания 4. Сразу отметаю варианты, которые начинаются с ssh, потому что нам нужна команда scp. Дальше замечаю что вариант stepik/* скопирует только файлы в папке, но не саму её, а значит правильным ответом является последний вариант(рис. @fig:004)

![Обмен файлами: Задание 4](image/image4.png){#fig:004 width=70%}

Приступаю к выполнению задания 5. Сразу отметаю варианты с командами sudo ... upgrade и sudo ... -only-upgrade, так как эти команды обновляют не ссылки, а уже установленные пакеты, что в данном случае бесполезно. Так же нам не подходит ответ с местом на диске, следовательно выбирает интернет соединение. Логично при проблемах с загрузкой первым делом проверить именно его.(рис. @fig:005)

![Обмен файлами: Задание 5](image/image5.png){#fig:005 width=70%}

Приступаю к выполнению задания 6. В видеоматериалах к заданию мы рассматривали функционал данного приложения, так что основываясь на них понимаем, что из предложенного только установка приложений на сервер не является его функционалом(рис. @fig:006)

![Обмен файлами: Задание 6](image/image6.png){#fig:006 width=70%}

Приступаю к выполнению задания 7. К сожалению его не удалось записать на скринкаст ввиду технический проблем(записался только чёрный экран). Сперва я создаю нужную мне директорию на компьютере
mkdir /home/box/files_on_client
Далее с помощью команды scp я копирую файлы с сервера на клиент
scp -r box@server1.stepik-local:/srv/files _on_server/* ~/files_on_client
Во время исполнения данной команды терминал запрашивает у меня пароль. Ввожу его и происходит процесс копирования(рис. @fig:007) 

![Обмен файлами: Задание 7](image/image7.png){#fig:007 width=70%}

Приступаю к выполнению задания 8. Сразу убираю из возможный вариант запустить программу на компьютере, так как в задании сказано, что требуется запустить именно на сервере. Вариант где ничего нельзя сделать также нам не подходит, так как мы можем проверить если версия программы для терминала и настроить сервер на вывод информации на экран компьютера(рис. @fig:008).

![Запуск приложений: Задание 8](image/image8.png){#fig:008 width=70%}

Приступаю к выполнению задания 9. Сразу отметаю вариант с !?, так как нет подобной команды для вывода информации. Все остальные же варианты подходят, способ выведения информации о программе зависит от самой программы(рис. @fig:009)

![Запуск приложений: Задание 9](image/image9.png){#fig:009 width=70%}

Приступаю к выполнению задания 10. Открываю справку по данной программе, где в строке -f format находится как раз нужный мне ответ(рис. @fig:010 - @fig:011).

![Запуск приложений: Задание 10](image/image10_1.png){#fig:010 width=70%}

![Запуск приложений: Задание 10](image/image10_2.png){#fig:011 width=70%}

Приступаю к выполнению задания 11. Открываю справку по заданной программе. Там сразу же ищу опцию для сножественного выравнивания(-align).  Записываю строку в порядке команда файл опции(рис. @fig:012 - @fig:013).

![Запуск приложений: Задание 11](image/image11_1.png){#fig:012 width=70%}

![Запуск приложений: Задание 11](image/image11_2.png){#fig:013 width=70%}

Приступаю к выполнению задания 12. Так как мы прервали выполнение первой программы, то информация о ней не будет выведена, приостановка программы два и работа программы три в фоновом режиме никак не влияет на команду, так что информация о них будет выведена(рис. @fig:014)

![Контроль запускаемых программ: Задание 12](image/image12.png){#fig:014 width=70%}

Приступаю к выполнению задания 13. Одинаковые идентификаторы только у ps и top, так как они используют уникальные идентификаторы программ, jobs же присваивает свои, пронумеровав по порядку запуска программ(рис. @fig:015)

![Контроль запускаемых программ: Задание 13](image/image13.png){#fig:015 width=70%}

Приступаю к выполнению задания 14. Мгновенно завершить процесс можно с помощью программы kill -9, однако этого не рекумендуется делать, так как программа kill делает это более плавно, посылая самой программе запрос на выключение(рис. @fig:016)

![Контроль запускаемых программ: Задание 14](image/image14.png){#fig:016 width=70%}

Приступаю к выполнению задания 15. Процесс приступет к завершению, как только будет продолжен, потому что без опций данная команда посылает лишь запрос на выключение и сама программа делает это во время своей работы, а значит она не закончится, пока приостановлена(рис. @fig:017)

![Контроль запускаемых программ: Задание 15](image/image15.png){#fig:017 width=70%}

Приступаю к выполнению задания 16. Программа не использцет вычислительных ресурсов центрального процессора, так как она остановлена и ничего не делает в данный момент(рис. @fig:018)

![Многопоточные приложения: Задание 16](image/image16.png){#fig:018 width=70%}

Приступаю к выполнению задания 17. Программа занимает столько же памяти, сколько и во время остановки, так как всё ещё хранит данные и не совершает никаких действий по их удалению(рис. @fig:019)

![Многопоточные приложения: Задание 17](image/image17.png){#fig:019 width=70%}

Приступаю к выполнению задания 18. Воспользовавшись подсказкой к заданию проверяю данный вопрос на практике, опытным путём устанавливая, что сделать этого нельзя никак(рис. @fig:020)

![Многопоточные приложения: Задание 18](image/image18.png){#fig:020 width=70%}

Приступаю к выполнению задания 19. По справкам проверяю что в несколько потоков можно запустить как bowtie2, так и bowtie2-build, однако система не принимает этот ответ. В комментариях пишут, что возможно это из-за устаревших заданий, также склоняюсь к этому варианту(рис. @fig:021)

![Многопоточные приложения: Задание 19](image/image19.png){#fig:021 width=70%}

Приступаю к выполнению задания 20. С помощью команды wget скачиваю необходимые для работы файлы, запускаю программу и перенаправлю вывод  ошибки в нужный мне файл с помощью 2>. Текст файла копирую и вставляю в графу ответа(рис. @fig:022)

![Многопоточные приложения: Задание 20](image/image20.png){#fig:022 width=70%}

Приступаю к выполнению задания 21. Когда мы используем две разные вкладки терминала, то процессы проходящие в них не связаны, а следовательно правильным ответом будет последний(рис. @fig:023)

![Менеджер терминалов tmux: Задание 21](image/image21.png){#fig:023 width=70%}

Приступаю к выполнению задания 22. В случае если мы ввёдём команду exit, то tmux завершит работу(рис. @fig:024)

![Менеджер терминалов tmux: Задание 22](image/image22.png){#fig:024 width=70%}

Приступаю к выполнению задания 23. Одним из существенных преимуществ tmux, из-за которого им пользуются, является именно то, что даже если соединение с сервером прервётся, он всё равно продолжит работу(рис. @fig:025)

![Менеджер терминалов tmux: Задание 23](image/image23.png){#fig:025 width=70%}

Приступаю к выполнению задания 24. Если принудительно закрыть tmux с запущенным в фоновом режиме процессом, то процесс прервётся(хотя в современных версиях он сначала выдаёт предупреждение, новкладку всё равно можно закрыть) (рис. @fig:026)

![Менеджер терминалов tmux: Задание 24](image/image24.png){#fig:026 width=70%}

Приступаю к выполнению задания 25. Изучаю справку по tmux и выбираю необходимое мне сочетание клавиш(рис. @fig:027)

![Менеджер терминалов tmux: Задание 25](image/image25.png){#fig:027 width=70%}

Приступаю к выполнению задания 26.Первое утверждение не верно, разелять можно сколько угодно раз. Второе, третье и четвёртое верны. Пятое не верно, команды разделения действуют в текущей вкладке. Последнее утверждение также верно.(рис. @fig:028 - @fig:029)

![Менеджер терминалов tmux: Задание 26](image/image26_1.png){#fig:028 width=70%}

![Менеджер терминалов tmux: Задание 26](image/image26_2.png){#fig:029 width=70%}


# Выводы

Курс я прошла успешно, выполнила все задания и получила полный бал, а также составила конспекты по разделу
# Список литературы{.unnumbered}

::: {#refs}
:::
