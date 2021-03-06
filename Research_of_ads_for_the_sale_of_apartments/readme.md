# Исследование объявлений о продаже квартир
## Описание проекта
### В моем распоряжении данные сервиса Яндекс.Недвижимость — архив объявлений о продаже квартир в Санкт-Петербурге и соседних населённых пунктах за несколько лет. Нужно научиться определять рыночную стоимость объектов недвижимости. Моя задача — установить параметры. Это позволит построить автоматизированную систему: она отследит аномалии и мошенническую деятельность.
### По каждой квартире на продажу доступны два вида данных. Первые вписаны пользователем, вторые — получены автоматически на основе картографических данных. Например, расстояние до центра, аэропорта, ближайшего парка и водоёма.
## Предобработка данных:
- определил и изучил пропущенные значения;
- для некоторых пропущенных значений предположил логичную замену;
- заполнил пропуски, где это уместно. Описал, почему решили заполнить пропуски именно в этих столбцах и как выбрал значения;
- указал причины, которые могли привести к пропускам в данных;
- привел данные к нужным типам;
- пояснил, в каких столбцах нужно изменить тип данных и почему.
## Посчитал и добавил в таблицу:
- цену квадратного метра;
- день недели, месяц и год публикации объявления;
- этаж квартиры; варианты — первый, последний, другой;
- соотношение жилой и общей площади, а также отношение площади кухни к общей.
## Общий вывод:
Сделаем общие выводы и на основе данных, и на основе графиков. Чем больше площадь квартиры, тем выше цена, чем больше цена за квадратный метр, тем выше цена. Чем выше доля жилой площади/площадь кухни, тем выше цена. Чем больше комнат, тем выше цена На первом этаже квартира дешевле, чем на остальных; на последнем дороже, чем на первом, но дешевле чем на остальных. Чем ближе к центру, тем дороже квартира. В самом центре (< 1 км до центра) квартиры стоят на порядок дороже, чем на более удаленных. Квартиры, размещенные к продаже в будние дни, в среднем дороже, чем размещенные в выходные. Квартиры, размещенные к продаже в летние месяцы и в октябре, в среднем дешевле, чем размещенные в любые другие месяца. В начале и в конце года цены стабильные и высокие. Квартиры, размещенные к продаже в 2014 году, дороже всех. Период 2015-2018 - период низких цен на квартиры (кризис). 2019г. - рецессия экономики - цены пошли вверх впервые после наступления кризиса.
## Библиотеки:
1. pandas
2. numpy
3. matplotlib.pyplot
4. seaborn
5. pymystem3
6. pprint
