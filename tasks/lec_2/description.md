## Описание таблиц

### fw_contracts
| Столбец | Описание |
| --- | --- |
|ID_CONTRACT_INST|Идентификатор контракта|
|DT_STOP|Дата конца действия записи|
|DT_START|Дата начала действия записи|
|ID_REC|Идентификатор записи|
|ID_CLIENT_INST|Идентификатор клиента|
|ID_CURRENCY|Валюта контракта|
|V_STATUS|Статус А активен,B заблокирован,С расторжен,D удален|
|DT_REG_EVENT|Дата регистрации|
|V_DESCRIPTION|Описание контракта|
|ID_DEPARTMENT|Код департамента из миграционной таблицы MIGR_DEPARTMENTS|
|ID_CATEGORY|Код котегории контракта|
|V_EXT_IDENT|Внешний идентификатор контракта|

### trans_external
| Столбец | Описание |
| --- | --- |
|ID_TRANS|Уникальный код платежа|
|ID_CONTRACT|Код контракта|
|ID_TRANS_TYPE|Уникальный код типа проводки.|
|ID_SOURCE|Уникальный код источника платежа|
|F_SUM||
|V_STATUS|Статус:A - активный D - удалён|
|ID_REPPERIOD_CREATION|Уникальный код отчётного периода создания платежа|
|ID_REPPERIOD_DELETION|Уникальный код отчётного периода удаления платежа|
|ID_MANAGER|Код оператора, внёсшего платёж|
|ID_MANAGER_DELETE|Код оператора, удалившего платёж|
|DT_EVENT|Дата фактического поступления платежа в систему|

### fw_departments
| Столбец | Описание |
| --- | --- |
|ID_DEPARTMENT|Уникальный код департамента|
|ID_PARENT|Ссылка на код, являющийся родителем|
|V_NAME|Уникальное наменование|
|B_DELETED|Признак удаленной записи|

### fw_currency
| Столбец | Описание |
| --- | --- |
|ID_CURRENCY||
|V_CODE|Буквенный код валюты|
|V_NAME|Наименование валюты|
|B_DELETED|Признак удаленности записи|
|V_PRINT_NAME|Видимое сокращённое название валюты, например: рубль=р.|

## Задачи



1. Создать отчет по платежам за последний месяц в разрезе департаментов 
Результат: наименование департамента, сумма платежей в этом департаменте за последний месяц, количество платежей в этом департаменте за последний месяц, количество контрактов в этом департаменте. 
2. Найти контракты, на которые в 2017 году было совершено более 3 платежей
Результат: номер лицевого счета, статус контракта, количество платежей на этом контракте за 2017 году
3. Найти такие департаменты, к которым не привязано ни одного контракта
Результат: наименование департаментов
4. Вывести количество платежей на контрактах.
Результат: количество платежей, дата последнего платежа, номер лицевого счета контракта, имя пользователя, создавшего платеж
5.  Найти те контракты, у которых менялась валюта, например, была указана валюта рубль, потом появилась новая запись с валютой уже доллар
Результат: код контракта, лицевой счет, статус, наименование валюты Данные вывести на текущий день
6. Вывести отчет по сумме активных платежей на контракте за каждый год. Результат: Сумма платежей на контракте, идентификатор контракта, наименование департамента, дата начала года