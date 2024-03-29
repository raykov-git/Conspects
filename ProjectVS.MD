# Проект VS

## Проекты

При создании в Visual Studio приложения или веб-сайта вы начинаете с проекта.
С логической точки зрения проект содержит все файлы,
которые будут скомпилированы в исполняемую программу,
библиотеку или веб-сайт. Сюда входят файлы с исходным кодом, значками, изображениями, данными и т. д.
Проект также содержит параметры компилятора и другие файлы конфигурации, которые могут потребоваться разным службам или компонентам,
с которыми взаимодействует программа.

## Файл проекта

Visual Studio использует MSBuild для создания каждого проекта в решении, и каждый проект содержит файл проекта MSBuild.
Расширение имени файла отражает тип проекта, например проект C# (CSPROJ), проект Visual Basic (VBPROJ) или проект базы данных (DBPROJ).
Файл проекта представляет собой XML-документ, который содержит все сведения и инструкции,
необходимые MSBuild для сборки проекта, включая содержимое, требования к платформе, сведения об управлении версиями,
параметры веб-сервера или сервера баз данных, а также выполняемые задачи.

Файлы проекта основаны на схеме XML MSBuild.
Чтобы просмотреть содержимое файлов проекта в новом стиле SDK в Visual Studio,
щелкните правой кнопкой мыши узел проекта в обозревателе решений и выберите пункт Изменить <projectname>.
Чтобы просмотреть содержимое проекта .NET Framework или другого проекта в этом стиле,
сначала выгрузите проект (щелкните правой кнопкой мыши узел проекта в обозревателе решений и выберите пункт Выгрузить проект).
Затем щелкните проект правой кнопкой мыши и выберите пункт Изменить <projectname> .

## Создать новые проекты

Самый простой способ создать новый проект — использовать шаблон проекта с нужным типом проекта.
Шаблон проекта — это базовый набор предварительно созданных файлов кода, файлов конфигурации, активов и параметров.
Для выбора шаблона проекта нажмите Файл > Создать > Проект. Дополнительные сведения см. в разделе Создание нового проекта.

Вы можете также создать пользовательский шаблон проекта, чтобы затем использовать его для создания новых проектов.
Дополнительные сведения см. в статье Создание шаблонов проектов и элементов.

При создании нового проекта Visual Studio сохраняет его в расположении по умолчанию — %USERPROFILE%\source\repos.
Чтобы изменить это расположение, перейдите в раздел Средства > Параметры > Проекты и решения > Расположения.
Дополнительные сведения см. в диалоговом окне параметров в разделе "Проекты и решения" > "Расположения".

## Решения

Проект находится внутри решения. Несмотря на название, под решением не подразумевается "решение вопроса".
Это просто контейнер для одного или нескольких связанных проектов вместе с информацией о сборке,
параметрами окна Visual Studio и любыми прочими файлами, которые не относятся к какому-либо конкретному проекту.

## Файл решения

В Visual Studio используются два типа файлов (SLN и SUO) для хранения параметров, связанных с решениями:

Расширение	             name	                                 Описание
.SLN	                   Решение Visual Studio	               Организует проекты, элементы проектов и решений в решении.
SUO	                     Параметры пользователя решения	       Сохраняет настройки и параметры уровня пользователя, например точки останова.

## Папка решения

Папка решения — это виртуальная папка, которая доступна только в Обозревателе решений,
где с ее помощью можно группировать проекты в решении. Если нужно найти файл решения на компьютере,
перейдите к разделу Средства > Параметры > Проекты и решения > Расположения.

## Обозреватель решений

После создания проекта можно просматривать проект, решение и связанные с ними элементы, а также для управлять ими с помощью обозревателя решений.
На следующем рисунке показан обозреватель решений с решением C#, включающим два проекта:

Снимок экрана: Обозреватель решений с двумя проектами в Visual Studio

![alt text](https://docs.microsoft.com/ru-ru/visualstudio/ide/media/solution-explorer.png?view=vs-2019)

На панели инструментов в верхней части Обозревателя решений есть кнопки для переключения из представления решения в представление папки,
фильтрации ожидающих изменений, отображения всех файлов, свертывания всех узлов, просмотра страниц свойств, просмотра кода в редакторе кода и т. д.

Многие команды меню доступны в контекстном меню различных элементов в Обозревателе решений.
К таким командам относится сборка проекта, управление пакетами NuGet, добавление ссылок, переименование файла и запуск тестов.
Это лишь некоторые из них.

В обозревателе решений можно настроить способ вложения файлов для проектов ASP.NET Core.

инсточник: https://docs.microsoft.com/ru-ru/visualstudio/ide/solutions-and-projects-in-visual-studio?view=vs-2019
