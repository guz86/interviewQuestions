# interviewQuestions
+ Unity, C#

Гит? Как взаимодействовать в команде? Ветки, открыть? Как добавить фитчу? Чем отличается Мерж от Ребейз?
Солид, кисс
Несколько хороших примеров когда какой паттерн использовать
Боксинг, анбоксинг, как работает память
Мультитрединг. использование юнити апи
что такое мэш, как просиходит рендер в юнити, как работает бэтчинг, какой он бывает, 
как оценивать производительность приложения
что делать если после портирования в мобильное приложении 10фпс
МVC паттерн
уровень транспорта - для сетевых игр
физика в юнити
как отправить запрос из юнити, что такое сокет
кватернион

• Понимание TPL, Async, Unity UI, Component System, Addressables, NetWorking, Message Bus
умение оценивать алгоритмическую сложность
базовые знания о сетевом взаимодействии (сокеты)

+Собеседование C# Junior developer





C#
CLR среда, Garbidge Collector как работает(событие подписать, отписаться, утечка памяти)

-Что вы знаете о Garbage collector'e ?

освобождение памяти, занятой объектами, которые стали бесполезными и не используются в дальнейшей работе приложения



-Что такое массив?

Массив представляет набор однотипных данных

-Что такое типы данных? 

Если есть тип Т и переменная x типа Т, то это означало, что переменная может принимать значения из множества, заданного типом, и к ней применимы операции, разрешенные типом.

-какие бывают?

-Типы-значения ( value ), или значимые типы.
-Ссылочные ( reference ).
-Указатели ( pointer ).
-Тип void.

К значимым типам относятся: логический, арифметический, структуры, перечисление. Массивы, строки и классы относятся к ссылочным типам.

какие бывают структуры данных?

Структуры C# представляют частный случай класса. Определив свой класс как структуру, программист получает возможность отнести класс к значимым типам


Ссылочные и значимые типы разница? 

 Для ссылочного типа значение задает ссылку на область памяти в "куче", где расположен соответствующий объект. Для значимого типа используется прямая адресация, значение хранит собственно данные, и память для них отводится, как правило, в стеке.

Если переменная ссылочного типа, при присваивании значения одной переменной к другой переменной будет копироваться ссылка, в случае со значимыми типами будет передоваться значение. Если в ссылочной переменной поменять значение переменной то оно поменяется и в другой переменной.

Динамический массив, List (обертка над обычным массивом) в чем разница? За счет чего в List можно легко добавлять данные?

Что такое ООП? Основные Столпы? 

- Инкапсуляция

Объединение данных и методов в один объект и защита внутреннего состояния объекта от других воздействий. Пользователь должен видеть только список декларируемых свойств и методов и не вникать во внутренную реализацию.

- Пример инкапсуляции?

Если у нас есть класс, который представляет кошелек с деньгами. Например у него будут два метода позволяющие просматривать количество денег и изменять его. Кошелек может хранить отрицательное количество денег. Для инкапсуляции нам нужно добавить методы: Добавить деньги если это положительное число, взять деньги, если это положительное число и количество денег не больше того что в кошельке. Таким образом мы не сможем потратить денег больше чем имеется и сумма в кошельке не будет отрицательной.

Пример в Unity
Player имеет методы Движение, ПоворотВлево, ПоворотВправо. Поля Скорость и Направление, мы можем задать отрицательную скорость или направить Player под землю. Как защитить от неправильного изменения? Закрыть полностью Направление, Закроем поле для редактирования и сделаем доступным для инспектора [SerializeField]. 


- Наследование

Зависимость и отношение, один класс - продолжение другого. Инструмент позволяет избежать дублирования кода и позволяет реализовать полиморфизм.

- Пример наследования

Например есть класс Человека с именем и фамилией и методом вывода кода на экран.
Сделаем класс студент, который будет наследовать все поля и методы класса Человек.
В новый класс студент мы можем добавить новый функционал, например метод Учиться. Мы так же можем переопределить работу методов базового класса. 


Полиморфизм (полиморфизм подтипов) - паттерн стратегия и шаблонный метод - объясняет что и зачем нужно

Возможность использовать классы потомки в том же контексте что и базовый класс.

