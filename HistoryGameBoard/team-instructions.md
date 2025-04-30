Інструкція для роботи над проєктом HistoryGameBoard
Ця інструкція допоможе вам розпочати та постійно працювати над проєктом HistoryGameBoard на GitHub. Проєкт — це настільна історична гра на Windows Forms (C#) із .NET Framework 4.7.2, сумісна з Visual Studio 2017, 2019 і 2022 (Community, Professional, Enterprise). У команді різні ролі: хтось працює над дизайном (UI, форми), хтось над кодом (логіка), хтось над ресурсами (зображення, тексти) або тестуванням. Інструкція охоплює початкове налаштування та щоденні задачі, включаючи внесення змін, коміти, гілки, Pull Requests і вирішення конфліктів. Для команд Git указані підказки, де їх вводити, щоб було зрозуміло навіть при копіюванні в месенджер (наприклад, Discord, Telegram).

1. Початкове налаштування: Встановіть необхідне програмне забезпечення

Visual Studio:
Завантажте з visualstudio.microsoft.com.
Рекомендується Visual Studio 2019 або 2022 (Community — безкоштовна). Visual Studio 2017 також підійде.
Під час встановлення виберіть Desktop development with C#.
Переконайтеся, що встановлено .NET Framework 4.7.2:
У Visual Studio: Tools > Get Tools and Features > виберіть .NET Framework 4.7.2.


Перевірте версію: Help > About Microsoft Visual Studio (наприклад, "Community 2022").


Git:
Завантажте з git-scm.com, встановіть (налаштування за замовчуванням).
Перевірте встановлення:
Відкрийте Командний рядок (Win+R, введіть cmd).
Введіть у командному рядку:git --version

Має з’явитися, наприклад, git version 2.41.0.


Налаштуйте Git (один раз):
Введіть у командному рядку:git config --global user.name "Ваше Ім’я"
git config --global user.email "ваш.email@example.com"

Наприклад:git config --global user.name "Олег"
git config --global user.email "oleg@example.com"






GitHub акаунт:
Зареєструйтеся на github.com.
Надішліть свій GitHub-нік лідеру проєкту (наприклад, VadymStudio) для доступу до https://github.com/VadymStudio/HistoryGameBoard.




2. Початкове налаштування: Склонуйте проєкт

Скопіюйте URL репозиторію:
URL: https://github.com/VadymStudio/HistoryGameBoard.git.


Склонуйте репозиторій:
Відкрийте Командний рядок (Win+R, введіть cmd) або термінал у Visual Studio (View > Terminal).
Перейдіть у папку для проєктів:
Введіть у командному рядку або терміналі Visual Studio:cd C:\Projects




Склонуйте:
Введіть у командному рядку або терміналі Visual Studio:git clone https://github.com/VadymStudio/HistoryGameBoard.git


Створиться папка C:\Projects\HistoryGameBoard.




Відкрийте проєкт:
У Visual Studio: File > Open > Project/Solution > виберіть C:\Projects\HistoryGameBoard\HistoryGameBoard.sln.
Якщо .sln не відкривається (наприклад, у Visual Studio 2017):
Створіть новий:
У Visual Studio: File > New > Project > Blank Solution (пошук: "Blank Solution").
Правою кнопкою миші на рішення > Add > Existing Project > виберіть C:\Projects\HistoryGameBoard\HistoryGameBoard\HistoryGameBoard.csproj.


Збережіть і додайте до Git:
Відкрийте термінал у Visual Studio (View > Terminal).
Введіть:cd C:\Projects\HistoryGameBoard
git add HistoryGameBoard.sln
git commit -m "Structure: Додано .sln для Visual Studio 2017"
git push origin feature/add-solution








Перевірте запуск:
Натисніть F5 у Visual Studio. Якщо є помилки, перевірте .NET Framework 4.7.2.


Відновіть NuGet пакети:
У Visual Studio: Tools > NuGet Package Manager > Manage NuGet Packages for Solution > Restore.




3. Постійна робота: Як працювати над задачею

Отримайте задачу:
Перегляньте Issues на GitHub (https://github.com/VadymStudio/HistoryGameBoard/issues).
Виберіть задачу залежно від вашої ролі:
Дизайн: "Створити форму ігрової дошки".
Код: "Реалізувати логіку гравця".
Ресурси: "Додати зображення для дошки".
Тестування: "Перевірити форму логіну".


Попросіть лідера призначити задачу, якщо неясно.


Оновіть гілку main (обов’язково перед кожною новою задачею):
Відкрийте термінал у Visual Studio (View > Terminal) або командний рядок (Win+R, введіть cmd).
Перейдіть до папки проєкту:
Введіть:cd C:\Projects\HistoryGameBoard




Оновіть:
Введіть у терміналі Visual Studio або командному рядку:git checkout main
git pull origin main




Або в Visual Studio: Git Changes > виберіть main > Pull.


Створіть свою гілку:
Назва гілки залежить від ролі та задачі:
Дизайн: feature/ui-game-board.
Код: feature/player-logic.
Ресурси: feature/add-images.
Тестування: feature/test-login.
Виправлення помилок: bugfix/image-display.


Введіть у терміналі Visual Studio або командному рядку:git checkout -b feature/ui-game-board


Або в Visual Studio: Git Changes > New Branch > введіть feature/ui-game-board > Create.




4. Постійна робота: Створюйте та комітьте зміни залежно від вашої ролі
Ось як вносити зміни, комітити їх і уникати конфліктів. Інструкції поділені за ролями, із чіткими вказівками, де вводити команди.
4.1. Для дизайнера (UI, форми)

Що робите:
Створюєте або редагуєте форми (наприклад, додаєте кнопки, текстові поля, графіку).
Працюєте з файлами .cs, .Designer.cs, .resx, зазвичай у папці Forms.


Як працювати:
Відкрийте проєкт у Visual Studio (C:\Projects\HistoryGameBoard\HistoryGameBoard.sln).
Додайте або редагуйте форму:
У Solution Explorer клацніть правою кнопкою миші на папку Forms > Add > Windows Form > назвіть, наприклад, GameBoardForm.
У дизайнері форм додайте елементи (кнопки, зображення, текст).
Збережіть (Ctrl+S).


Перевірте:
Натисніть F5, щоб запустити і перевірити форму.
Переконайтеся, що дизайн виглядає коректно на різних роздільних здатностях.


Додайте зміни до Git:
Відкрийте термінал у Visual Studio (View > Terminal) або командний рядок (Win+R, введіть cmd).
Перейдіть до папки проєкту:
Введіть:cd C:\Projects\HistoryGameBoard




Перегляньте зміни:
Введіть у терміналі Visual Studio або командному рядку:git status



Побачите файли, наприклад:
Forms/GameBoardForm.cs
Forms/GameBoardForm.Designer.cs
Forms/GameBoardForm.resx


Додайте файли:
Введіть:git add .




Або в Visual Studio:
У Git Changes побачите файли (GameBoardForm.cs тощо).
Виберіть усі файли для коміту.




Створіть коміт:
Введіть у терміналі Visual Studio або командному рядку:git commit -m "UI: Додано форму GameBoardForm із кнопками і графікою"


Або в Visual Studio:
У Git Changes введіть повідомлення: "UI: Додано форму GameBoardForm із кнопками і графікою".
Натисніть Commit All.




Відправте на GitHub:
Введіть у терміналі Visual Studio або командному рядку:git push origin feature/ui-game-board


Або в Visual Studio: Git Changes > Push.




Поради:
Уникайте редагування коду логіки в .cs (залишайте це розробникам).
Попереджайте команду про нові форми, щоб уникнути конфліктів у .csproj.
Перевіряйте дизайн на різних розмірах екрану.



4.2. Для розробника коду (логіка, класи)

Що робите:
Пишете логіку гри (класи, методи, обробники подій).
Працюєте з файлами .cs у папці Classes (наприклад, Player.cs) або Forms (обробники подій).


Як працювати:
Відкрийте проєкт у Visual Studio.
Створіть або редагуйте код:
Додайте клас: у Solution Explorer клацніть правою кнопкою миші на папку Classes > Add > Class > назвіть, наприклад, Player.cs.
Напишіть код, наприклад:namespace HistoryGameBoard
{
    public class Player
    {
        public string Name { get; set; }
        public int Score { get; set; }

        public Player(string name)
        {
            Name = name;
            Score = 0;
        }
    }
}


Додайте логіку в Forms/GameBoardForm.cs (наприклад, обробник кнопки).
Збережіть (Ctrl+S).


Перевірте:
Натисніть F5, щоб протестувати логіку.
Додайте дебаг-точки (клацніть ліворуч від рядка коду > F9), якщо потрібно.


Додайте зміни до Git:
Відкрийте термінал у Visual Studio (View > Terminal) або командний рядок.
Перейдіть до папки:
Введіть:cd C:\Projects\HistoryGameBoard




Перегляньте зміни:
Введіть:git status



Побачите файли, наприклад:
Classes/Player.cs
Forms/GameBoardForm.cs


Додайте:
Введіть:git add .




Або в Visual Studio: у Git Changes виберіть файли.


Створіть коміт:
Введіть у терміналі Visual Studio або командному рядку:git commit -m "Code: Додано клас Player і логіку кнопки у GameBoardForm"


Або в Visual Studio:
У Git Changes введіть повідомлення: "Code: Додано клас Player і логіку кнопки у GameBoardForm".
Натисніть Commit All.




Відправте:
Введіть:git push origin feature/player-logic


Або в Visual Studio: Git Changes > Push.




Поради:
Уникайте редагування дизайну форм (.Designer.cs).
Пишіть чистий код із коментарями.
Тестуйте кожен метод окремо.



4.3. Для розробника ресурсів (зображення, тексти)

Що робите:
Додаєте файли: зображення (.png, .jpg), тексти (.txt), звуки.
Працюєте з папкою Resources або файлами .resx.


Як працювати:
Додайте ресурси:
У Visual Studio: у Solution Explorer клацніть правою кнопкою миші на проєкт > Add > New Folder > назвіть Resources (якщо немає).
Скопіюйте файли (наприклад, board.png) у C:\Projects\HistoryGameBoard\HistoryGameBoard\Resources.
Додайте до проєкту: у Solution Explorer клацніть правою кнопкою миші на Resources > Add > Existing Item > виберіть board.png.
Або додайте до .resx:
Відкрийте Forms/GameBoardForm.resx (подвійний клік у Solution Explorer).
Перетягніть board.png у вікно ресурсів.


Збережіть (Ctrl+S).


Перевірте:
У Forms/GameBoardForm.cs використайте ресурс, наприклад:pictureBox1.Image = Properties.Resources.board;


Запустіть (F5), перевірте відображення.


Додайте зміни до Git:
Відкрийте термінал у Visual Studio або командний рядок.
Перейдіть:
Введіть:cd C:\Projects\HistoryGameBoard




Перегляньте:
Введіть:git status



Побачите:
Resources/board.png
Forms/GameBoardForm.resx


Додайте:
Введіть:git add .




Або в Visual Studio: у Git Changes виберіть файли.


Створіть коміт:
Введіть:git commit -m "Resources: Додано зображення board.png для ігрової дошки"


Або в Visual Studio:
У Git Changes введіть: "Resources: Додано зображення board.png для ігрової дошки".
Натисніть Commit All.




Відправте:
Введіть:git push origin feature/add-images


Або в Visual Studio: Git Changes > Push.




Поради:
Оптимізовуйте зображення (не додавайте файли >10 МБ).
Використовуйте .resx для ресурсів, які потрібні в коді.
Попереджайте команду про нові файли.



4.4. Для тестувальника

Що робите:
Перевіряєте форми, логіку, ресурси.
Створюєте звіти про помилки в папці Tests.


Як працювати:
Запустіть проєкт:
У Visual Studio: F5.
Тестуйте функції (кнопки, введення даних, графіку).


Створіть звіт:
Створіть текстовий файл, наприклад, Tests/test-report.txt у C:\Projects\HistoryGameBoard\HistoryGameBoard\Tests.
Напишіть:Тест форми GameBoardForm:
- Кнопка "Старт" працює.
- Зображення дошки не відображається (помилка).


Збережіть.


Додайте зміни до Git:
Відкрийте термінал у Visual Studio або командний рядок.
Перейдіть:
Введіть:cd C:\Projects\HistoryGameBoard




Перегляньте:
Введіть:git status



Побачите:
Tests/test-report.txt


Додайте:
Введіть:git add .




Або в Visual Studio: у Git Changes виберіть файл.


Створіть коміт:
Введіть:git commit -m "Test: Додано звіт про тестування GameBoardForm"


Або в Visual Studio:
У Git Changes введіть: "Test: Додано звіт про тестування GameBoardForm".
Натисніть Commit All.




Відправте:
Введіть:git push origin feature/test-game-board


Або в Visual Studio: Git Changes > Push.




Поради:
Створюйте Issue на GitHub для кожної помилки:
Перейдіть: Issues > New issue.
Назва: "Зображення дошки не відображається".
Опишіть проблему, додайте скріншот.


Тестуйте на різних роздільних здатностях.



4.5. Створіть Pull Request

Перейдіть на GitHub:
Відкрийте https://github.com/VadymStudio/HistoryGameBoard.
Побачите повідомлення про вашу гілку (наприклад, feature/ui-game-board).


Створіть Pull Request:
Натисніть Compare & pull request.
Додайте назву та опис залежно від ролі:
Дизайн: "UI: Додано форму GameBoardForm із графікою".
Код: "Code: Додано клас Player і логіку".
Ресурси: "Resources: Додано зображення board.png".
Тестування: "Test: Додано звіт про тестування GameBoardForm".


Приклад опису:UI: Додано форму GameBoardForm із кнопками і графікою.
Перевірте, чи коректно відображається у .NET Framework 4.7.2.


Натисніть Create Pull Request.


Додайте рецензентів:
У Reviewers виберіть лідера (VadymStudio) або колег.


Виправте зауваження:
Якщо лідер залишив коментарі, редагуйте код/файли у Visual Studio.
Закомітьте виправлення:
Введіть у терміналі Visual Studio або командному рядку:cd C:\Projects\HistoryGameBoard
git add .
git commit -m "Fix: Виправлено зауваження до GameBoardForm"
git push origin feature/ui-game-board


Або в Visual Studio: Git Changes > введіть повідомлення > Commit All > Push.


Зміни оновляться у Pull Request.


Чекайте об’єднання:
Лідер об’єднає Pull Request у main.




5. Постійна робота: Після об’єднання Pull Request

Оновіть локальну гілку main:
Відкрийте термінал у Visual Studio (View > Terminal) або командний рядок.
Перейдіть до папки:
Введіть:cd C:\Projects\HistoryGameBoard




Оновіть:
Введіть:git checkout main
git pull origin main


Або в Visual Studio: Git Changes > виберіть main > Pull.




Видаліть використану гілку:
Локально:
Введіть:git branch -d feature/ui-game-board


Або в Visual Studio: Git Changes > Branches > клацніть правою кнопкою миші на гілку > Delete.


На GitHub: у Pull Request натисніть Delete branch.




6. Постійна робота: Уникнення конфліктів між ролями
Щоб уникнути конфліктів, коли кілька людей змінюють проєкт одночасно, дотримуйтесь цих правил:

Розподіл задач за ролями:
Дизайнер: редагує .Designer.cs, .resx у папці Forms.
Розробник коду: працює з .cs у Classes і логікою в Forms.
Розробник ресурсів: додає файли в Resources і оновлює .resx.
Тестувальник: створює звіти в Tests, не редагує код.
Домовляйтеся в чаті (Discord, Telegram), хто які файли редагує.


Оновлюйте main перед кожною задачею:
Завжди виконуйте:
Введіть у терміналі Visual Studio або командному рядку:cd C:\Projects\HistoryGameBoard
git checkout main
git pull origin main






Уникайте конфліктів у .csproj:
Якщо додаєте нові форми, класи чи ресурси, попереджайте команду, щоб один додавав за раз.
Якщо виник конфлікт у HistoryGameBoard.csproj:
Відкрийте файл у Visual Studio або текстовому редакторі.
Знайдіть позначки конфлікту, наприклад:<<<<<<< HEAD
<ItemGroup><Compile Include="Forms/GameBoardForm.cs" /></ItemGroup>
=======
<ItemGroup><Compile Include="Classes/Player.cs" /></ItemGroup>
>>>>>>> origin/feature/player-logic


Об’єднайте зміни:<ItemGroup>
  <Compile Include="Forms/GameBoardForm.cs" />
  <Compile Include="Classes/Player.cs" />
</ItemGroup>


Закомітьте:
Введіть:cd C:\Projects\HistoryGameBoard
git add HistoryGameBoard.csproj
git commit -m "Fix: Виправлено конфлікт у .csproj"
git push origin feature/ваша_гілка










7. Постійна робота: Переміщення файлів у папки
Проєкт організовано з папками Forms, Classes, Resources, Tests. Якщо потрібно перемістити файли (наприклад, Form1.cs у Forms), виконайте наступне, щоб уникнути помилок:

Закрийте Visual Studio:
Це запобігає конфліктам із відкритими файлами.


Перемістіть файли у файловій системі:
Відкрийте C:\Projects\HistoryGameBoard\HistoryGameBoard у Провіднику Windows.
Наприклад, для форми:
Знайдіть файли: Form1.cs, Form1.Designer.cs, Form1.resx.
Перемістіть їх у папку Forms (шлях: C:\Projects\HistoryGameBoard\HistoryGameBoard\Forms).


Для інших файлів:
Класи (наприклад, Player.cs) → Classes.
Зображення (наприклад, board.png) → Resources.
Звіти (наприклад, test-report.txt) → Tests.




Оновіть .csproj:
Відкрийте C:\Projects\HistoryGameBoard\HistoryGameBoard\HistoryGameBoard.csproj у текстовому редакторі (наприклад, Notepad).
Знайдіть рядки для переміщених файлів, наприклад:<Compile Include="Form1.cs" />
<Compile Include="Form1.Designer.cs" />
<EmbeddedResource Include="Form1.resx" />


Оновіть шляхи:<Compile Include="Forms\Form1.cs" />
<Compile Include="Forms\Form1.Designer.cs" />
<EmbeddedResource Include="Forms\Form1.resx" />


Для інших файлів:
Classes/Player.cs:<Compile Include="Classes\Player.cs" />


Resources/board.png:<Content Include="Resources\board.png" />


Tests/test-report.txt:<Content Include="Tests\test-report.txt" />




Збережіть файл.


Перевірте в Visual Studio:
Відкрийте HistoryGameBoard.sln.
У Solution Explorer перевірте, чи файли відображаються в папках.
Скомпілюйте (F5).
Якщо помилки, перевірте шляхи в .csproj.


Закомітьте зміни:
Відкрийте термінал у Visual Studio (View > Terminal).
Перейдіть:
Введіть:cd C:\Projects\HistoryGameBoard




Перегляньте:
Введіть:git status



Побачите, наприклад:
modified:   HistoryGameBoard.csproj
renamed:    Form1.cs -> Forms/Form1.cs


Додайте:
Введіть:git add .




Створіть коміт:
Введіть:git commit -m "Structure: Переміщено файли в папки Forms, Classes, Resources, Tests"




Відправте:
Введіть:git push origin feature/project-structure






Створіть Pull Request:
На GitHub (https://github.com/VadymStudio/HistoryGameBoard) створіть Pull Request для гілки feature/project-structure (див. пункт 4.5).




Поради:
Переміщуйте пов’язані файли (Form1.cs, Form1.Designer.cs, Form1.resx) разом.
Попереджайте команду про переміщення файлів у чаті.
Оновіть main після об’єднання Pull Request.




8. Постійна робота: Вирішення проблем
Якщо виникають проблеми під час роботи, ось як їх вирішити:

Проєкт не відкривається:
Перевірте .NET Framework 4.7.2:
У Visual Studio: Tools > Get Tools and Features > виберіть .NET Framework 4.7.2.


Якщо .sln не працює, створіть новий (див. пункт 2.3).


Помилка git push:
Виконайте:
Введіть у терміналі Visual Studio або командному рядку:cd C:\Projects\HistoryGameBoard
git pull origin main




Виправте конфлікти (див. пункт 6).
Повторіть:
Введіть:git push origin feature/ваша_гілка






NuGet пакети не відновлюються:
У Visual Studio: Tools > NuGet Package Manager > Manage NuGet Packages for Solution > Restore.


Помилки компіляції після переміщення файлів:
Перевірте HistoryGameBoard.csproj:
Відкрийте файл, знайдіть неправильні шляхи (наприклад, Form1.cs замість Forms\Form1.cs).
Виправте, збережіть.


Переконайтесь, що namespace у файлах не змінився (має бути HistoryGameBoard).
Скомпілюйте (F5).


Автентифікація на GitHub:
Якщо потрібен пароль:
Створіть Personal Access Token на GitHub (Settings > Developer settings > Personal access tokens > Generate new token).
Використовуйте токен як пароль під час git push.




Питання чи помилки:
Пишіть у чат (Discord, Telegram) або створіть Issue на GitHub із описом проблеми.




9. Постійна робота: Координація та поради

Координація в команді:
Використовуйте чат (Discord, Telegram) для обговорення:
Хто які файли редагує.
Нові форми чи ресурси.
Проблеми з Git чи Visual Studio.


Регулярно перевіряйте Issues і Pull Requests на GitHub.
Нагадуйте колегам оновлювати main перед створенням гілок.


Поради за ролями:
Дизайнер: Перевіряйте UI на різних екранах, не редагуйте логіку.
Розробник: Тестуйте методи, додавайте коментарі до коду.
Ресурси: Оптимізовуйте файли (зображення <10 МБ).
Тестувальник: Створюйте детальні звіти, додавайте скріншоти до Issues.


Гілки:
Використовуйте назви: feature/роль-назва (наприклад, feature/ui-login) або bugfix/назва (наприклад, bugfix/image-display).


Коміти:
Пишіть зрозумілі повідомлення, вказуйте роль: "UI: Додано форму", "Code: Виправлено логіку".


Оновлення:
Завжди оновлюйте main перед новою гілкою.


Документація:
Оновлюйте README.md із прогресом проєкту:
Додавайте розділ "Прогрес":## Прогрес
- Додано форму GameBoardForm.
- Реалізовано клас Player.


Закомітьте:
Введіть:cd C:\Projects\HistoryGameBoard
git add README.md
git commit -m "Docs: Оновлено README із прогресом"
git push origin main










10. Додаткові інструменти

GitHub Desktop: Завантажте з desktop.github.com для зручного керування Git.
Visual Studio Git: Використовуйте Git Changes для комітів і гілок.
Live Share: У Visual Studio (View > Live Share) для спільного редагування коду з колегами.


11. Структура проєкту
Проєкт організовано з папками для зручної роботи:

Forms: Містить форми (.cs, .Designer.cs, .resx), наприклад, GameBoardForm.cs.
Classes: Містить класи логіки, наприклад, Player.cs.
Resources: Містить зображення, тексти, звуки (наприклад, board.png).
Tests: Містить звіти тестувальників (наприклад, test-report.txt).

Якщо потрібно перемістити файли в ці папки, дотримуйтесь інструкцій у пункті 7.

