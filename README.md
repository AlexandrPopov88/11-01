# Домашнее задание к занятию "`Базы данных, их типы`" - `Попов Александр`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

### Ответ
Для этого подойдут реляционные СУБД, такие как PostgreSQL или Oracle Database, которые обеспечивают высокую степень целостности данных, четкую структуру и поддержку сложных транзакций. 

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы? 

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

### Ответ

Для лендингов, где данные должны быть быстро обрабатываться и представлены пользователю, лучше использовать реляционные базы данных, такие как MySQL или PostgreSQL. 
Они хорошо масштабируются и обладают хорошей производительностью для чтения и записи данных.

Для CRM, где данные должны быть структурированны и обработаны с целью аналитики и поддержки принятия решений, лучше использовать CRM-систему, которая уже имеет встроенную базу данных.
Например, Salesforce, HubSpot или Bitrix24 предоставляют гибкие и быстрые инструменты для управления данными о лидарах и клиентах.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это 
реализовать?

### Ответ
В этом случае документо-ориентированная СУБД подойдет для хранения и поиска документов с разной структурой.

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.

### Ответ
Для департамента логистики, который решает задачи по быстрому формированию маршрутов доставки материалов и распределению курьеров, важна возможность быстро обрабатывать и оптимизировать связи между различными объектами.
В этом случае можно рассмотреть использование графовой базы данных, которая специально предназначена для работы со связанными данными.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД 
логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

*Приведите ответ в свободной форме.*

---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

### Ответ

1. Инициация транзакции:
Пользователь выбирает способ пополнения баланса (например, через мобильное приложение, терминал, сайт оператора или банкомат).
Вводит номер телефона и сумму пополнения.
2. Проверка данных:
Система проверяет введённый номер телефона на корректность (валидность номера, принадлежность оператору связи).
Проверяется доступность и правильность введённой суммы (например, сумма должна быть в допустимых пределах для пополнения).
3. Аутентификация и авторизация:
Если требуется, пользователь проходит процесс аутентификации (например, вводит PIN-код, подтверждает действие через мобильное приложение банка).
Производится проверка доступности средств на счёте пользователя, если используется банковская карта или другой способ оплаты.
4. Отправка запроса на пополнение:
После успешной авторизации, система отправляет запрос на проведение платежа в платёжный шлюз или банк.
Платёжный шлюз или банк проверяет возможность списания средств и, при положительном исходе, инициирует транзакцию.
5. Обработка транзакции оператором:
Оператор мобильной связи получает запрос на пополнение баланса и резервирует соответствующую сумму.
Если транзакция успешно обработана, оператор обновляет баланс пользователя на сервере.
6. Подтверждение и завершение:
Пользователь получает уведомление о результате пополнения (успешная транзакция или ошибка).
При успешной транзакции на счёт телефона поступает пополненная сумма, и пользователь видит обновлённый баланс.
В случае ошибки пользователь получает соответствующее уведомление с описанием проблемы (например, недостаточно средств, неверный номер телефона).
Этот процесс завершает транзакцию по пополнению баланса телефона и гарантирует корректное выполнение операции.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

*Приведите ответ в свободной форме.*

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

*Приведите ответ в свободной форме.*

### Ответ

1. Строгая структура данных:
2. Транзакционная целостность (ACID-свойства):
3. Широкая поддержка и зрелость технологий:
4. Мощные возможности для анализа данных:
5. Стандартизация и совместимость:

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

*Приведите ответ в свободной форме.*

### Ответ
Для задачи связанной с большими объёмами данных и необходимостью в распределённых вычислениях, наиболее подходящим выбором будет NoSQL-система (например, Cassandra) в сочетании с Apache Spark для управления распределёнными вычислениями.
Эта комбинация обеспечит высокую масштабируемость, производительность и гибкость, необходимые для эффективной работы на 1000 машинах.


---

Задания,помеченные звёздочкой, — дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже разобраться в материале.