- Пример полиморфизма?

 Если у нас есть класс Машина и он имеет метод Управлять. У нас есть класс Человек и у него есть тоже метод Управлять, который принимает объект класса Машина, и у этого объекта мы вызываем метод Управлять. Мы можем добавить наследника Спортивная машина, в базовом классе метод Управлять мы сделаем виртуальным virtual и в классе наследнике добавим override метод Управлять, где мы реализуем возможность управления спортивной машиной. И в зависимости от того какой класс мы передадим человеку в методе Управления, реализуется логика - для обычный или спортивной машины. При этом мы никаким образом не меняем класс Человека в этом и заключается суть полиморфизма.  

- Чем отличается класс от абстрактного класса?
- Абстрактный класс? зачем нужны?

Абстрактный класс это некая идея, описание контракта с возможной частичной реализацией в наследниках класса. 
Нечто абстрактное которое должно делать что-то разными способами. В абстрактном классе можно указать астрактный метод без реализации. Так же можно указать конкретную реализацию - метод. Все наследуемые классы могут использовать этот метод. Другой класс в методах может использовать в качестве параметра объект типа нашего абстрактного класса, тогда любой объект который унаследован из астрактного класса может передаваться в качестве параметра. Наследники обязаны реализовать метод от абстрактного класса(override - для переопределения абстрактного метода). 

- Интерфейс? зачем нужны?
С помощью интерфейсов мы определяем поведение(сигнатура метода) которое будет реализовано в каком-то классе. Интерфейсы позволяют реализовать множественное наследование, они наследуются между собой или один класс может наследовать несколько интерфейсов. Говорят: Класс реализует интерфейс. В интерфейсе не может быть конструкторов, не может содержать поля. Модификаторы доступа для методов и интерфейса всегда public, не указываются - публичный контракт.



Делегаты и события? в чем разница?
Делегат описывает что метод будет принимать, что возвращать.

Подписка методов на события?


Когда вызывается статический конструктор?

В чем преимущество StringBuilder перед String ?

Что такое Linq?

оператор using?

как реализовывать правильно интерфейсы в структурах?

зачем нужен и для чего используется паттерн состояние?
паттерн обсервер (событие) и медиатор?
паттерн Фасад?


## Unity Junior Developer - Требования к кандидатам
Как работают функции Awake/Start?

- В чем разница между  Awake и Start?

Awake вызывается перед Start, а Start вызывается перед РЕНДЕРИНГОМ кадра для инициализируемого GameObject

Как работает функция Update?
Для чего предназначен класс Transform?
Для чего предназначен класс GameObject?
Как создать/удалить GameObject на сцене через код?
Как можно переместить объект в игре с помощью скрипта?

-В чем разница в скриптах между Image и Sprite?

Image это элемент управления изображением, а спрайт это отображаемое изображение. Image Displays a Sprite for the UI System.

Как сделать так чтобы объект не удалился при переходе из одной сцены в другу?

- Для чего нужен тег [SerializeField]?

Для того чтобы сделать поле доступным из инспектора

Принципы ООП и зачем они нужны в геймдеве?
 
наследование
разница между классом и объектом
какое преимущество дают принципы ООП
для чего нужны статические классы и как используются
Паттерн Одиночка - как работают, написать код для объяснения
Паттерн Абстрактная фабрика - как работают, написать код для объяснения
ГИТ - пуш, коммит, мердж, пул
Фотошоп мелкие задачи, чтобы не дергать дизайнера



## Вопросы на собеседование unity junior developer

### C
- Основные принципы ООП?
> ООП -



- Пример наследования?


- Чем отличается интерфейс от абстрактного класса? В каких случаях вы использовали бы и то, и другое?
- Чем отличается абстрактный класс от интерфейса? Для чего нужны интерфейсы и какие задачи они выполняют?
- В чем отличие интерфейса от абстрактного класса ?

