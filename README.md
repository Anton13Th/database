# Домашнее задание к занятию "Базы данных, их типы" - `Нагорнов Антон Алексеевич`
Задание 1. СУБД
Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.
Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.
Ответ: 
Реляционная СУБД т.к. необходимо построить систему, в рамках которой требуется хранить значительное количество сущностей (таблиц), с различными типами связей между ними.

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.
Ответ:
Для решения данной задачи подойдет также реляционная СУБД, она отвечает всем необходимым требованиям.
           
1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.
Ответ: 
СУБД ключ-значение т.к. такая СУБД хорошо подходит для баз где нужно хранить достаточно простые структуры, и иметь к ним очень быстрый доступ.

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.
Ответ: 
Можно использовать графовые СУБД - специфичный тип СУБД, предназначенный для работы с графами, с их узлами, свойствами, и произвольными отношениями между узлами.

Задание 2. Транзакции
2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.
- Ввести данные - номер телефона, сумму пополнения;
- Аутентификация пользователя в банке;
- Проверка достаточности средств на счету;
- Блокировка необходимой суммы для оплаты;
- Списание указанной суммы;
- Зачисление суммы на указанный счет;
2.1. * Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?
Все тоже самое, за исключением условия ручного ввода данных т.е. наступление условия для автоматического обращения в систему, например, по дате или окончании средств на счете.

Задание 3. SQL vs NoSQL
3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.
Ответ:
- SQL-база данных имеет строгую схему данных, которая определяет типы данных и связи между таблицами.
- Данные в таблицах структурированы по строгим правилам и могут быть связаны с помощью внешних ключей. Эта структура данных делает SQL-базы данных хорошо подходящими для хранения и обработки структурированных данных.
- SQL-базы данных имеют более развитое индексирование, чем NoSQL-базы, что обеспечивает более высокую производительность при выполнении сложных запросов.
- В SQL можно легко установить ограничения на доступ к данным для разных пользователей, а также применять различные аутентификационные механизмы для обеспечения безопасности данных. При этом SQL-базы данных имеют лучшую поддержку транзакционности, что позволяет автоматически откатывать изменения при обнаружении проблемных транзакций и, таким образом, нивелировать возможные проблемы безопасности.
- Кэширование в SQL-базах данных позволяет улучшить производительность и более точно отслеживать изменения, что может помочь в оптимизации обработки запросов.

3.1. * Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.
Ответ:
- совершенно новый движок, не унаследованный от классических СУБД;
- поддержка реляционной модели и транзакционности;
- горизонтальная масштабируемость.

Задание 4. Кластеры
Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.
На основе какого критерия будете выбирать тип СУБД, и какая модель распределённых вычислений здесь справится лучше всего и почему?
Ответ:
Исходя из условий основным критерием создания кластера является именно производительность, но также необходимо не забывать про масштабируемость и надежность. Так же, из-за большого количества машин необходимо учитывать балансировку нагрузки. СУБД с клиент-серверной многоуровневой архитектурой подойдет для данной задачи лучше всего. В этом типе архитектуры пул задач обработки данных распределен по отдельным серверам. Такая технология разделяет задачи обработки данных для более выгодного использования вычислительной мощности серверов и, как следствие, повышения эффективности всей IT-системы. Сервера обрабатывают запросы от клиентов, которые затем передаются между различными слоями клиентской стороны. Логика приложения разделена на несколько компонентов, которые могут быть развернуты на разных устройствах или даже в разных физических местах. Клиенты обмениваются данными и запросами между собой и серверами, дабы выполнять нужные операции.
