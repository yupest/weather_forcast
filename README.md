# weather_forcast
Calculating complex factor fire safety

## [meteostations.csv](https://github.com/yupest/weather_forcast/blob/main/data/meteostations.csv)

Метеостанции и соответствие им населенных пунктов (НП). Был произведен поиск фактически ближайших метеостанций. В результате чего, оказалось, что станции *Леприндо и Улан-Макит* находятся далеко от заданных населенных пунктов, поэтому могут быть исключены из исследования.

|колонка|обозначение|
|--|--|
|district| название района
|NP| название населенного пункта
|station| метеостанция, которая относится к НП с сайта rp5
|number| номер метеостанции
|lat_station| широта метеостанции
|lon_station| долгота метеостанции
|poly_wkt| полигон населенного пункта
|HubName| ближайшая станция по факту (найдена с помощью QGIS)
|HubDist| дистанция до ближайшей метеостанции
|centroid| точка центроида полигона НП

## [kp_po_forcast.csv](https://github.com/yupest/weather_forcast/blob/main/data/kp_po_forcast.csv)

По всем метеостанциям, по дате и времени, при подсчете Комплексного показателя были взяты средние температуры, так как в таблице не было за 12. Дождливым день считается, если в какое либо время в течение дня осадки превысили 2.5.

|колонка|обозначение|
|--|--|
|station| название станции
|date| дата
|time| время
|datetime| время дата
|sss| высота снежного покрова (см)
|RRR| осадки
|T| температура воздуха
|Td| температура точки росы
|t(t-r)| подсчет (по средним за день T и Td) kp показателя без учета дней после дождя 
|n| количество дней после дождя (при RRR >2.5 - считается дождем - и n = 0)
|kp| комплексный показатель пожарной безопасности с учетом n (сумма  предыдущих kp без дождя)

## [kp_po_forcast_nearest_station.csv](https://github.com/yupest/weather_forcast/blob/main/data/kp_po_forcast_nearest_station.csv)

То же самое, что файл выше, только не учитывая метеостанции *Леприндо и Улан-Макит*

## [kp_po_forcast_by_day.csv](https://github.com/yupest/weather_forcast/blob/main/data/kp_po_forcast_by_day.csv)

По всем метеостанциям, сгруппировано по дням:
- взяты средние sss, T, Td
- максимальное RRR


## [kp_po_forcast_nearest_station_by_day.csv](https://github.com/yupest/weather_forcast/blob/main/data/kp_po_forcast_nearest_station_by_day.csv)

То же самое, что файл выше, только не учитывая метеостанции *Леприндо и Улан-Макит*
