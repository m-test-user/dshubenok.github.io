#
## UNIX и Линукс, краткая история

Перед тем, как начать писать программы на Питоне, нужно потратить пару недель на изучение некоторых фундаментальных инструментов. Этим мы и займемся на первом спринте. 

На этой неделе мы познакомимся с операционными системами семейства Unix. Большинство из вас (судя по проведенному опросу, 80%) сидят под Виндой. Так вот, Unix — это не Windows, они отличается как внутренне, так и идеологически. Ниже ты поймешь, почему так. 

В нескольких абзацах про историю создания Unix. Всё началось в Америке, примерно в 1969-1970, когда вот эти ребята...

![](/img/ken_and_dennis.jpg)

... **Кен Томпсон** и **Деннис Ритчи**, работавшие в компании Bell Labs, создали операционную систему Unix для нужд компании. Первая версия была написана на ассемблере (это такой очень сложный язык программирования низкого уровня), поэтому стороннему человеку было очень сложно что-либо понять, ребята заморочились и постепенно пришли к тому, что создали высокоуровневый язык программирования С (произносится как "Си") и переписали Unix на Си. Это позволило распространить Юникс среди ведущих университетов Америки, откуда и началось развитие разных ответвлений Unix-систем. Например, есть такой замечательный человек из Амстердама, **Эндрю Таненбаум...**

![](/img/andrew.png)

...автор нескольких фундаментальных книг и преподаватель университета, он создал свою операционную систему на основе Unix чисто для учебных целей и назвал её Minix. Теперь переносимся в Финляндию, молодой студент Хельсинского университета **Линус Торвальдс**...

![](/img/linus.jpg)

...во время своей учебы читает одну из книг Таненбаума «Операционные системы: разработка и реализация» и очень сильно вдохновляется, настолько сильно, что начинает создавать свою собственную операционную систему. К проекту подключается **Ричард Столлман**...

![](/img/richard.jpg)

... со своим проектом GNU и появляется свободная операционная система Linux. 

Ближе к двухтысячным компания Apple выпускает операционную систему DARWIN, которая послужила основой для современной MacOS, она была сделана по стандарту POSIX, это такой стандарт, который описывает совместимость unix-подобных операционных систем. Благодаря ему обеспечивается совместимость между всеми unix-подобными операционными системами. 

Что из этого всего надо вынести? **Начало эпохи UNIX** приходится на 1 января 1970 года. Запомни этот момент, он пригодится в будущем. 

Зачем нам всё это нужно? А затем, что на Unix-подобных операционных системах (в основном, на Линуксе) работает подавляющее большинство серверов, и тебе, как разработчику, придется постоянно иметь с этим дело. 

Заниматься разработкой следует на UNIX-подобных системах, таких как Linux, MacOS или FreeBSD. Использовать операционную систему Windows рекомендуется только тогда, когда пишешь под винду на C#. 

Мы не будем писать под Винду, поэтому в курсе по умолчанию будет Линукс, но всё применимо и для MacOS. Если у тебя Винда, и ты пока не хочешь ничего с этим делать (вполне разумный подход), то ниже есть абзац про то, как с этим жить. 

## Подключение к удаленному серверу

Это будет наше первое знакомство с географически удаленным сервером, он один для всех студентов и уже настроенный. Забегая вперед: на втором месяце обучения ты создашь свой собственный сервер и научишься его администрировать. 

Сразу после подключения тебе нужно изменить дефолтный пароль, это требование безопасности. На самом деле вход по паролю небезопасный, нужно ходить на сервер по ssh-ключу, но мы научимся этому через три недели, когда будем создавать свой сервер. Пока по паролю. И не забудь его сменить, потому что он **сгорит через три дня и ты не сможешь зайти на сервер и выполнить задание.** 

Это практический урок: выполняй все, о чем читаешь, самостоятельно. Экспериментируй. 

## Командный интерфейс

