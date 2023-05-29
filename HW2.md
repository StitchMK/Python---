## Задача 1

Скачать файл в уроке
Считать данные с помощью pandas
Вывести на экран первые 5 строк
Посмотреть на описание признаков и на их содержание


```python
import pandas as pd
```


```python
df = pd.read_csv('/Users/mschneider/Downloads/kc-house-data.csv', encoding='cp1251', index_col='id')
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>price</th>
      <th>bedrooms</th>
      <th>bathrooms</th>
      <th>sqft_living</th>
      <th>sqft_lot</th>
      <th>floors</th>
      <th>waterfront</th>
      <th>view</th>
      <th>condition</th>
      <th>grade</th>
      <th>sqft_above</th>
      <th>sqft_basement</th>
      <th>yr_built</th>
      <th>yr_renovated</th>
      <th>zipcode</th>
      <th>lat</th>
      <th>long</th>
      <th>sqft_living15</th>
      <th>sqft_lot15</th>
    </tr>
    <tr>
      <th>id</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7129300520</th>
      <td>20141013T000000</td>
      <td>221900.0</td>
      <td>3</td>
      <td>1.00</td>
      <td>1180</td>
      <td>5650</td>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>1180</td>
      <td>0</td>
      <td>1955</td>
      <td>0</td>
      <td>98178</td>
      <td>47.5112</td>
      <td>-122.257</td>
      <td>1340</td>
      <td>5650</td>
    </tr>
    <tr>
      <th>6414100192</th>
      <td>20141209T000000</td>
      <td>538000.0</td>
      <td>3</td>
      <td>2.25</td>
      <td>2570</td>
      <td>7242</td>
      <td>2.0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>2170</td>
      <td>400</td>
      <td>1951</td>
      <td>1991</td>
      <td>98125</td>
      <td>47.7210</td>
      <td>-122.319</td>
      <td>1690</td>
      <td>7639</td>
    </tr>
    <tr>
      <th>5631500400</th>
      <td>20150225T000000</td>
      <td>180000.0</td>
      <td>2</td>
      <td>1.00</td>
      <td>770</td>
      <td>10000</td>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>6</td>
      <td>770</td>
      <td>0</td>
      <td>1933</td>
      <td>0</td>
      <td>98028</td>
      <td>47.7379</td>
      <td>-122.233</td>
      <td>2720</td>
      <td>8062</td>
    </tr>
    <tr>
      <th>2487200875</th>
      <td>20141209T000000</td>
      <td>604000.0</td>
      <td>4</td>
      <td>3.00</td>
      <td>1960</td>
      <td>5000</td>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>7</td>
      <td>1050</td>
      <td>910</td>
      <td>1965</td>
      <td>0</td>
      <td>98136</td>
      <td>47.5208</td>
      <td>-122.393</td>
      <td>1360</td>
      <td>5000</td>
    </tr>
    <tr>
      <th>1954400510</th>
      <td>20150218T000000</td>
      <td>510000.0</td>
      <td>3</td>
      <td>2.00</td>
      <td>1680</td>
      <td>8080</td>
      <td>1.0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>8</td>
      <td>1680</td>
      <td>0</td>
      <td>1987</td>
      <td>0</td>
      <td>98074</td>
      <td>47.6168</td>
      <td>-122.045</td>
      <td>1800</td>
      <td>7503</td>
    </tr>
  </tbody>
</table>
</div>



## Задача 2

Проведите первичный анализ данных <br/>
Изучите типы данных <br/>
Найдите количество пропущенных ячеек в данных <br/>
Посчитайте основные статистики по всем признакам и поизучайте их <br/>
Пишите выводы

Все данные таблицы - это числовой тип даных, кроме столбца date - тип данных: object


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    Int64Index: 21613 entries, 7129300520 to 1523300157
    Data columns (total 20 columns):
     #   Column         Non-Null Count  Dtype  
    ---  ------         --------------  -----  
     0   date           21613 non-null  object 
     1   price          21613 non-null  float64
     2   bedrooms       21613 non-null  int64  
     3   bathrooms      21613 non-null  float64
     4   sqft_living    21613 non-null  int64  
     5   sqft_lot       21613 non-null  int64  
     6   floors         21613 non-null  float64
     7   waterfront     21613 non-null  int64  
     8   view           21613 non-null  int64  
     9   condition      21613 non-null  int64  
     10  grade          21613 non-null  int64  
     11  sqft_above     21613 non-null  int64  
     12  sqft_basement  21613 non-null  int64  
     13  yr_built       21613 non-null  int64  
     14  yr_renovated   21613 non-null  int64  
     15  zipcode        21613 non-null  int64  
     16  lat            21613 non-null  float64
     17  long           21613 non-null  float64
     18  sqft_living15  21613 non-null  int64  
     19  sqft_lot15     21613 non-null  int64  
    dtypes: float64(5), int64(14), object(1)
    memory usage: 3.5+ MB


Таблица не содержит пустых ячеек


```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>price</th>
      <th>bedrooms</th>
      <th>bathrooms</th>
      <th>sqft_living</th>
      <th>sqft_lot</th>
      <th>floors</th>
      <th>waterfront</th>
      <th>view</th>
      <th>condition</th>
      <th>grade</th>
      <th>sqft_above</th>
      <th>sqft_basement</th>
      <th>yr_built</th>
      <th>yr_renovated</th>
      <th>zipcode</th>
      <th>lat</th>
      <th>long</th>
      <th>sqft_living15</th>
      <th>sqft_lot15</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.161300e+04</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>2.161300e+04</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
      <td>21613.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>5.400881e+05</td>
      <td>3.370842</td>
      <td>2.114757</td>
      <td>2079.899736</td>
      <td>1.510697e+04</td>
      <td>1.494309</td>
      <td>0.007542</td>
      <td>0.234303</td>
      <td>3.409430</td>
      <td>7.656873</td>
      <td>1788.390691</td>
      <td>291.509045</td>
      <td>1971.005136</td>
      <td>84.402258</td>
      <td>98077.939805</td>
      <td>47.560053</td>
      <td>-122.213896</td>
      <td>1986.552492</td>
      <td>12768.455652</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3.671272e+05</td>
      <td>0.930062</td>
      <td>0.770163</td>
      <td>918.440897</td>
      <td>4.142051e+04</td>
      <td>0.539989</td>
      <td>0.086517</td>
      <td>0.766318</td>
      <td>0.650743</td>
      <td>1.175459</td>
      <td>828.090978</td>
      <td>442.575043</td>
      <td>29.373411</td>
      <td>401.679240</td>
      <td>53.505026</td>
      <td>0.138564</td>
      <td>0.140828</td>
      <td>685.391304</td>
      <td>27304.179631</td>
    </tr>
    <tr>
      <th>min</th>
      <td>7.500000e+04</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>290.000000</td>
      <td>5.200000e+02</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>1.000000</td>
      <td>290.000000</td>
      <td>0.000000</td>
      <td>1900.000000</td>
      <td>0.000000</td>
      <td>98001.000000</td>
      <td>47.155900</td>
      <td>-122.519000</td>
      <td>399.000000</td>
      <td>651.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>3.219500e+05</td>
      <td>3.000000</td>
      <td>1.750000</td>
      <td>1427.000000</td>
      <td>5.040000e+03</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>3.000000</td>
      <td>7.000000</td>
      <td>1190.000000</td>
      <td>0.000000</td>
      <td>1951.000000</td>
      <td>0.000000</td>
      <td>98033.000000</td>
      <td>47.471000</td>
      <td>-122.328000</td>
      <td>1490.000000</td>
      <td>5100.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>4.500000e+05</td>
      <td>3.000000</td>
      <td>2.250000</td>
      <td>1910.000000</td>
      <td>7.618000e+03</td>
      <td>1.500000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>3.000000</td>
      <td>7.000000</td>
      <td>1560.000000</td>
      <td>0.000000</td>
      <td>1975.000000</td>
      <td>0.000000</td>
      <td>98065.000000</td>
      <td>47.571800</td>
      <td>-122.230000</td>
      <td>1840.000000</td>
      <td>7620.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>6.450000e+05</td>
      <td>4.000000</td>
      <td>2.500000</td>
      <td>2550.000000</td>
      <td>1.068800e+04</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>4.000000</td>
      <td>8.000000</td>
      <td>2210.000000</td>
      <td>560.000000</td>
      <td>1997.000000</td>
      <td>0.000000</td>
      <td>98118.000000</td>
      <td>47.678000</td>
      <td>-122.125000</td>
      <td>2360.000000</td>
      <td>10083.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>7.700000e+06</td>
      <td>33.000000</td>
      <td>8.000000</td>
      <td>13540.000000</td>
      <td>1.651359e+06</td>
      <td>3.500000</td>
      <td>1.000000</td>
      <td>4.000000</td>
      <td>5.000000</td>
      <td>13.000000</td>
      <td>9410.000000</td>
      <td>4820.000000</td>
      <td>2015.000000</td>
      <td>2015.000000</td>
      <td>98199.000000</td>
      <td>47.777600</td>
      <td>-121.315000</td>
      <td>6210.000000</td>
      <td>871200.000000</td>
    </tr>
  </tbody>
