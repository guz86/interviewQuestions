## interviewQuestionsJS

как проиходит рендреринг Web страницы

приоритеты CCS(специфичность)
    0) !important
    1) attrStyle
    2) ID
    3) атрибут
    4) класс
    5) тег (уточнения вес)

DOM?


Какие способы централизовать

    1) Flex
    display:flex;
    justify-content:center;
    align-items:center;

    2)Block
    width: 100px;
    margin: 0 auto;

    3) Grid demo
    display:grid;
    place-items:center;

    4) position:absolute; top:50%; transform: translateX(-50%)translateY(-50%);

    5) .parent{width:100%;height: 100%; display: table; text-align: center; } .parent > .child{display:table-cell; vertical-align: middle;}

    6) .parent {height: 200px; width: 400px; text-align:center; }
    .parent > .child { line-height: 200px; }
    
В чем разница async и defer? Особенности размещения
async - какой скрипт раньше загрузится тот и будет выполняться
defer - будут ожидать загрузки

HTML5 теги?

По какому правилу вкладываются теги друг в друга? Какие теги могут быть в нескольких местах?

Способы подключения стилей к странице?
		Через тег style и в него писать ccs, можно использовать link и инлайновые стили.
        
Методология BEM
	4 основных компонента блок элемент модификатор Микс https://ru.bem.info/methodology/quick-start/#%D0%9C%D0%B8%D0%BA%D1%81

Методология Atomic CSS





 