Общее: Один из принципов проектирования - нужно программировать на уровне абстракций, а не реализации, под абстракцией как раз и понимается интерфейс или абстрактный класс. Вызывающий код работает по определенному контракту и не вдается в детали реализации.(фабрика, загрузочная операция) - код который использует их ничего не знает о том какой класс в данный момент реализуется, это позволет подменять реализацию поведения на ходу избегая длинных и сложных условий. Нельзя напрямую создать экземпляр абстрактного класса или интерфейса.
Отличия:
1. Астрактый класс может содержать логику и состояние, интерфейс - нет, это модель поведения, контракт. Абстрактный класс наследуется а интерфейс реализуется. Если классы могут быть сведены к единой классификации, то следует применять абстрактый класс. Пример с фабрикой по созданию объектов - общий функционал - выделение отдельной сцены, в которой будут создаваться объекты, этот функционал нужен во всех наследниках. Если у классов нет общей логики то для них сгодится интерфейс(каждая операция отличается от другой). 
2. Множественное наследование. В интефейсе можно выполнять наследование, это позволяет выделять различные аспекты поведения объекта под определенным интерфейсом. Вызывающий код будет работать с интерфейсом. Такой подход оберегает от излишнего использования объекта сторонними классами. - при явной реализации интерфейса.
При неявной реализации - это обычный публичный метод доступный для всех. 
3. Все члены интерфейса по умолчанию являются доступными для использования в явном или не явном виде. Поменять модификатор доступа нельзя. Астрактый метод или свойство могут быть protected.
4. Интерфейс не может содержать переменные или делегаты, в отличии от абстрактного класса. 

Резюмируя: Абстрактный класс применяют там где нужно выделить четкое семейство классов, с общим функционалом и состоянием. Интерфейс применяется там где разница наследников велика и ничего кроме общей модели поведения нет.




- Что такое конструктор и деструктор ?

- Какие бывают типы переменных в c# ?
- Что такое ссылочные переменные и переменные значения ?

- С какими коллекциями ( Collections ) вы работали и как ?

- Какие паттерны вы знаете и как их использовали ?

- Что такое упаковка/распаковка ?

- Что такое побитовый сдвиг и как он используеться в Unity ?

- Что такое delegate ?
- Что такое event ?
- Приведите пример взаимодействия через событие

- Что такое хеш код объекта ?
- Для чего нужны хеш таблицы ?

- Пишите ли вы шейдеры под Unity ?
- Пишите ли вы плагины под Unity ?
- Какие вы знаете приемы оптимизации под мобильные устройства ?
  Урок по оптимизации в Unity

Математика:
1. Что такое кватернион ?

Кватернионы используются для представления вращений.
В Unity все вращения представлены в виде кватернионов. Их использование решает проблему "шарнирного замка" (gimbal lock).

2. Как найти угол между двумя векторами ?
3. Как найти вектор перпендикулярный 2м векторам ?
4. Придумайте алгоритм, который выдает элемент из массива в зависимости от вероятности его выпадения

3D:
1. Из чего состоит 3D модель ? ( вертексы, текстурные координаты...)
2. Что такое материал ?
3. Что такое карта нормалей ? ( normal map )
4. Что такое pivot 3D модели ?



Вопросы для Junior
Общее

1. Назовите основные принципы ООП.

2. Что такое наследование, инкапсуляция, абстракция, полиморфизм: приведите примеры (желательно из собственного опыта). От какого класса неявно наследуются все классы в .NET? Разрешено ли множественное наследование в C#?

3. Что такое рекурсия?

4. Что такое лямбда-выражение?

5. Что такое параллельное программирование (многопоточность) и его назначение? Какие классы используются?

6. Что такое JSON?

7. Как вы понимаете REST?

8. Расскажите о SPA concept.

9. Какие GoF-паттерны использовали?

10. Какая разница между GET и POST HTTP методами?

11. Какую проблему решает Docker? Каковы его плюсы и минусы?

12. Чем принципиально отличаются unit-тесты от интеграционных тестов?

 

Обработка исключений

13. Что такое Exception?

14. Для чего служат try, catch, finally? В каком случае может не выполниться блок finally?

15. Что такое call stack? Какие ключевые слова вы знаете?

 

Платформа .NET

16. Что такое ASP.NET?

17. Какие существуют типы Action filters?

18. Что такое Web Service?

19. Что такое CLR?

20. Что такое сборщик мусора (Garbage Collector) на базовом уровне?
CLR сама вызовет сборщик мусора и очистит память.

21. Что такое делегат?

22. Отличается ли Delegate от Action?

23. Что такое LINQ и для чего используется? Приведите несколько примеров применения LINQ.

24. Что такое пространство имен (namespace) и зачем это нужно?

 Логически классы с близкой функциональностью объединяются в группы, называемые пространством имен (Namespace)
