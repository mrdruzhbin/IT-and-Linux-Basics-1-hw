# Домашнее задание к занятию "Обзор IT-систем: принципы работы современных компьютеров" - Дружбин Александр

### Кейс 1.

Как вы думаете, какие принципиальные отличия есть между:

* компьютером секретаря

* рабочей станцией для работы с 3d графикой

* файловым сервером

* сервером, выполняющим роль маршрутизатора для выхода в интернет

### Решение

Эти устройства заточены на разную работу с информацией. 

* компьютер секретаря нужен для создания информации (документы, заметки, созвоны и т.д.), соответственно главное тут - простота использования и всякие мелкие офисные программы, не особо требовательные по железу

* рабочая станцией для работы с 3d графикой нужна для обработки информации и подразумевает более высокую производительность т.к. программы потяжелее и более требовательные

* файловый сервер нужен для хранения информации, следовательно нужен большой объем памяти и желательно отказоустойчивость (бекап, например)

* сервер, выполняющий роль маршрутизатора для выхода в интернет, нужен для передачи информации и подразумевает высокую пропускную способность 

---

### Кейс 2.

Чем отличаются чипсет и процессор? Напишите ответ в свободной форме.

### Решение

Процессор - центральный компонент, производит вычисления, исполняет код программ, управляет другими устройствами и т.д. А чипсет нужен для его обслуживания, т.е. чипсет контролирует обмен данных между процессором и RAM (и другими устройствами). Если совсем в свободной форме, то  процессор - сердце, а чипсет - это что-то вроде крови, которая циркулирует по организму, связывает всё со всем.

---

### Кейс 3.

#### Какой вариант хранилища вы бы выбрали для задач ниже (3.1-3.5)?


#### Вариант хранилища:

**А)** SSD [1], **B)** HDD [2], **C)** Ленточная библиотека [3], **D)** Собственный вариант.

#### Задачи:

* 3.1 Хранилище архива проектов, расположенное на диске с общим доступом, не критично к скорости чтения, большого объёма, должно быть доступно круглосуточно

* 3.2 Сервер баз 1С с высокими требованиями по скорости доступа к диску

* 3.3 Системный диск (на котором установлена операционная система) рабочей станции, объём небольшой

* 3.4 Хранилище ежемесячных резервных копий большого объёма, носители которого должны храниться вне офиса на случай пожара и других непредвиденных ситуаций. Подлежат использованию к крайнем случае

* 3.5 Второй диск на рабочей станции, на котором пользователь хранит данные второстепенной важности

### Решение

* 3.1 [2]
* 3.2 [1]
* 3.3 [1]
* 3.4 [3]
* 3.5 [2]

---

### Кейс 4.

Существует ли возможность использовать жёсткий диск [Western Digital WD40PURZ](https://market.yandex.ru/product--zhestkii-disk-western-digital-wd40purz/1729220435) в комплекте со старой материнской платой, в которой зашит классический BIOS?
Если да, то в каком случае. Если нет, то почему? Есть ли какой-то обходной вариант? Напишите ответ в свободной форме.

### Решение

Основываясь на [сравнении](http://screenshot.alarislabs.com/ADr/image_20231018225417_60f80c74.png) из лекции, предположу, что для того, чтобы материнская плата поддерживала диски более 2,2 тб, нужно, чтобы вместо BIOS был UEFI (и чтобы sata контролер на материнской плате поддерживал диски более 2,2 тб). Гугл подсказал, что ограничение по размеру распространяется не на размер диска, а на максимальный размер раздела на нём в таблице разделов MSDOS. То есть в теории можно купить этот диск и порезать его на разделы поменьше.

---

### Кейс 5.

Опишите процесс загрузки компьютера с момента нажатия кнопки включения и до появления рабочего стола.
Опишите этот процесс настолько детально, насколько вы это понимаете.

### Решение

До прочтения статьи из материалов для дальнейшего изучения ответил бы, что компьютер загружается благодаря живущим в нем маленьким гномикам или что-то в этом роде. Прочитал статью, сильно понятнее не стало, просто гномики получили имена:

1. Я нажимаю на кнопку включения

2. Поступает питание, блок питания включается и подается сигнал Reset, при этом начинается тестирование блока питания, соответствует ли он требованиям по напряжению. Следующий за этим сигнал Power Good означает, что блок питания проверку прошел, а значит сигнал Reset можно снять и идти дальше

3. В работу включается BIOS, его код находится на ПЗУ, которое было опознано еще на втором пункте вместе с другими подключенными устройствами. Работа с ПЗУ очень медленная, поэтому BIOS инициализирует оперативную память и копирует в нее собственный код из ПЗУ

4. Следом за этим идёт этап проверок различных компонентов, включая процессор, оперативную память, видеокарту и т.д., эти проверки называются Power On Self-Test (POST), а их количество зависит от типа POST (сокращенный/полный). Во время этих проверок компьютер может пищать и мигать светодиодами, оповещая о том, что та или иная проверка успешна или неуспешна

5. В зависимости от Boot Priority BIOS ищет загрузочную область (откуда загружать ОС), следом за этим включается загрузчик ОС, который поэтапно собирает информацию о системе и запускает ОС

6. Ядро ОС запускает первый процесс, порождающий все остальные, после чего первый процесс переходит в режим ожидания
 
---

### Кейс 6.

Попробуйте узнать IP-адрес вашего компьютера из [консоли (командной строки)](https://webkyrs.info/post/chto-takoe-komandnaia-stroka-kak-ee-zapustit-na-windows-linux-i-mac) с помощью команды `ipconfig` или `ifconfig` в зависимости от ОС, либо через графический интерфейс.
Совпадает ли он с [адресом, который видит, например, Яндекс](https://internet.yandex.ru)? Как вы думаете, почему?

### Решение

[Узнал](http://screenshot.alarislabs.com/ADr/image_20231018221346_468a1ce9.png), команда ipconfig выдаёт IP 10.146.17.217 (назначенный IP от OpenVPN) и IP 192.168.0.102 (это мой внутренний IP). А Яндекс показывает мой внешний IP, который с предыдущими двумя не совпадает.

---

### Кейс 7.

Какой процессор вы выберете - Intel Core i5 9600K или Intel Core i7 7700K?
Почему Intel Core i5 9600K или Intel Core i7 7700K? [Изменится ли мнение после просмотра этого сравнения?](https://cpu.userbenchmark.com/Compare/Intel-Core-i5-9600K-vs-Intel-Core-i7-7700K/4031vs3647) Опишите ход ваших мыслей.
Какую материнскую плату вы выберете для выбранного процессора?

### Решение

Выберу Intel Core i5 9600K. Ход мыслей простой: загуглил "Intel Core i5 9600K или Intel Core i7 7700K?" и сразу наткнулся на сайты с бенчмарками, восхваляющими Intel Core i5 9600K. Потом перешёл по твоей ссылке и убедился в том, что она лучше. Твой подвох бы сработал, если бы мне пришлось выбирать уже в магазине за пару секунд без гуглежа, тогда выбрал бы ту, у которой циферка больше и видимо пожалел бы потом

Относительно материнской платы загуглил "best motherboard for Intel Core i5 9600K" и мимоходом выяснил что "the most suitable motherboard chipset is Z390". Думаю, в реальной ситуации потратил бы много времени на выбор, проверяя, какие из этих материнских плат есть в местных магазинах и посмотрел бы доп. разборы на ютубе. А так рискну и выберу Gigabyte Z390 UD, по крайней мере в её совместимости сомневаться не приходится.
