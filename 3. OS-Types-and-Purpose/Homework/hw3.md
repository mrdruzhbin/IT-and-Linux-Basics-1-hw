# Домашнее задание к занятию "Типы и назначение операционных систем. ОС Linux" - Дружбин Александр

### Задание 1. 

### Кейс: 
Компания ООО "Рога и Копыта" решила автоматизировать свою работу и централизировать управление учетными записями.
Руководством было принято решение развернуть пять новых серверов:

* систему контроля доступа пользователей и управления учетными записями;
* терминальный сервер;
* два сервера для веб-приложений и прокси сервер.

#### Какие ОС вы выберете для каких серверов? Почему?

### Решение
Выберу серверную ОС (например, любой из популярных дистрибутивов Linux). Погуглил, в случае с системой контроля доступа пользователей и управления учетными записями речь идёт об IdM/IAM, гугл выдал статью от RHEL, так что взял бы, допустим, этот дистрибутив. Раз он такой бизнес-ориентированный, взял бы его и для терминального сервера, и для веба с прокси. Пробежался по доп. статье по дистрибутивам - подводных камней не вижу. 

Есть ощущение, что я неправильно понял вопрос и речь не о дистрибутивах, а о самих ОС. В таком случае ответ Linux т.к. требуется не user-friendly интерфейс как на Windows, а производительность и надёжность.

---

### Задание 2. 

#### На каких уровнях системы работают следующие службы или приложения?

* оконный менеджер;
* файловый менеджер;
* веб-браузер;
* текстовый редактор;
* калькулятор.

### Решение
* User Applications: веб-браузер, текстовый редактор, калькулятор.
* OS Services: оконный менеджер, файловый менеджер.
---

### Задание 3. 

#### Назовите по два DEB и RPM дистрибутива.

### Решение
* DEB-дистрибутивы: Debian, Ubuntu
* RPM-дистрибутивы: RHEL, CentOS
