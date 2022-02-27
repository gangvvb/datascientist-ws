# DataScientist_WS

# Сессия 1

1.1 Предобработка данных и выделение значимых атрибутов.
Задача автоматической сортировки корреспонденции заключается в определении адресата для входящих документов. Исходя из этого, необходимо определить, какие атрибуты имеют наибольшее влияние на классификацию входящих документов и оставить только их для последующего обучения. Также необходимо обосновать выбор атрибутов.

Используемые библиотека - pandas, re, matplotlib, pymorphy2, nltk, collections, wordcloud

Анализ данных — это процесс сбора, преобразования, очистки и моделирования данных с целью обнаружения необходимой информации. Полученные результаты сообщаются, предлагая выводы и поддерживая принятие решений. Визуализация данных иногда используется для изображения данных для облегчения обнаружения полезных шаблонов в данных. Термины «Моделирование данных» и «Анализ данных» означают одно и то же.

1.2 Разбиение сложных атрибутов.
В исходных данных есть поля, представляющие собой конкатенацию нескольких, иногда разнотипных, значений. Необходимо выделить и разбить такие поля на несколько других

Удаляем пропущенные значеия, не трогая колонку примечания.

1.3 Дополнение недостающими данными.
Согласно алгоритму направления входящей документации, письма от конкретных лиц и организаций направляются разным сотрудникам Союза. Так, например, от первых лиц министерств – непосредственно Генеральному директору, независимо от указанного адресата. Однако в исходных данных отсутствует информация о том, кем является отправитель. Такая же ситуация с адресатом, система, определяющая направление документа по фамилии будет являться частным случаем решения, и в случае кадровых перестановок не сможет функционировать. В связи с этим, необходимо проанализировать исходный набор данных и дополнить его.

Создаём доп. признаки на основе краткого содержания и даты регистрации, из которой мы можем взять месяц отправки. Переводим дату в datetime. Анализируем дату регистрации.

1.4 Формирование словарей данных.
Сформируйте отдельный атрибут или атрибуты, где будет содержаться анализ краткого содержания документов по количеству вхождений ключевых слов. Проанализируйте возможность определения адресата, используя полученные словари и Перечень вопросов и список руководителей, кому делегировано рассмотрение и подписание ответов.