</table>
</div>



## Задача 3
Ответьте на несколько вопросов
### 3.1 В каком диапазоне изменяются стоимости недвижимости?


```python
df['price'].min(), df['price'].max()
```




    (75000.0, 7700000.0)



### 3.2 Какую долю в среднем занимают жилая площадь от всей площади по всем домам?


```python
df['sqft_living'].mean() * 100 / df['sqft_lot'].mean()
```




    13.76781757959227



### 3.3 Как много домов с разными этажами в данных?


```python
df['floors'].value_counts()
```




    1.0    10680
    2.0     8241
    1.5     1910
    3.0      613
    2.5      161
    3.5        8
    Name: floors, dtype: int64



### 3.4 Насколько хорошие состояния у домов в данных?


```python
df['condition'].value_counts()
```




    3    14031
    4     5679
    5     1701
    2      172
    1       30
    Name: condition, dtype: int64



### 3.5 Найдите года, когда построили первый дом, когда построили последний дом в данных?


```python
df['yr_built'].min(), df['yr_built'].max()
```




    (1900, 2015)



## Задача 4
Ответьте на несколько вопросов

### 4.1 Сколько в среднем стоят дома, у которых 2 спальни?


```python
df[df['bedrooms'] == 2]['price'].mean()
```




    401372.681884058