Пространства имен позволяют структурировать проекты, содержащие большое число классов, объединяя в одну группу близкие классы.
 Помимо структуризации, это дает возможность присваивать классам имена, не задумываясь об их уникальности. 
 

Типы данных, коллекции и структуры данных

25. Какие типы данных вы знаете?

26. Какие примитивные типы знаете?

27. Что такое Nullable-тип?

28. Что такое тип значения, а что такое тип ссылки? Что из этого class, а что struct? В каком участке памяти они хранятся?

29. Чем отличаются value от reference type? String - это reference или value?

30.В чем отличие между string builder и string?

31. Что такое дженерики? Какие проблемы они решают?

32. Что такое boxing / unboxing?

33. Что такое Array, List, HashSet, Dictionary? Приведите примеры использования этих структур данных. Какая сложность операций с ними (поиск, вставка, удаление)?

34. Какие знаете коллекции?

35. Что делает оператор yield?

 
 

36. Что такое класс?



39. Какие вы знаете модификаторы доступа?

40. В чем разница между обычным классом и статическим?

41. В чем разница переопределения метода между ключевыми словами new и override?

42. Какое различие между const и read only?

43. Разница между структурой и классом. Приведите примеры структур.

44. Может ли экземпляр структуры храниться в куче (heap)? Как это сделать?

 

Асинхронность

45. Что такое асинхронность и чем она отличается от многопоточности?

46. Какие есть ключевые слова для использования асинхронности в коде?

47. Что означают ключевые слова async / await?

 

Базы данных

48. Разница между реляционными и нереляционными базами, плюсы и минусы использования обоих вариантов.

49. Что такое индексы в RDBMS?

50. Какие типы JOIN существуют в SQL?

 

Тестирование

51. Для чего нужны unit-тесты?

52. Какие преимущества и недостатки использования unit-тестов?

53. Из каких трех логических блоков состоит unit-тест?

 

Вопросы для Middle
 

Общее

54. Вы набираете google.com в браузере. Расскажите как можно подробнее, что происходит в это время на HTTP-уровне?

55. Как работает HTTPS?

56. Как вы понимаете SOLID?

S - Single-responsiblity Principle
Принцип единой отвественности. Метод, класс, модуль должны иметь только одну зону ответственности. 
Например если есть модуль LeaderBoard - единая отвественность это отображение списка пользователей по каким то признакам. Ни при какой логике тут не может быть логики сохранения, логина или покупок. Это все другие модули. Модуль может с ними общаться но без подробности реализации. Модуль делиться на классы. классы на методы и с каждым понижением уровня снижается объем ответственности. 
Плюсы: Снижение сложности кода, Переиспользуемость, Тестируемость. 
Минусы: Уменьшение скорости разработки. 

O - Open-closed Principle
Принцип открытости закрытости. Сущности должны быть открыты для расширения и закрыты для изменения. Играет важную роль по мере развития проекта. Меняется текущий код при добавлении функционала и можно что-то сломать. Код должен быть закрыт для изменения - Стратегия, декоратор и фабрика - отлично помогают расширять функционал без изменений исходного кода. Нужно определить что поменять в коде, выделяется абстракция в виде интерфейса или абстрактного класса, от него наследуюется текущий функционал, под занавес абстракции создается новый функционал, который будет меняться в зависимости от каких то условий. 
Нужно применять очень дозированнно, т.к. чрезмерно абстрактный код является очень сложным для понимания. 
Плюсы: Безопасное внедрение новой функциональности, слабая связанность кода, Тестируемость.
Минусы: Черезмерное использование ведет к невозможности поддержния проекта.

L - Liskov Substitution Principle
Принцип подстановки Барбары Лисков. Звучит он так: функции, которые используют базовый тип, должны иметь возможность использовать подтипы базового типа, не зная об этом. Классы-наследники не должны противоречить базовому классу. Если переопределить какой нибудь из методов - сломает принцип. Виртуальные методы являются прямым нарушением принципа. Более грубое нарушение - наследовать базовый класс так, что вызывающий код должен делать проверку на тип и совершать какие-то дополнительные действия. 
Плюсы: устойчивость к ошибкам,  слабая связанность, тестируемость.
Минусы: сложность применения.

