### React.js
- Группируйте импорты, не должны быть мешанины реакт-роутера, компонентов, UI компонентов (правила линта можно настроить)
- Не забывем про притиер
- Используем реэкспорты что бы не было дублирование (./components/header/header)
- Если у нас в компоненты один интерфейс или пропс, то понятно, что они относятся к этому компоненту и не надо писать PropsButton или в таком духе (есть практика писать TButton - type, IButton - inteface, но это зависит как принято на проекте)
- При импорте styles можно сократить нейминг styles до буквы s
- Если в проекте тайпскрипт, то можно давать тип функциональному компоненту **React.FC => FC** (просто FC, без реакта)
- При импорте с реакт библиотеки FC,useState,useEffect и.т.д лучше отдельно импортировать хуки и отдельно FC (разделять импорты)
- Шпаргалка по типам (тс) https://react-typescript-cheatsheet.netlify.app/docs/basic/getting-started/default_props
- В компоненте app стараемся минимизировать логику (работаем уже с готовыми компонентами), app не должен знать про логику
- При работе со сторам(данными), задумывайтесь о том, на сколько быстро отработает ваш алгоритм (оценка сложности алгоритма)
- В стор стоит ложить сериализованные данные (данные которые можно конвертировать в JSON)
- При подключении middleware, надо сначала распаковать дефолтные мидлвары, а потом уже туда добавить logger
**middleware: [logger]
middleware: (getDefaultMiddleware) => getDefaultMiddleware().concat(logger)**
- Если ключу соответствует значение, то можно избавить от дублирование
**id:id => id**
- Нейминг функций, должен говорить о том, что они делают (clickHandler не говорит, о том, что делает функция) clickHandler => toggleFavorite
- Не стоит перегружать компонент и внутри создавать два и более подкомпонента, лучше их вынести в отдельный файл
- **Скидывать в пулл реквесты, файлы, которые можно ревьювить (если это временная заглушка,то это не стоит сбрасывать на проверку, если вы сами понимаете, что это не корректный код)**
- Использовать || вместо тернарника, по возможности
- Если с бэка приходят не корректные данные, то стоит их обработать и изменить на корректные с точки зрения фронтенда (использовать промежуточную функцию, или можно использовать transformResponseс ртк)
- Статические данные выносите за компонент (выше), ибо при каждом ререндере будут пересоздаваться статические данные, которые находятся в теле компонента.
- Фетч данных в компоненте стоит вынести в хук юзэффект
- Тайпскрипт иногда может сам определять тип данных не стоит писать **useState< string >('')**
- Название интерфейса с большой буквы interface Example 
- Следить за тем, что бы тип : void указывался для тех случаев, где он действительно уместен 
- Не стоит использовать тип any, т.к мы лешаем себя прелестей тайпскрипта
- Стоит добавить правило еслинт, которое будет говорить о том, что данные в коде не используются 
- Стоит избегать export default
- В консоль в юз эффекте будет отрабатывать 2 раза (из-за стрикт мода). Это у вас **НЕ** код отрабатывает 2 раза.
- Использовать React.memo, в случае, если UI компонент использует теже пропсы, что и на предыдущем рендере(или всегда)
- Консоль => шестеренка => Rendering => Paint flashing (начнет обводить компоненты в браузере зеленой рамкой, которые ререндерятся при пользовательских действиях)
- Если у вас в коде используются секретные данные, выносите их в **.env**
- Ссылка https://12factor.net/ (12 принципов построения приложения)
- Стараемся избегать восклицательный знак(!) в тайпскрипте
- Не мешать then и  await вместе
- Не забывайте указывать кнопке тайп
- Название css классов с маленькой буквы
- Следите за тем, что бы явно не указывать тру или фолс, вы должны понимать, в каких случаях условие возвращает тру, а в каких фолс
- Не добавляйте к именованию сущностей приставки arr, obj, func т.к это можно понять или из типов или по смыслу компонента 
- Избегайте сайд эффектов
- Выносить типы, не типизировать по месту назначения сущности
- Статья про юз эффект, в каких случаях его использовать, в каких лучше избегать https://beta.reactjs.org/learn/you-might-not-need-an-effect
- Отделяйте пустыми строчками логику, что бы легче было читать код
- Не стоит писать ретерн в стрелочных функциях then(res => {return res}) then(res => res)
- Не вешайте обработчик (онклик) на див