![image](https://user-images.githubusercontent.com/94251604/155878975-59d42840-5ed8-4b7e-94e1-f84a96e5feca.png)
График

![image](https://user-images.githubusercontent.com/94251604/155878986-1f9255f2-0894-443e-bbb1-c74bd6813bad.png)
Облако слов

1.5 Преобразование списков переадресаций
В исходных данных некоторые письма переадресуются другим сотрудникам. Необходимо выявить такие строки и изменить начального адресата на того, кому в итоге был направлен документ

Вытаскиваем Авторов (от которых исходит письмо). Переписать список откуда и куда, сравнить строки. Анализируем форму составления кратного сожержания

# Сессия 2

2.1 Классификация документов
Выберите модель классификации входящих документов по адресату, приведите обоснование выбора модели. Разделите исходный набор данных на обучающую и тестирующую выборки оптимальным образом.

2.2 Визуализация зависимостей данных
Используя программные средства, визуализируйте зависимости атрибутов в наборе данных.  Визуализация должна отражать влияние атрибутов на определение класса (адресата). Произведите расчеты зависимостей по выбранным алгоритмам. Приведите интерпретацию полученным результатам

2.3Подготовка отчета
Подготовьте отчет, содержащий следующие пункты:
	Обоснование выбора модели классификации
	Выбор способов визуализации
	Результаты визуализации
	Обоснование способа разделения на обучающую и тестирующую выборки

# Сессия 3

3.1 Обучение
Проведите обучение выбранной модели на обучающей выборке, сформированной в предыдущей сессии. Протестируйте работу обученной модели на тестовой выборке.Определите показатели точности работы выбранной модели, сравните с остальными рассматриваемыми моделями.

3.2FeatureEngineering
Путём преобразования набора данных, добейтесь более точной работы выбранной модели. Опишите приемы генерации новых данных и результаты, к которым они привели, рассматривая все ранее определенные показатели точности

3.3Подготовка отчета
Подготовьте отчет, содержащий следующие пункты:
	Выбор показателей точности работы модели
	Точность работы выбранной модели в сравнении с другими рассматриваемыми моделями
	Результаты FeatureEngineering

# Сессия 4

4.1 Разработка бота
Вам необходимо разработать программный продукт – бота, который будет выполнять следующие действия:
	По введенным параметрам выполнять команды определения адресата по описанию входного документа, выдачи документов за определенный период по заданному адресату
	Распознавать команды, описанные на естественном языке, например, «Кому бы можно было направить письмо, в котором написано …»
	Предоставлять справку по имеющимся командам и их параметрам

4.2Настройки бота
Реализовать параметры «жесткости» определения адресата таким образом, чтобы пользователь мог устанавливать возможность выдачи одного конкретного адресата, либо нескольких наиболее вероятных, для заданного текста документа

4.3Подготовка руководства пользователя
Разработать руководство пользователя для бота, в котором описать интерфейс и возможности для потенциального пользователя

# Сессия 5

5.1 Разработка API
Разработайте интерфейс, позволяющий подключить разработанный программный продукт в качестве модуля к системе электронного документооборота. Интерфейс должен предоставлять метод или совокупность методов, принимающих в качестве параметров выдачу структуры данных СЭД «Практика». В качестве результата должна возвращаться аналогичная структура с заполненным значением (значениями) атрибута Адресат

5.2Последующее обучение
Для повышения точности сортировки корреспонденции в разработанный программный продукт необходимо внеси опцию оценки корректности результата. Если оператор системы считает, что адресат определен неправильно, он должен иметь возможность внести изменения. При каждой такой ситуации должен дополняться новый набор данных, который в перспективе можно будет использовать для обучения модели.

5.3Программная документация
Для разработанного APIсоставьте программную документацию

API (application programming interface) — это набор готовых классов, функций, процедур, структур и констант, предоставляемые самим приложением или операционной системой для взаимодействия с внешними программами.
Например, у вас есть кот Барсик, который любит лежать на обеденном столе. Вам это не нравится. Вы говорите Барсику: «Барсик, брысь со стола!». Барсик хоть и нехотя, но слезает со стола. Так вот, API — это набор команд, благодаря которым кот Барсик понял хозяина, что ему следует слезь со стола. Другой пример, если программу (модуль, библиотеку) рассматривать как чёрный ящик, то API — это множество «ручек», которые доступны пользователю данного ящика и которые он может вертеть и дёргать.
При этом пользователю необязательно понимать и знать, что такое API. API это «язык» общения между двумя программами и необходим программистам. API создаётся чтобы приложения созданные разными разработчикам корректно существовали вместе и могли взаимодействовать друг с другом. Компоненты образуют иерархию, в результате которой высокоуровневые компоненты используют API низкоуровневых компонентов, а те, в свою очередь, используют API ещё более низкоуровневых компонентов. По такому принципу построены протоколы передачи данных по Интернет. Каждый уровень пользуется функциональностью предыдущего («нижележащего») уровня и, в свою очередь, предоставляет нужную функциональность следующему («вышележащему») уровню.
На рисунке ниже представлена схема СЭД «Кодекс: Документооборот», в которой отображено API для внешних систем, а также для внутренних в данной СЭД.
Сигнатура функции
Сигнатура функции — это часть общего объявления функции, позволяющая средствам трансляции идентифицировать функцию среди других. В различных языках программирования существуют разные представления о сигнатуре функции, что также тесно связано с возможностями перегрузки функций в этих языках.
Например, в языке программирования C++ простая функция однозначно опознаётся компилятором по её имени и последовательности типов её аргументов, что составляет сигнатуру функции в этом языке. Если функция является методом некоторого класса, то в сигнатуре будет участвовать и имя класса.
В языке программирования Java сигнатуру метода составляет его имя и последовательность типов параметров; тип возвращаемого значения в сигнатуре не участвует.
В СЭД «Кодекс: Документооборот» используется API на основе web-технологий REST-API, на её примере рассмотрим формирование вызова любого GET\POST запроса.
Семантика функции
Семантика функции — это описание того, что данная функция делает. Семантика функции включает в себя описание того, что является результатом вычисления функции, как и отчего этот результат зависит. Обычно результат выполнения зависит только от значений аргументов функции, но в некоторых модулях есть понятие состояния. Полным описанием семантики функций является исполняемый код функции или математическое определение функции.
В API находится обученная модель которую можно использоваться :D