I - Interface Segregation Principle
Принцип разделения интерфейсов. Идет рука об руку с первым принципом единой отвественности. Разделение больших интерфейсов на маленькие, чтобы минимизировать количество членов, которые нужно реализовать. Нарушение - нежелание создавать новый интерфейс при добавлении нового функционала.

D - Dependency Inversion Principle
Инверсия зависимостей. Модули верхних уровней не должны зависеть от модулей нижних уровней. Оба этих слоя должны зависеть от астракций. Инверсия - идем снизу вверх.  (пример паттерн-фабрика - у нижнего уровня выделяется общий аспект поведения состояния и переносите в интерфейс или базовый класс, а дальше он уже используется на верхнем уровне. "Дай объект который наследуется от абстракции." )

57. Какие протоколы сериализации вы знаете и где они применяются?

58. Что такое в вашем понимании чистая функция? Какие у нее преимущества?

Тема связана со специальностями:

 
С чего начать?
 
Frontend Developer
 
Верстальщик сайтов
59. Что такое dependency injection и зачем оно нужно?

60. Что такое cohesion и coupling (связанность и связность)?

61. Что такое IaaS, PaaS, SaaS и каковы различия между ними?

62. Какие способы отладки программы вы используете?

63. Какие знаете паттерны? Объясните суть перечисленных.

64. В чем суть паттерна Singleton? Почему его еще называют антипаттерном?

65. Для чего нужен паттерн Strategy?

66. Какие ключевые различия между распределенными системами и монолитными?

67. Какие паттерны проектирования распределенных систем вы знаете?

68. Какие есть принципы работы Message bus? Почему могут возникать дубликаты в очередях?

69. Какие принципы построения идемпотентных сервисов знаете?

70. Расскажите, как работают асинхронные методы? Чем асинхронность отличается от параллелизма?

 

Платформа .NET

71. Какие исключения нельзя остановить в блоке catch?

72. Какая разница между .NET Standard Class Library и .NET Core Class Library?

73. Объясните разницу между отложенным и немедленным исполнением в LINQ. Приведите примеры.

74. Для чего нужен метод ConfigureServices в Startup.cs?

75. Какая разница между services.AddTransient и services.AddScope в ASP.NET Core?

76. Что такое Kestrel?

77. Опишите ASP.NET MVC request pipeline.

78. Как в ASP.NET WebAPI настроить кэширование ответов на HTTP-запросы?

 

Управление памятью

79. Что такое куча и стек? Различия, принцип работы.

80. Как работает сборщик мусора?

81. Зачем нам зарезервированное слово using в C#, если в .NET есть автоматическое управление памятью? Как с этим связан disposable-паттерн и зачем такой сложный паттерн для managed и unmanaged ресурсов?

82. Какие особенности работы с Large Object Heap?

 

Типы данных, коллекции и структуры данных

83. Когда генерируется дженерик-класс конкретного типа - при выполнении программы или во время компиляции?

84. Что такое рефлексия?

85. Расскажите о коллекции LinkedList <T>. Чем она отличается от других коллекций?

86. Что такое индексатор?

87. Что такое immutable object? Какие преимущества дает использование immutable object? Предложите способ реализации его в .NET.

88. Когда использовать StringBuilder, а когда string? Как работает StringBuilder?

89. Что такое балансирование деревьев?

90. Что такое Key-value структуры?

100. Что такое хэш-функция и зачем нужны хэш-таблицы?

101. Какими свойствами должна обладать идеальная хеш-функция?

102. Что такое коллизии и как с ними бороться?

103. В чем заключается сложность CRUD-операций в Dictionary <K, V> в .NET?

104. Где хранятся массивы? Массивы примитивных типов?

105. В чем отличие между массивом (T [ ]) и списком (List <T>)?

106. В чем разница между IList <T> и IEnumerable <T>?

107. Зачем нужны Enumerable, Observable, AsyncEnumerable и какие модели получения данных они реализуют?

108. В чем разница между IEnumerable и IQueryable?

109. Что такое enum flags?

 

Базы данных

110. Расскажите о нормальных формах в СУБД.

111. Что такое индекс в БД?

112. Когда следует использовать индексы? Преимущества и недостатки.

113. Какие типы индексов существуют? Чем они отличаются?

114. Что такое ACID?

115. Какие вы знаете уровни изоляции транзакций?

116. Что такое план выполнения запроса (execution plan) в MS SQL?