### 4.2 Какая в среднем общая площадь домов, у которых стоимость больше 600 000?


```python
df[df['price'] > 600000]['sqft_lot'].mean()
```




    20442.524776214832



### 4.3 Как много домов коснулся ремонт?


```python
df[df['yr_renovated'] != 0].shape[0]
```




    914



### 4.4 Насколько в среднем стоимость домов с оценкой grade домов выше 10 отличается от стоимости домов с оценкой grade меньше 4?


```python
price_grade_10 = df[df['grade'] > 10]['price'].mean()
print(price_grade_10)
```

    1678635.1175298805



```python
price_grade_4 = df[df['grade'] < 4]['price'].mean()
print(price_grade_10)
```

    1678635.1175298805



```python
difference = price_grade_10 - price_grade_4
print(difference)
```

    1488885.1175298805


## Задача 5
Ответьте на несколько вопросов
### 5.1 Выберите дом клиенту
Клиент хочет дом с видом на набережную, как минимум с тремя ванными и с подвалом. Сколько вариантов есть у клиента?


```python
df[(df['waterfront'] == 1) & (df['bathrooms'] > 3) & (df['sqft_basement'] != 0)].shape[0]
```




    36



### 5.2 Выберите дом клиенту
Клиент хочет дом либо с очень красивым видом из окна, либо с видом на набережную, в очень хорошем состоянии и год постройки не меньше 1980 года. В какой ценовом диапазоне будут дома?


