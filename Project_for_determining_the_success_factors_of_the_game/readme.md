## Исследование успешности видеоигр


### Описание

Заказчик — интернет-магазин, который продаёт по всему миру компьютерные игры. 
Исходные данные: исторические данные о продажах игр, оценки пользователей и экспертов, жанры и платформы. 
Цель исследования: выявить определяющие успешность игр факторы и закономерности. 


### Инструменты

pandas, numpy, matplotlib


### Выводы


 Первичный анализ произведен, обнаружены проблемы с типами данных в столбцах: year_of_release, users_scores и разнорегистрововые наименования, для корректной работы потребовалось привести столбцы к int32, float32 - типам, а наименования трансформировать в нижний регистр. В data sets имеются пропуски, как данные собирались из открытых источников. Пропуск в наименовании игры может означать невозвожность кодирования на латиницу исходного наименования, либо некоректная отработка сборщика. Отсутствие пользовательских отзывов и критиков. Отсутствие рейтинга или tbd означает не более чем, что издатель не захотел получать рейтинговую оценку ESRB или игра не планировалась выпускаться для региона NA.

   Подготовка данных к анализу произведена:
Строки с пропуском имени были удаленны, так же как и строки с пропуском жанра.
Пропуски в столбце rating были замененны на tbd, что означает что рейтинга нет или он ожидается
Пропуски в столбцах critic_score и user_score были заменены на нулевые, что означает, что нет оценки. Сделать замену на медианное или какое-либо иное значение на текущем этапе нельзя, т.к. будет смещение в данных.
Суммарные продажи посчитаны.

   Исследовательский анализ выполнен:
   До 1994 года выпускалось примерно 50 игр в год для разных платформ, а с 1994 года начался рост количества игр для платформ, где согласно тренду за пять лет происходит удвоение количества, но 2008 год стал экстемумом и было выпущено 1430 игр,а после 2009 года началось падение количественного показателя и в 2012 году - в 2 раза по сравнению с 2011, и зафиксировался снижающийся тренд и среднее количество игр выпускоемое в год - 579 +/-60;
   Средний срок жизни платформы равен 7 годам;
   Предварительный - да, но не зватает дополнительных данных активность игроков на платформе;
   Количество игр растёт на платформах PS4 и XOne, в отличии от 3DS и WiiU;
   Топ3 игр: Fifa 17, Pokemon Sun/Moon, Uncharted 4 - из графика видно, что это топовые игры с самыми высокими показателями выручки, соответственно вывод о том, что топовыми платформами являются PS4, 3DS, XOne. PC - это платформа долгожитель, но это вполне логично, т.к. от ПК никто отказываться не планирует, т.к. он связан со множеством других функций;
   Корреляционная зависимость между отзывами пользователей,критиков и продажами есть, но слабо выраженая. Например, у самой кассовой игры 2016 года - fifa 17, далеко не самый высокий показатель. Есть игры, отзывы которых высокие, но продажи среднии. Тут с моей точки зрения нужны более свежии данные с более высоким уровнем качества;
   Для платформы PS4 корреляция между продажами и пользовательскими отзывами: -0,12 - слабая, отрицательная, в тоже время оценки критиков коррелируют:0,38 - средняя зависимость, положительная, а усреднённые отзывы коррелируют слабо за счёт разности коррекляций для данной платформы;
   Для платформы XOne корреляция между продажами и пользовательскими отзывами: -0,18 - слабая, отрицательная, в тоже время оценки критиков коррелируют:0,41 - средняя зависимость, положительная, а усреднённые отзывы коррелируют слабо за счёт разности коррекляций для данной платформы;
   Для платформы 3DS корреляция между продажами и пользовательскими отзывами: 0.41 - средняя, положительная, в тоже время оценки критиков коррелируют:0,34 - средняя зависимость, положительная, а усреднённые отзывы коррелируют средне за счёт смещения в пользовательскую сторону для данной платформы;
   Таким образом, пользовательские отзывы в большей части слабо коррелируют и в отрицателдьную сторону, что не совпадает с отзывами критиков, т.к. тут зависимость есть от 0.34-0.41 средневыраженая. Средний показатель отзывов не позволяет выявить корреляцию между отзывами и продажами, т.к. он постояно смещается. Соответственно, критики более точно прогнозируют успех игры, в отличии от пользователей. Конечно, вывод немного странный, но тут нужно с моей точки зрения проведение дополнительного анализа. Правда, отличается сильно по всем коэффициентам корреляции платформа 3DS, где отзывов критиков меньше, а пользователи оцинивают на порядок лучше, чем пользователи платформ PS4 и XOne;
   Игровая индустрия очень быстро изменяется:тренд выручки нисходящий; топ платформы: PS4, WiiU, XOne, 3DS. (по усреднённой сумарной выручке);
   Топовые жанры: Shooters, Sports, Role-playing - 2016 и 2015 годов; Топ-низ жанры: Adventure, Puzzle. (по усреднённой сумарной выручке);

   Портреты пользователей составлены (по суммарным показателям выручки):

   Самые популярные платформы (топ-5).
EU: PS4, XOne, PC, 3DS, WiiU - Европа
JP: 3DS, PS4, PSV, PS3, WiiU - Япония
NA: PS4, XOne, 3DS, WiiU, PC - CША

   Самые популярные жанры (топ-5)
EU: Shooter, Sports, Action, Role-Playing, Racing - Европа
JP: Action, Role-Playing, Adventure, Shooter, Misc - Япония
NA: Shooter, Action, Sports, Role-Playing, Fighting - CША

   Влияет ли рейтинг ESRB на продажи в отдельном регионе?

   Да, влияние есть, и это проявляется на графике, кроме региона - Япония, здесь сумарные продажи у игр без рейтинга выше.
   Пользователи Европы и Штатов любят "шутеры", что соответствует платформе PS4 и XOne, но американские пользователи предпочитают "экшен" жанр - спортивномe, в топе у европейцев входят "гонки", а у представителей штатов "файтинги". Портрет японского игрока полностью отличается, т.к. главный игровой жанр - "экшен", а основная консоль - 3DS. По большей части игровые жанры для определённого региона соответствуют менталитету и культуре стран, консоли же подбираются исходя из основных жанров. Правда некоторые платформы имеют множество жанров, что позволяет покрыть потребности разных регионов. Рейтинг ESRB влияет на европейских и американских игроков, кроме региона - Япония, здесь сумарные продажи у игр без рейтинга выше.

   Проверка гипотез
   Первая гипотеза: HO - подтвердилась, H1 - отвергнута. Что подтвердило статистическую гипотезу о равенстве пользовательских рейтингов, т.к. базировалась она на нулевой. При проведении статистического теста по всему периоду, получилось, что рейтинги платформ разные и нулевая гипотеза отвергалась, но когда был выбран актуальный период - 2016 год, то ситуация изменилась и нулевая гипотеза не отвергнута.
   Вторая гипотеза: HO - принята, H1 - отвергнута. При проведении статистического теста по всему периоду, получилось, что рейтинги жанров action и sports разные и нулевая гипотеза отвергалась, НО когда был выбран актуальный период, то ситуация изменилась и нулевая гипотеза не отвергнута, что означет, что альтернативная гипотеза отвергнута и средние рейтинги равны со статистической значимостью 0.05.
