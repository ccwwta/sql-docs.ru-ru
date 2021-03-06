---
title: Вопросы и ответы по Azure Data Studio
description: Получите ответы на часто задаваемые вопросы об Azure Data Studio, например, о функциях, сценариях применения и стоимости.
ms.prod: azure-data-studio
ms.technology: azure-data-studio
ms.topic: conceptual
author: dzsquared
ms.author: drskwier
ms.reviewer: alayu, maghan
ms.custom: seodec18
ms.date: 10/28/2020
ms.openlocfilehash: 56d3f751fdae52fa0ff94aafe94d8ba955b418ec
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/10/2021
ms.locfileid: "100040194"
---
# <a name="azure-data-studio-faq"></a>Вопросы и ответы по Azure Data Studio

## <a name="what-is-azure-data-studio"></a>Что такое Azure Data Studio?

[Azure Data Studio](what-is-azure-data-studio.md) — это межплатформенная среда с открытым исходным кодом для специалистов по работе с данными, использующих семейство локальных и облачных платформ данных Майкрософт в Windows, MacOS и Linux. Выпущенный ранее под именем предварительной версии SQL Operations Studio инструмент Azure Data Studio предлагает современный редактор со сверхбыстрой технологией IntelliSense, а также возможности использования фрагментов кода, интеграции системы управления версиями и интегрированного терминала. Он создан с учетом потребностей пользователей платформы данных и включает в себя встроенную возможность построения диаграмм на основе результирующих наборов запросов и настраиваемые панели мониторинга.

Как показывают исследования, пользователи тратят на порядок больше времени на редактирование запросов, чем на выполнение любых других задач в SQL Server Management Studio. По этой причине при разработке Azure Data Studio основное внимание уделялось наиболее востребованным возможностям, а дополнительные функции были реализованы в виде необязательных расширений для продукта. Благодаря этому пользователи могут настраивать свою среду на основе наиболее часто используемых рабочих процессов.

## <a name="how-much-does-azure-data-studio-cost"></a>Сколько стоит Azure Data Studio?

Azure Data Studio предоставляется бесплатно для частного или коммерческого использования.

## <a name="who-should-use-azure-data-studio"></a>Кто может использовать Azure Data Studio?

Azure Data Studio — это инструмент для всех. Тем не менее он предназначен для оптимизации задач, выполняемых разработчиками и администраторами баз данных, системными администраторами и независимыми поставщиками программного обеспечения.

## <a name="what-can-i-do-with-azure-data-studio"></a>Какие возможности дает Azure Data Studio?

Azure Data Studio базируется на основе Visual Studio Code и предоставляет упрощенный современный интерфейс для создания кода с акцентом на использование клавиатуры при работе с SQL Server, базой данных SQL Azure и Azure Synapse Analytics. Azure Data Studio упрощает выполнение повседневных задач благодаря таким встроенным функциям, как несколько окон вкладок, полнофункциональный редактор SQL, технология IntelliSense, завершение ключевых слов, фрагменты кода, навигация по коду и интеграция системы управления версиями (Git и TFS). Вы можете выполнять запросы по требованию, просматривать и сохранять результаты в виде текстовых файлов, файлов JSON или Excel, редактировать данные, упорядочивать избранные подключения к базам данных и управлять ими, а также просматривать объекты базы данных, используя привычный интерфейс обозревателя объектов.

Используйте популярные программы и средства командной строки (например, Bash, PowerShell, sqlcmd, bcp, psql и SSH) в окне встроенного терминала непосредственно в пользовательском интерфейсе Azure Data Studio. Вы можете с легкостью генерировать и выполнять сценарии CREATE и INSERT для объектов базы данных, что позволяет создавать копии базы данных для разработки или тестирования. Поддержка интеллектуальных фрагментов кода с полнофункциональным графическим интерфейсом для создания новых баз данных и их объектов (таблиц, представлений, хранимых процедур, пользователей, имен входа, ролей и т. д.), а также для обновления существующих объектов баз данных, позволяет заметно повысить эффективность вашей работы. Используйте многофункциональные настраиваемые панели мониторинга для отслеживания и быстрого устранения проблем, препятствующих высокой производительности баз данных, размещаемых локально, в среде Azure или в облаке.