```python
clients_choice = df[((df['view'] == 4) | (df['waterfront'] == 1)) & (df['condition'] == 5) & (df['yr_built'] >= 1980)]
clients_choice
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>price</th>
      <th>bedrooms</th>
      <th>bathrooms</th>
      <th>sqft_living</th>
      <th>sqft_lot</th>
      <th>floors</th>
      <th>waterfront</th>
      <th>view</th>
      <th>condition</th>
      <th>grade</th>
      <th>sqft_above</th>
      <th>sqft_basement</th>
      <th>yr_built</th>
      <th>yr_renovated</th>
      <th>zipcode</th>
      <th>lat</th>
      <th>long</th>
      <th>sqft_living15</th>
      <th>sqft_lot15</th>
    </tr>
    <tr>
      <th>id</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>3761100045</th>
      <td>20140618T000000</td>
      <td>3000000.0</td>
      <td>4</td>
      <td>4.25</td>
      <td>4850</td>
      <td>12445</td>
      <td>2.0</td>
      <td>1</td>
      <td>4</td>
      <td>5</td>
      <td>10</td>
      <td>3850</td>
      <td>1000</td>
      <td>1989</td>
      <td>0</td>
      <td>98034</td>
      <td>47.7011</td>
      <td>-122.244</td>
      <td>3350</td>
      <td>12210</td>
    </tr>
    <tr>
      <th>7278100515</th>
      <td>20140821T000000</td>
      <td>1295000.0</td>
      <td>2</td>
      <td>2.50</td>
      <td>2910</td>
      <td>19449</td>
      <td>2.0</td>
      <td>1</td>
      <td>4</td>
      <td>5</td>
      <td>9</td>
      <td>1940</td>
      <td>970</td>
      <td>1985</td>
      <td>0</td>
      <td>98177</td>
      <td>47.7729</td>
      <td>-122.393</td>
      <td>2540</td>
      <td>23598</td>
    </tr>
    <tr>
      <th>3585901025</th>
      <td>20140613T000000</td>
      <td>1735000.0</td>
      <td>3</td>
      <td>2.50</td>
      <td>4310</td>
      <td>32093</td>
      <td>1.5</td>
      <td>0</td>
      <td>4</td>
      <td>5</td>
      <td>10</td>
      <td>2510</td>
      <td>1800</td>
      <td>1982</td>
      <td>0</td>
      <td>98177</td>
      <td>47.7624</td>
      <td>-122.380</td>
      <td>3810</td>
      <td>26400</td>
    </tr>
    <tr>
      <th>7856400300</th>
      <td>20140702T000000</td>
      <td>1411600.0</td>
      <td>2</td>
      <td>2.50</td>
      <td>3180</td>
      <td>9400</td>
      <td>2.0</td>
      <td>0</td>
      <td>4</td>
      <td>5</td>
      <td>10</td>
      <td>2610</td>
      <td>570</td>
      <td>1985</td>
      <td>0</td>
      <td>98006</td>
      <td>47.5617</td>
      <td>-122.158</td>
      <td>3760</td>
      <td>9450</td>
    </tr>
    <tr>
      <th>7856400300</th>
      <td>20150322T000000</td>
      <td>1505000.0</td>
      <td>2</td>
      <td>2.50</td>
      <td>3180</td>
      <td>9400</td>
      <td>2.0</td>
      <td>0</td>
      <td>4</td>
      <td>5</td>
      <td>10</td>
      <td>2610</td>
      <td>570</td>
      <td>1985</td>
      <td>0</td>
      <td>98006</td>
      <td>47.5617</td>
      <td>-122.158</td>
      <td>3760</td>
      <td>9450</td>
    </tr>
  </tbody>
</table>
</div>




```python
clients_choice['price'].min(), clients_choice['price'].max()
```




    (1295000.0, 3000000.0)



### 5.3 Выберите дом клиенту
Клиент хочет дом без подвала, с двумя этажами, стоимостью до 150000. Какая оценка по состоянию у таких домов в среднем?


```python
clients_choice = df[(df['sqft_basement'] == 0) & (df['floors'] == 2) & (df['price'] < 150000)]
clients_choice
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>date</th>
      <th>price</th>
      <th>bedrooms</th>
      <th>bathrooms</th>
      <th>sqft_living</th>
      <th>sqft_lot</th>
      <th>floors</th>
      <th>waterfront</th>
      <th>view</th>
      <th>condition</th>
      <th>grade</th>
      <th>sqft_above</th>
      <th>sqft_basement</th>
      <th>yr_built</th>
      <th>yr_renovated</th>
      <th>zipcode</th>
      <th>lat</th>
      <th>long</th>
      <th>sqft_living15</th>
      <th>sqft_lot15</th>
    </tr>
    <tr>
      <th>id</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>5061300030</th>
      <td>20140508T000000</td>
      <td>134000.0</td>
      <td>2</td>
      <td>1.50</td>
      <td>980</td>
      <td>5000</td>
      <td>2.0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>980</td>
      <td>0</td>
      <td>1922</td>
      <td>2003</td>
      <td>98014</td>
      <td>47.7076</td>
      <td>-121.359</td>
      <td>1040</td>
      <td>5000</td>
    </tr>
    <tr>
      <th>5466310060</th>
      <td>20150324T000000</td>
      <td>139500.0</td>
      <td>2</td>
      <td>1.50</td>
      <td>1230</td>
      <td>1561</td>
      <td>2.0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>1230</td>
      <td>0</td>
      <td>1983</td>
      <td>0</td>
      <td>98042</td>
      <td>47.3768</td>
      <td>-122.149</td>
      <td>1660</td>
      <td>2243</td>
    </tr>
    <tr>
      <th>7614100080</th>
      <td>20150211T000000</td>
      <td>140000.0</td>
      <td>3</td>
      <td>1.75</td>
      <td>1270</td>
      <td>8991</td>
      <td>2.0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>1270</td>
      <td>0</td>
      <td>1981</td>
      <td>0</td>
      <td>98042</td>
      <td>47.3563</td>
      <td>-122.149</td>
      <td>1270</td>
      <td>8993</td>
    </tr>
    <tr>
      <th>9272202260</th>
      <td>20140924T000000</td>
      <td>130000.0</td>
      <td>3</td>
      <td>1.00</td>
      <td>1200</td>
      <td>7000</td>
      <td>2.0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>7</td>
      <td>1200</td>
      <td>0</td>
      <td>1908</td>
      <td>0</td>
      <td>98116</td>
      <td>47.5883</td>
      <td>-122.384</td>
      <td>3290</td>
      <td>6000</td>
    </tr>
    <tr>
      <th>4239400300</th>
      <td>20141129T000000</td>
      <td>90000.0</td>
      <td>3</td>
      <td>1.00</td>
      <td>980</td>
      <td>2490</td>
      <td>2.0</td>
      <td>0</td>
      <td>0</td>
      <td>4</td>
      <td>6</td>
      <td>980</td>
      <td>0</td>
      <td>1969</td>
      <td>0</td>
      <td>98092</td>
      <td>47.3170</td>
      <td>-122.182</td>
      <td>980</td>
      <td>3154</td>
    </tr>
    <tr>
      <th>7399100210</th>
      <td>20141126T000000</td>
      <td>140000.0</td>
      <td>3</td>
      <td>1.50</td>
      <td>1200</td>
      <td>2002</td>
      <td>2.0</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>8</td>
      <td>1200</td>
      <td>0</td>
      <td>1966</td>
      <td>0</td>
      <td>98055</td>
      <td>47.4659</td>
      <td>-122.189</td>
      <td>1270</td>
      <td>1848</td>
    </tr>
  </tbody>
</table>
</div>




```python
clients_choice['condition'].mean()
```




    2.8333333333333335




```python

```
