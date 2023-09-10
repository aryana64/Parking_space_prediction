# Parking_space_prediction
## Модель находится на яндекс диске https://disk.yandex.com/d/vHhTBW7tBtoEcA
## Всероссийский хакатон “Цифровой прорыв” в Нижнем Новгороде, 08.09-10.09.2023
![image](https://github.com/aryana64/Parking_space_prediction/assets/112254501/f5ab509c-dfb4-4fd8-9e85-18cb53f169b4)

Кейсодержатель группа “Самолёт” (Samolet group)
### Проблематика 
Формирование информативной и **актуальной для клиентов рассылки** влияет на репутацию компании и напрямую обеспечивает лояльность клиентов в долгосрочной перспективе.
Для предупреждения издержек негативного характера необходимо построить модель, которая должна **точно выделять целевую аудиторию** для каждой рассылки, что позволит избежать спама во входящих сообщениях неактивных клиентов, и при этом в перспективе увеличит эффективность продаж за счет правильно адресованной рассылки
### EDA 
Данные очень разреженные, формируют группы (spans)
#### Преобразование данных 
**Числовые фичи**
1. Большие значения: 
    1. Выделяем m групп столбцов по масштабу значений (в пределах триллиона, миллиарда, тысяч и т.д.) и определяем, что они могут значить (подумать или погуглить услуги и их стоимость)
    2. Смотрим значения в этих столбцах в каждой из m групп и на основе этого выделяем n промежутков для каждой группы
    3. Создаем n категориальных признаков по попаданию в эти промежутки для каждой из m групп и заполняем их
    4. Итог: m групп по n категориальных признаков
2. Маленькие значения
    1. Заполнить нулями пустые значения
**Строковые значения**
1. Ссылка
### Modeling
Использованные алгоритмы:
Logistic regression, gradient boosting, SVM, decision trees
RNN, Transformers для анализа временных последовательностей
После генерации новых признаков было обнаружено, что они слабо коррелируют между собой. По этой причине выбор модели пал на Transformer, поскольку они способны работать с разными типами данных.
Решение рассчитано для различных OS.
В файле model.pt расположена сама модель, ссылка на Яндекс.Диск  

https://disk.yandex.com/d/vHhTBW7tBtoEcA  