Azure Data Studio предлагает оптимизированную среду для резервного копирования и восстановления баз данных. Благодаря плановой поддержке групп доступности Always On SQL Server вы сможете с легкостью настраивать группы доступности для критически важных баз данных SQL Server, отслеживать их состояние, устранять связанные с ними неполадки, а в случае аварии моментально выполнять отработку отказа в базу данных-получатель. Инструмент Azure Data Studio разработан для повышения производительности в рамках жизненного цикла DevOps ваших баз данных, независимо от их вида и используемой операционной системы. Таким образом, вы получаете полный контроль над ситуацией, возможность снизить риски и ускорить процесс решения проблем, а также сможете на постоянной основе обеспечить уровень обслуживания, превосходящий ожидания ваших клиентов.

## <a name="is-azure-data-studio-open-source"></a>Является ли Azure Data Studio проектом с открытым исходным кодом?

Исходный код Azure Data Studio и используемых поставщиков данных доступен на сайте GitHub. Исходный код внешнего интерфейса [Azure Data Studio](https://github.com/microsoft/azuredatastudio), который базируется на основе Visual Studio Code, доступен на условиях лицензионного соглашения в отношении исходного кода. Это соглашение предоставляет права на изменение и использование программного обеспечения, но не на его распространение или размещение в облачной службе. Исходный код поставщиков данных предоставляется на условиях лицензии MIT на странице [https://github.com/Microsoft/sqltoolsservice](https://github.com/Microsoft/sqltoolsservice).

## <a name="do-we-plan-to-open-source-ssms"></a>Планируется ли предоставить открытый доступ к исходному коду SSMS?

Нет.

Тем не менее интерфейс командной строки и средства графического пользовательского интерфейса следующего поколения, поддерживающие несколько операционных систем, имеют открытый исходный код. Например, расширение mssql для VS Code, mssql-scripter и msql-CLI имеют открытый исходный код и доступны на сайте GitHub. Исходный код Azure Data Studio данных доступен на сайте GitHub.  

## <a name="now-that-theres-azure-data-studio-does-microsoft-plan-to-deprecate-ssms-and-ssdt"></a>Планирует ли корпорация Майкрософт вывод из обращения SSMS и SSDT после выпуска Azure Data Studio? 

Нет.

Помимо интерфейса командной строки и средств графического пользовательского интерфейса следующего поколения, поддерживающих несколько операционных систем и баз данных, мы продолжим работу над флагманскими средствами для Windows (SSMS, SSDT, PowerShell). Мы ставим перед собой задачу обеспечить клиентам возможность использовать в своих сценариях любые средства на любых платформах. Инструмент Azure Data Studio ориентирован в первую очередь на оптимизацию задач, связанных с редактированием запросов и разработкой данных, которые, как показывают исследования, являются одним из наиболее трудоемких направлений работы с SQL Server Management Studio. Дополнительные полезные возможности, такие как резервное копирование, восстановление, управление заданиями агента и профилирование сервера, в Azure Data Studio реализуются на основе расширений. Благодаря кроссплатформенной архитектуре пользователи могут выбирать предпочитаемую платформу для работы с Azure Data Studio. Тем не менее SQL Server Management Studio по-прежнему предлагает наиболее широкий диапазон функций администрирования и остается флагманским решением для выполнения задач по управлению платформой. 

## <a name="when-should-i-use-azure-data-studio-or-sql-server-management-studio"></a>Когда следует использовать Azure Data Studio или SQL Server Management Studio?

*Используйте Azure Data Studio, если вы...*

- в основном редактируете или выполняете запросы;
- хотите быстро создавать диаграммы и визуализировать результирующие наборы;
- можете выполнять большинство задач администрирования через встроенный терминал с помощью sqlcmd или PowerShell;
- имеете незначительную потребность в использовании мастера;
- не будете выполнять детализированную административную конфигурацию;
- работаете в macOS или Linux.

*Используйте SQL Server Management Studio, если вы...*

- выполняете сложную настройку административных функций или платформы;
- управляете вопросами безопасности, включая управление пользователями, оценку уязвимостей и настройку функций безопасности;
- будете использовать помощники по настройке производительности и панели мониторинга;
- используете конструкторы таблиц и диаграмм баз данных;
- должны получать доступ к зарегистрированным серверам;
- используете динамическую статистику запросов или статистику клиента.

## <a name="feature-comparison"></a>Сравнение возможностей

Дополнительные сведения о различиях между Azure Data Studio и SQL Server Management Studio (SSMS) см. в разделе [Что такое Azure Data Studio](what-is-azure-data-studio.md#feature-comparison-with-sql-server-management-studio-ssms).


## <a name="what-if-azure-data-studio-is-missing-a-feature-that-is-in-ssmsssdt"></a>Что делать, если в Azure Data Studio отсутствуют некоторые возможности, реализованные в SSMS/SSDT?

Все зависит от конкретных сценариев, а также потребностей клиентов и бизнеса. Чтобы помочь в назначении приоритетов, предоставьте предложение и проголосуйте за существующее на [GitHub](https://github.com/microsoft/azuredatastudio/issues).

## <a name="i-understand-azure-data-studio-and-the-mssql-extension-for-vs-code-are-powered-by-a-new-tools-service-that-uses-smo-apis-under-the-covers-is-smo-available-on-linux-and-macos"></a>Azure Data Studio и расширение mssql для VS Code базируются на основе новой службы средств, которая использует API управляющих объектов SQL Server. Будут ли управляющие объекты SQL Server доступны для Linux и macOS?

API управляющих объектов SQL Server на данный момент недоступны для Linux или macOS. Мы перенесли в .NET Core некоторые API управляющих объектов SQL Server, которые используются в Azure Data Studio, и в дальнейшем планируем увеличить их количество. Служба средств SQL на сайте GitHub: [https://github.com/Microsoft/sqltoolsservice](https://github.com/Microsoft/sqltoolsservice).

## <a name="do-you-plan-to-port-the-dacfx-apis-andor-sqlpackageexe-andor-ssdt-to-linux-and-macos"></a>Планируете ли вы переносить API DACFx и (или) sqlpackage.exe и (или) SSDT в Linux и macOS?

Да.

[SqlPackage. exe](../tools/sqlpackage/sqlpackage-download.md) теперь доступен в .NET Core для Windows, macOS и Linux.  Функциональные возможности проектов SQL (SSDT) включены в Azure Data Studio в [расширении проектов базы данных SQL](extensions/sql-database-project-extension.md).

## <a name="will-sql-powershell-cmdlets-be-available-on-linux-and-macos"></a>Будут ли командлеты PowerShell SQL доступны в Linux и macOS?

Командлеты PowerShell SQL на данный момент представлены в коллекции PowerShell и могут использоваться в Windows для работы с любыми экземплярами SQL Server, включая SQL на Linux. Реализация командлетов SQL PowerShell для Linux и macOS также находится в наших планах. Чтобы помочь нам в расстановке приоритетов, направьте свое предложение через сайт [GitHub](https://github.com/microsoft/azuredatastudio/issues).

## <a name="who-usually-uses-azure-data-studio"></a>Кто обычно использует Azure Data Studio?

Основными пользователями Azure Data Studio являются разработчики и администраторы баз данных.

## <a name="does-azure-data-studio-integrate-with-azure-synapse-analytics"></a>Интегрируется ли Azure Data Studio с Azure Synapse Analytics?

Да.

Поддержка Azure Synapse Analytics в Azure Data Studio в настоящее время реализована в виде предварительной версии, так же как для Управляемого экземпляра SQL Azure и больших данных SQL Server 2019.

## <a name="why-is-azure-data-studio-important-for-big-data-scenarios"></a>Почему Azure Data Studio важен для сценариев с большими данными?

По мере расширения возможностей SQL Server в области больших данных возникает потребность в новых средствах, обеспечивающих работу в подобных сценариях. Поэтому в Azure Data Studio сейчас реализована новая функция для поддержки больших данных SQL Server. Помимо прочего, сюда входит интерфейс для работы с записными книжками в наборе инструментов SQL Server, а также новый мастер создания внешней таблицы, который значительно упрощает и оптимизирует доступ к данным на удаленных экземплярах SQL Server и Oracle.

## <a name="can-i-use-visual-studio-code-vs-code-extensions-with-azure-data-studio"></a>Можно ли использовать расширения Visual Studio Code (VS Code) с Azure Data Studio?

Да.

Однако не все расширения VS Code преобразуются в Azure Data Studio.

## <a name="next-steps"></a>Next Steps
- [Что такое Azure Data Studio](what-is-azure-data-studio.md)
- [Скачать Azure Data Studio](download-azure-data-studio.md)