Разработка программ — сложный процесс, он включает в себя не только написание кода. Написанный код нужно как-то запускать, где-то хранить. Первое, с чем ты сталкиваешься, когда начинаешь программировать, и то, к чему нужно привыкать сразу — это командная строка. Командная строка — это интерфейс взаимодействия с операционной системой и другими программами. Обычно он выглядит как черное окошко с белыми буквами:

![](/img/emtpy_bash.png)

Тебе хорошо знаком другой интерфейс взаимодействия — графический. В данный момент он у тебя перед глазами. Этот способ взаимодействия идеально подходит для рядовых пользователей — тут есть привычные окошки, которые можно перемещать по экрану или сворачивать, файлы и папки в виде картинок, всё это делает выполнение пользовательских задач интуитивно простым. 

Командный интерфейс взаимодействия работает иначе. В командном интерфейсе ты печатаешь команду, нажимаешь Enter, система выполняет эту команду, пишет на экран результат выполнения и ждёт следующей команды.  Это называется REPL (**R**ead **E**val **P**rint **L**oop, англ. "Цикл Прочитать, Выполнить, Распечатать"). 

[![asciicast](https://asciinema.org/a/3y4XQ3RR8GD9u1Cj4W0QGPUdX.svg)](https://asciinema.org/a/3y4XQ3RR8GD9u1Cj4W0QGPUdX)

Предположим, ты хочешь удалить файл *diplom.txt* из привычного графического интерфейса. Ты переходишь в ту папку, где он находится, наводишь на него курсор и перетаскиваешь свой *diplom.txt* мышкой на значок корзины, после чего опустошаешь корзину. Чтобы сделать то же самое в командном интерфейсе, тебе достаточно лишь набрать `rm diplom.txt` (rm — это команда для удаления файла, от слова **r**e**m**ove) и нажать Enter.

Сначала может показаться, что взаимодействовать с системой таким способом ужасно неудобно, но это только на первый взгляд. На самом деле всё наоборот. Основные преимущества командного интерфейса перед графическим:

- Скорость работы возрастает на порядок.
- Набор команд можно записывать в файлы, то есть писать скрипты (сценарии) и потом запускать. Это позволяет решать сложные задачи, которые в графическом интерфейсе не получится решить в принципе. А также автоматизировать какие-то действия.
- Ты лучше понимаешь все происходящие в системе процессы и можешь их контролировать, потому что работаешь с системой напрямую, а не через "прослойку" в виде графической оболочки. Это открывает практически неограниченные возможности в работе, которые недоступны в графическом интерфейсе.
- Возможность подключаться к компьютеру, который расположен где-то очень далеко и выполнять на нём команды. То есть работать с удалённым сервером. На удалённых серверах не бывает графического интерфейса и взаимодействовать с другими компьютерами можно только посредством команд.

Командный интерфейс состоит из командной оболочки и терминала, терминал запускает командную оболочку в графической среде.

**Командная оболочка** (shell) — это программа, передающая твои команды на выполнение системе, тот самый REPL, про который было написано выше. Самая популярная командная оболочка — **bash**, она используется по умолчанию в таких операционных системах, как Linux и MacOS. Существует множество других командных оболочек (например, в операционной системе Windows используется какая-то своя, а на FreeBSD используется tcsh), но именно bash можно назвать стандартом из-за доминирования Линукса на серверах.

Для запуска командной оболочки внутри графического интерфейса потребуется **терминал** — это то самое окошко, внутри которого будет запущен Баш. Терминалов тоже бывает много и они отличаются всякими дополнительными возможностями — можно изменять шрифт, создавать вкладки и прочее. 

Итак, у нас есть Терминал — это программа, которая запускает командную оболочку (обычно Баш) в графическом интерфейсе твоей системы. Если у системы нет графического интерфейса, то и в терминале нужды нет. Для простоты далее в курсе мы будем пользоваться термином Баш, подразумевая под этим окно терминала с запущенным Башем. Он позволяет взаимодействовать с операционной системой с помощью команд. Такой метод взаимодействия очень эффективный и иногда единственно возможный. Команды можно группировать в сценарии, скрипты. 

Наверное, тебе уже не терпится выполнить свои первые команды? Давай приступим к практике.

## Запуск Баша в терминале

Если у тебя Мак или на твоем компьютере установлена операционная система Линукс, то просто запусти программу Терминал (Terminal), она так и называется. Перед тобой появится Баш.

Если Винда, то стандартный вариант для всех — поставить [Git Bash](https://gitforwindows.org). Это эмулятор Баша. Разберешься с установкой? Если нет, пиши в чат. 

Если у тебя Windows 10 и ты знаешь толк в извращениях, то можешь интегрировать Linux в свою Винду из Microsoft Store. Держи инструкцию: [https://docs.microsoft.com/ru-ru/windows/wsl/install-win10](https://docs.microsoft.com/ru-ru/windows/wsl/install-win10) 

В любом случае, после выполнения вышеперечисленных действий перед твоими глазами должен быть либо полноценный Баш, либо его эмулятор. Напечатай команду `whoami`и нажми Enter. На экране появится твое имя пользователя. Чтобы завершить работу напечатай команду `exit` или просто закрой терминал.

Теперь можно переходить к следующей теме. Если у тебя не получилось выполнить команду `whoami`, то вернись назад и попробуй понять, что ты сделал не так. Если не помогло, то **пиши в чат**.

## Перемещение по директориям

Вспомни, как открывать и закрывать терминал. 

Сейчас ты начнешь выполнять первые команды. Очень важно выполнять все команды самостоятельно, а не просто читать текст. Только так можно чему-то научиться. 

Символ `$` разделяет служебную информацию слева (имя пользователя, текущая директория) и ввод твоих команд справа.

После запуска графической оболочки ты попадаешь на так называемый Рабочий стол, это точка входа по умолчанию. В командной оболочке ты тоже всегда где-то находишься. Точкой входа для новой сессии является домашняя директория (*home directory*), и обычно она соответствует текущему имени пользователя, а то место, где ты находишься сейчас — рабочей директорией (*working directory*). 

Файловая система Unix отличается от файловой системы Windows. Она имеет древовидную структуру, в основе которой лежит корневой каталог — `/` (этот символ называется *слэш)*. Домашняя директория, например, лежит на два уровня ниже корневой: `/home/username`

Где ты находишься? Ты всегда где-то находишься, чтобы это узнать, есть команда `pwd`:

```bash
pwd 
# print working directory — напечатать текущую директорию
```

Всё, что идёт после символа решетки (#) игнорируется Башем, мы будем использовать это для комментариев. 

Чтобы перейти в другую директорию, используй комнду `cd`:

```bash
cd <путь до директории>
# change directory — сменить директорию
```

Пути бывают абсолютными и относительными.

Абсолютный — идёт от корня и является постоянным, например `/home/username`

Относительный — идёт от той директории, в который ты находишься. Этот путь не постоянный, а зависит от текущий директории. 

Существует короткая запись некоторых наиболее часть используемых директорий:

`.` ссылка на текущую директорию

`..` ссылка на родительскую директорию (ту, которая находится на уровень выше). То есть `cd ..` поднимет тебя на уровень выше по дереву каталогов. Попробуй выполнить эту команду и посмотри что получится. Не забывай смотреть свое местоположение с помощью `pwd`

`~` (тильда) — ссылка на домашнюю директорию. У каждого пользователя по умолчанию есть домашняя директория. Она находится в `/home/<имя пользователя>`(на Линуксе) или `/Users/<имя пользователя>` (на Маке). Тильда ссылается на эту директорию. Чтобы вернуться в домашнюю директорию, просто набери `cd ~`

Для просмотра содержимого директории используй команду `ls`:

```bash
ls
# показать содержимое директории
```

С помощью команды `man` ты можешь прочесть о том, что делает каждая команда, передав ей имя команды в качестве аргумента:

```bash
man ls
# получить справку по команде ls
```

### Ключи

У команд бывают необязательные ключи (опции), которые можно активировать через символ дефиса (иногда у ключа есть полная запись, которая передается через двойной дефис). Например:

`ls` посмотреть, что содержится в текущей директории
`ls -a` (`—all`) ключ `-a` или `—all` показать **всё** (ключ назван от англ. all, "всё") содержимое, даже скрытые файлы (скрытые файлы начинаются с символа точки). Скрытые файлы обычно не нужно трогать, поэтому они скрытые
`ls -l` подробные данные про каждый файл
Ключи можно комбинировать, для этого их надо ставить вместе: `ls -lah` (соответствует вызову `ls -l -a -h`), попробуй понять, что делает ключ -h.
`ls` можно передавать директорию и смотреть что в ней: `ls ../somedirectory` покажет, что в директории `somedirectory`, которая находится на уровень выше, для этого не нужно переходить в неё

Узнай свою текущую директорию `pwd`. Переместись на директорию выше `cd ..`, проверь текущее местонахождение `pwd` и вернись обратно `cd <директория>`.

Перемещайся на уровень выше, пока не дойдешь до корневой директории, посмотри что там интересного с помощью команды `ls`. Если заблудишься, всегда можно вернуться домой с помощью `cd ~` (вернуться в домашнюю директорию). 

### Типы файлов и права доступа

В системах Unix всё есть файл и можно выделить 6 типов. В данный момент не нужно над этим заморачиваться, рассмотрим только два типа — файл и директория. 

У каждого файла и каталога есть владелец и права доступа. Набери команду `ls-l`:

```jsx
drwxrwxr-x 2 alex alex 4096 Oct  1 23:40 testdir
-rw-rw-r-- 1 alex alex    0 Oct  1 23:40 testfile
```

Здесь нас интересуют первые десять символов, которые есть у любого файла или директории: `-rw-rw-r--` Первый символ указывает на тип файла: `d` — это **d**irectory, директория. `-` (дефис) это просто файл. Далее идут девять символов, первая тройка который определяет права доступа для владельца файла, вторая тройка для группы владельца и третья для всех остальных. Владелец файла из примера выше у нас **alex**, его группа так же alex. Владелец файла — это обычно тот, кто файл создал. Так же домашняя директория и все что в ней входит во владение текущего пользователя. 

r означает **r**ead (чтение), w это **w**rite (запись), а x — e**x**ecute (выполнение). То есть, пользователь alex может открывать и изменять файл testfile, но не может его запускать. Все остальные пользователи могут только открывать, но не могут изменять. 

Изменить права доступа можно командой `chmod`:

```bash
chmod u=rwx,g=rw,o=rx file.txt
```

u — значит user (владелец), g — group, o — others (все остальные). r, w, x это чтение, запись и исполнение. Просто перечисляем, для кого мы даем какие права. Например, себе как владельцу максимальные права, а всем остальным ограниченные.

## Манипуляции с директориями и файлами

Окей, перемещаться по директориям научились, давай посмотрим, как выполнять над директориями какие-либо действия. Большинство команд работает и для файлов.

### Создать, удалить, скопировать, переместить

`mkdir` cоздать директорию, можно передавать несколько параметров. Например, команда `mkdir one two three`создаст сразу три директории с именами *one*, *two* и *three*

Команда `touch <имя файла>` создает файл. Если применить к существующему файлу, то обновится его время последнего изменения

`rm` удалить **пустую** директорию или файл. Чтобы удалить непустую директорию, добавь ключ -r (**r**екурсивно)

`cp file1 myfolder/file2` сделать копию файла `file1`и поместить в директорию `myfolder` под именем `file2`

`mv` переместить, работает так же, как и предыдущая команда, только вместо копии выполняет перенос файла. Если "перенести" файл в текущую директорию с новым именем, то файл просто переименуется: `mv old_filename new_filename`

### Вывести на экран

`cat` —  весь файл, `head` — верхняя часть, `tail` — нижняя часть

`cat file.txt` — вывести содержимое файла `file.txt`

`head -n 3` — вывести верхний кусочек файла (первые три строчки)

`head -c 10` — вывести первые 10 символов файла

`tail -n 3` — вывести конец файла (последние 3 строчки)

`tail -c 10` — вывести последние 10 символов

`echo <text>` — просто выводит на экран текст, который ты передаешь в качестве аргумента

### Комбинирование команд

Команды можно комбинировать и записывать в одну строку. 

`;` — независимо от результата предыдущей команды выполнить следующую

`&&` — то же самое, но с условием успешного выполнения предыдущей команды

Примеры: 

`mkdir myfolder && cd myfolder` команда создаст директорию myfolder и перейдёт в неё. Если директория уже существует, то ничего не будет выполнено

`mkdir myfolder; cd myfolder` команда создаст директорию myfolder и перейдёт в неё. Если директория уже существует, то просто перейдет в неё

### Поиск по шаблону

`grep` — это поиск по шаблону

`grep 42 file` (найти упоминания числа 42 в файле `file`)

`grep 42 file -с` (вывести количество упоминаний "42" в файле `file`)

`grep -i привет file` (ignore case) будет искать привет в файле `file` без учета регистра ("привет", "Привет", "ПРИВЕТ", "пРиВеТ" и так далее)

### Перенаправление ввода-вывода

Символами стрелочек можно перенаправлять результат выполнения команды в файл:

```bash
echo Hi > greetings
# перенаправит Hi в файл greetings
# если файла не существует, то он создастся
# если файл существует, то он полностью перезапишется

date > current_datetime
# перенаправит текущую дату и время в файл current_datetime
# если файла не существует, то он создастся
# если файл существует, то он полностью перезапишется

echo Hi >> greetings
date >> current_datetime
# то же самое, но если файл существует, он не будет перезатираться
# результат просто дозапишется в конец
```

`>` перенаправление в файл, перезаписывает файл, если файла нет, то он будет создан

`>>` перенаправление в файл, добавляет в конец, если файла нет, то он будет создан

### Пайпы

Пайпом называется прямая черта `|`, с помощью которой можно строить команды по принципу конвейера — то есть, результат выполнения прошлой команды будет передаваться на вход следующей команде:

```bash
cat file | grep '#'
# передали содержимое файла file в grep, 
# который поискал в этом содержимом символ решетки

cat file | grep '#' | wc -l
# передали содержимое файла file в grep, 
# который поискал в этом содержимом символ решетки,
# и далее передали на подсчет команде wc (word count),
# чтобы посчитать количество слов с решеткой

cat file | grep '#' | wc -l > str_with_hash
# записали результат сразу в файл
```

Пайпы отлично демонстрируют базовые принципы Unix (так называемый «unix way» — одна программа (команда) делает что-то одно, но делает это хорошо, а текст выступает в качестве универсального интерфейса взаимодействия между такими программами (командами). 

В данном случае мы использовали команду `cat`, которая делает что-то одно и передает результат своей работы дальше, следующей команде, а потом еще дальше. При этом команды передают друг другу результат выполнения как обычный текст (текстовый интерфейс). 

### Консольные редакторы текста

Среди консольных редакторов можно выделить vi(m) и nano. Для знакомства мы рассмотрим nano, потому что он проще. И далее в курсе Нано будет дефолтным консольным редактором текста. Про него и поговорим.

Команда `nano` — запустить консольный редактор nano (привет, кэп!):

![](/img/nano.png)

Нано очень дружелюбный: внизу у него есть список горячих клавиш (значок `^` означает `Ctrl`). Попрактикуйся немного с ними, это понадобится для выполнения практического задания. 

`nano file` — открыть в редактое файл с именем `file`, если такой файл отсутствует, то он будет создан с пустым содержимым.

Чтобы сохранить, нажми *Ctrl+O*

Чтобы выйти, нажми *Ctrl+X*, **Yes**. Если файл был изменен, тебе предложат его сохранить. 

Вим (или его предшественник *vi*) не похож на Нано. Он очень сложный и мощный, но нужно потратить много времени, чтобы научиться им пользоваться. А предварительно освоить [слепой метод набора](https://ru.wikipedia.org/wiki/Слепой_метод_печати). Ещё существует emacs, про него можно сказать то же самое. 

## Полезности.

**Автозаполнение**. Начинай вводить имя файла и нажми Tab.

**История команд**. Стрелочками на клавиатуре можно возвращать уже выполненные команды, чтобы снова их не набирать. Попробуй понажимать стрелку вверх. История команд сохраняется в файле .bash_history и вызывается командой `history`

**Очистить экран.**  `Ctrl + l` или `clear`

## Дальнейшее изучение

Книга "Unix и Linux. Руководство системного администратора" (**5-е издание**)

## Практика

В качестве практического задания тебе предстоит подключиться к удалённому серверу, который расположен в Амстердаме, и выполнить на нём некоторые действия.

Напоминаю, что все практические задания должны быть зачтены до 23:59:59 субботы (GMT+3), иначе нам придется попрощаться. Чтобы этого не произошло, выполняй всё как можно раньше, не оставляй на потом.

Открой терминал. Подключись к удаленному серверу с помощью команды `ssh`:

```bash
ssh username@host
```

Замени `username` и `host` на значения, которые тебе отправили в Телеграме. Далее потребуется ввести пароль, не пугайся, что его символов не будет видно — это сделано для безопасности. Пароль ты так же найдешь в сообщении Телеграма.

При первом подключении к серверу появится примерно такое сообщение:

```bash
The authenticity of host cannot be established.
Are you sure you want to continue connecting? (yes/no)?
```

Набери `yes` и нажми *Enter*. 

Ты на сервере, можешь выполнять задания. 

Если станет скучно и одиноко в процессе выполнения, можно развлечься следующими командами:
`w` (`who`) посмотреть кто сейчас подключен к серверу
`write <username>` написать сообщение, заменив `<username>` на имя пользователя, который сейчас онлайн. Чтобы закончить, нажми **Ctrl+D**
`wall` написать сообщение всем, кто сейчас онлайн! Вводишь команду `wall`, жмешь *Enter*, пишешь послание, нажимаешь **Ctrl+D**. Отправлено.

## **Задание 1**

Задание для разогрева и проверки умения гуглить. Нужно изменить на удаленном сервере свой пароль по умолчанию (тот, который тебе прислали в телеграме). Твой дефолтный пароль **сгорит через три дня**, поэтому поспеши. Позаботься о том, чтобы пароль был сложным: на сервере орудует злоумышленник и если ему удастся сбрутфорсить твой пароль, то это может плохо закончиться ;)

## **Задание 2**

Измени права доступа своей домашней директории (и всего, что вложено), запрети любой доступ другим пользователям, чтобы никто не мог в неё зайти и стащить твою домашку. После того, как это сделаешь, можешь попытаться стащить у кого-нибудь домашку ;) 

## **Задание 3**

Убедись, что ты находишься в домашней директории. Там есть директория `a49e51672b547a9a`, где-то в её недрах потерялся один файл, твоя задача найти его и вернуть (переместить) домой (в домашнюю директорию). После этого удали все директории, должен остаться только файл. Чтобы не печатать эти сложные названия вручную, вспомни про автодополнение — введи пару первых символов и нажми *Tab*. 

## **Задание 4**

Посчитай количество вхождений смертельного заклинания в фанфик **Гарри Поттер и Методы Рационального Мышления** (файл `/home/hpmor.txt`) и сохрани это **число** в файл `hpmor_practice_count` в домашней директории. Также сохрани все **предложения**, по каждому на строку, в которых содержится смертельное заклинание, в файл `hpmor_practice_sentences` в домашней директории. 

## **Задание 5**

Считай переменную окружения `SECRET_ENV` и добавь её содержимое в файл с Задания 3. Мы это не проходили, поэтому найди информацию самостоятельно. 

## **Задание 6**

Создай в своем любимом текстовом редакторе файл `hi` и оставь любое послание автору курса, файл сохрани в домашней директории.