117. Проблема: запрос долго выполняется. Какие есть методы ее диагностики и решения?

118. Как ORM (Entity Framework или Entity Framework Core) транслируют C# код в язык запросов базы данных? Что для этого используется?

 

Параллелизм

119. Для чего использовать Task.ConfigureAwait?

120. Например, есть веб-сервер, который по HTTP-запросу делает выборку из базы данных. Всего на сервере 16 тредов (threads). Каждый HTTP-request выполняет запрос в базу и ожидает результатов, в этом случае тред блокируется. Можно ли оптимизировать эту работу средствами .NET?

121. Зачем нужен ThreadPool? Опишите механику работы: как поток выделяется и возвращается обратно в ThreadPool.

 

Вопросы для Senior
 

Общее

122. Какие ещё практики, кроме ООП, использовали (AOP, FP и т. д.)?

123. Назовите три самые сложные проблемы, которые вам приходилось решать. Как вы это сделали, как пришли к этому решению?

124. Что такое слабосвязанный код? Чем он лучше сильносвязанного кода? Как бы вы достигали более слабой связности кода?

125. Использование статических классов повышает или понижает связность кода?

126. Как можно измерить performance кода? Влияет ли факт замеров на производительность?

127. Для чего используются и как работают multi-stage билды в Docker?

128. Как понять, что какая-то часть кода утилизирует много памяти или долго выполняется? Что может быть ботлнеком в разных случаях? Какие есть способы уменьшения памяти и трафика памяти?

129. Как бы вы реализовали cross-cutting concern (например, логирование, валидация, транзакции)?

130. Расскажите о Rest Maturity Model.

Видео курсы по схожей тематике:

ASP.NET Базовый
ASP.NET Базовый

Дмитрий Охрименко
Выполнение домашнего задания по курсу C# Базовый
Выполнение домашнего задания по курсу C# Базовый

Константин Черный
Автоматизация тестирования на С#
Автоматизация тестирования на С#

Татьяна Пешкова
131. Что такое CPU и IO-bound задачи?

132. Что такое маршалинг?

133. Как работает async / await (подробно)? Почему нельзя использовать async void методы?

 

Платформа .NET

134. Как работает lock? Можно ли использовать структуры внутри выражения lock?

135. Что такое Expression Tree?

136. Как работает сборщик мусора (подробно)? Почему в GC три поколения, а не, скажем, пять, десять или два?

137. Как бы вы организовали трассировки Web API сервисов?

138. Как в .NET Core можно настроить хранение секретов на компьютерах разработчиков и на рабочих средах?

139. Как бы вы организовали процесс CI/CD .NET Core сервисов для их деплоймента в облачную инфраструктуру?

140. Как включить CORS в AspNetCore?

 

Типы данных, коллекции и структуры данных

141. Как реализованы дженерики?

142. Как создать собственный immutable-тип?

143. Как работает IEnumerable <T> (подробно)?

144. Какой алгоритм использует коллекция STACK?

145. Какие структуры данных вы реализовывали сами для платформы .NET? Расскажите, чем они отличались от стандартных реализаций.

147. Почему в структуре нет конструктора по умолчанию?

 

Базы данных

148. Как БД сохраняет данные?

149. Какие типы БД вы знаете?

150. Как и когда БД лучше использовать?

151. Что такое денормализации?

152. Когда и какие уровни изоляции транзакций можно использовать?

153. Как в популярных СУБД реализованы принципы ACID (SQL Server, PostgreSQL и т. д.)?

154. Приходилось ли вам оптимизировать запрос в БД? Если да, то как?

155. Опишите, какие вы знаете потенциальные проблемы, связанные с параллельными запросами к БД.

156. Какую базу данных вы бы использовали для реализации distributed lock механизма? Расскажите детали реализации.

 

Микросервисы

157. Какую проблему решают микросервисы?

158. Какие есть способы коммуникации микросервисов?

159. Расскажите варианты реализации распределенных транзакций в микросервисах.

160. Что такое circuit breaker?

161. Каким образом вы будете налаживать систему, состоящую из множества микросервисов, если нужно отследить полный путь обработки запроса?

162. Что такое брокеры сообщений? Что такое at-least-once, at-most-once семантика? Есть ли какие-то брокеры, которые гарантируют exactly-once семантику?

163. Как должен работать код клиента брокера в зависимости от выбранной семантики?

164. Какие инструменты для работы с очередями вам известны (как в .NET, так и отдельные продукты), какой инструмент/продукт вы бы выбрали и почему?

 

MS Azure

165. Какие виды сервисов бывают в Service Fabric?

166. Какие особенности и ограничения Azure Table Storage?

167. Как бороться с проблемой холодного старта в Azure Functions?

168. В чем отличие очередей и топиков в Azure Service Bus?

 

Практические задания
 

Junior only

Опишите, как бы вы реализовали калькулятор. Если понадобится добавить поддержку для римской системы счисления, что будете делать?
Напишите программу, чтобы проверить, является ли число простым или нет.
Найдите наименьший элемент в массиве.
Упорядочите структуры папок в файловой системе.
Напишите программу, которая симулирует fizz-buzz.
Расскажите, что делает этот код, и предложите, как его улучшить.
а)

public bool IsArrayEmpty(string[] array)
{
  if (array.Length > 0)
    return false;
  else
    return true;
}
 

б)

protected string GetClass(object url)
{
  string result = string.Empty;
  if (SiteMap.CurrentNode != null && SiteMap.CurrentNode.Url == url.ToString())
    result = "class=\"active\"";
  return result;
}
 

Middle

Напишите программу для тиражирования последовательности Фибоначчи для заданного числа.
Спроектируйте базу данных врачей и пациентов в SQL. Создайте stored procedure или запрос в SQL, который вернет врачей, имеющих больше, чем N пациентов.
Проверьте коллекцию на наличие дубликатов.
Спроектируйте thread-safe класс Singleton в C#.
Надо записать некую сущность в базу данных и отправить событие в брокер сообщений. Как это сделать с минимальным риском потери данных?
Имеются три сервиса. Выполняется HTTP-запрос на первый. Первый должен записать данные во второй, а второй - в третий. Как гарантировать, что данные при такой сложной коммуникации не потеряются? Как предотвратить записи дубликатов данных?
Будет ли работать этот код и почему?
a)

SomeClass myClass = null;
myClass.SomeMethod();
 

б)

var table = GetTable();
table.Draw();
…
private SomeClass GetTable()
{
  using(var table = new SomeClass())
  {
    table.ID = "www";
    table.Width = "95%";
    table.Controls.Add(tr);
    return table;
  }
}
Расскажите, что делает этот код, и предложите, как его улучшить:
а)

Shape shape = GetNextShape();
if(shape is Circle)
Console.WriteLine(((Circle)shape).Radius);
 

б)

public int Quantity
{
  get
  {
    try
    {
      return int.Parse(TxtQuantity.Text);
    }
    catch (Exception)
    {
      return 0;
    }
  }
}
 

Что не так с кодом?
 

try
{
  SomeMethod();
}
catch(Exception e)
{
  Log(e.Message);
  throw e;
}
 

Senior

Как бы вы спроектировали FTP-сервер? Web-сервер? Хостинг картинок с разделением прав доступа? Систему, состоящую из front- и back-офисов? Создайте клон любой популярной социальной сети (Instagram, Facebook и т.д.)
Допустим, есть сущность сделки (Bid). И в сделке есть список партнеров, с которыми эта сделка заключается. Сами сделки хранятся в сервисе сделок (bidding service), а партнеры - в своем сервисе (partners service). И когда показывается список сделок, на начальном скрине нужно отразить количество партнеров. Как бы вы спроектировали хранение и изображение этого счетчика?
Задача на знание LINQ: с исходной коллекции данных необходимо получить новую коллекцию по определенным требованиям (например, отсортированную, без дубликатов и т. д.).
Напишите программу, которая проверяет, является ли поле судоку 9×9 правильно заполненным.
Реализуйте свой Select, Where, SelectMany со всеми характеристиками LINQ (отложенное исполнение, одномоментная (eager) проверка входных данных).
С помощью LINQ напишите метод, который вернет такие элементы коллекции, которые делятся на N без остатка, отсортированные от наибольшего значения к наименьшему. Сигнатура метода: List <int> Filter (IEnumerable <int> collection, int n) ;.
Напишите функцию, которая вернет сумму всех четных элементов массива, который передается в функцию (JavaScript).
  
  
  
https://www.interviewbit.com/c-sharp-interview-questions/
https://www.simplilearn.com/tutorials/c-sharp-tutorial/c-sharp-interview-questions
https://hackr.io/blog/c-sharp-interview-questions
https://www.guru99.com/c-sharp-interview-questions.html
https://www.devteam.space/hiring-interview-tips/c-interview-questions-and-answers/
https://blog.udemy.com/c-sharp-interview-questions-2/
https://www.edureka.co/blog/interview-questions/c-sharp-interview-questions/
https://www.turing.com/blog/c-interview-questions-to-hire-c-developers-in-2022/
https://www.javatpoint.com/c-sharp-interview-questions
https://www.naukri.com/learning/articles/c-sharp-interview-questions-and-answers/
https://itvdn.com/ru/blog/article/150-questions-net-developer
https://habr.com/ru/post/541194/
https://www.programcreek.com/2012/11/top-10-algorithms-for-coding-interview/
https://www.toptal.com/c-sharp/top-10-mistakes-that-c-sharp-programmers-make
  
  
требования
▫️ Хорошее знание Rigidbody, Joint, Animation, Navigation Mesh, Input System, Raycast, Collider, Multithreading, URP
▫️ Понимание Unity Lifecycle
▫️Опыт в Zenject, UniRx, DOTween, UniTasks, Addressables, Burst Compiler, Unity Jobs

От джуниор/инди разработчика до мидл+ 
https://www.youtube.com/watch?v=jqeoq6X-5S8&t=3s
https://www.dropbox.com/s/pd6kwy1mj5c5ofd/From%20junior%20indie%20developer%20to%20middle%2B%20%28Eugen%20Dubovik%29.pdf?dl=0

Искать крупные компании на крупные проекты для понимания логики принятия тех или иных решений и лучших практик.

- Участие в завершенных проектах.
- Компетенции для разрабатываемого продукта(платформеры, матч3, стратегии и прочее) - нужны проекты по конкретной тематики и понимание архитектуры для конкретного проекта
- У программистов есть мифы(бэкпректис) нужно ставить все под сомнение 
- должна быть возможность отключить управление(обрабатывать input напрямую плохо input.GetKey)
- публичные переменные плохо, другой программист может их использовать.
-  Откуда брать знания:
mdsnReference
ютуб Unity3D - осторожно смотреть с критикой, смотреть про оптимизацию
github Unity-Technologies -есть samples как правильно использовать
jacksondunstan - глубоко копает в юнити
Habr - Pixonics
- Архитектура приложения: GameCore, PlayerProgress, Input, UI, Sound, Statistics, Tutorial, Quests/Scenarios, Save Data, Configs/PredefinedData, Localization - все начинается с инпута и сохранения данных, супер правильной архитектуры нет, нет идеальной
- архитектура должна иметь запас прочности по расширяемости, должны быть необходимые модули и понятные связи, удобство, минимум бойлерплейта, не должно быть сервис локаторов раздающих данные
- часто используемые архитектурные паттерны (MVC family) MVC-90% проектов(не нужна большая функциональность), т.к. большинство программистов использует вообще, хорошо для бизнес приложения но сложно применимо к геймдеву потому что сущности должны знать о других сущностях, появляются грабли, MVVM MVP
- компоненты и контроллеры - более ориентирована к геймдеву
- ЕСS
- Сложности: добавление механик, изменение старых, много условий для поведения, смена поведения в зависимости от контекста
- скачать и посмотреть unity3d kit
- часто используемые паттерны - состояние/ конечный автомат, стратегия, дерево принятия решений

советы
- создать рпг типа диабло на кубиках прототип
где будут разные классы с разными скилами(одноручное, двуручное оружие), апдейты для скилов
система инвентаря
бонусы атаки, защиты
система сохранения
система квестов
система диалогов
инструментарий для гейм и левел дизайнеров
системы звука и анимации
системы статистики
сохранение данных игрока в онлайн базе

изучать технологии и компетенции которые актуальны на рынке


**pro:**
adressables
render pipline
shader graph
vfx graph
кастомные инспекторые + uiElements+Odin
  
  
  
- Опыт использования профайлера в Unity;
- Опыт работы с Jenkins.
  
**Ваши вопросы:**
Менторы и лиды
Проекты
компенсации обучения
частота пересмотров зп
