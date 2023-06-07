## Задача 1
Скачать данные по ссылке https://www.kaggle.com/datasets/ionaskel/laptop-prices
Считать данные с помощью pandas
Вывести на экран первые 5 строк


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
      <td>221900</td>
      <td>3</td>
      <td>1</td>
      <td>1180</td>
      <td>5650</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>1180</td>
      <td>0</td>
      <td>1955</td>
      <td>0</td>
      <td>98178</td>
      <td>48</td>
      <td>-122</td>
      <td>1340</td>
      <td>5650</td>
    </tr>
    <tr>
      <th>6414100192</th>
      <td>20141209T000000</td>
      <td>538000</td>
      <td>3</td>
      <td>2</td>
      <td>2570</td>
      <td>7242</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>2170</td>
      <td>400</td>
      <td>1951</td>
      <td>1991</td>
      <td>98125</td>
      <td>48</td>
      <td>-122</td>
      <td>1690</td>
      <td>7639</td>
    </tr>
    <tr>
      <th>5631500400</th>
      <td>20150225T000000</td>
      <td>180000</td>
      <td>2</td>
      <td>1</td>
      <td>770</td>
      <td>10000</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>6</td>
      <td>770</td>
      <td>0</td>
      <td>1933</td>
      <td>0</td>
      <td>98028</td>
      <td>48</td>
      <td>-122</td>
      <td>2720</td>
      <td>8062</td>
    </tr>
    <tr>
      <th>2487200875</th>
      <td>20141209T000000</td>
      <td>604000</td>
      <td>4</td>
      <td>3</td>
      <td>1960</td>
      <td>5000</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>7</td>
      <td>1050</td>
      <td>910</td>
      <td>1965</td>
      <td>0</td>
      <td>98136</td>
      <td>48</td>
      <td>-122</td>
      <td>1360</td>
      <td>5000</td>
    </tr>
    <tr>
      <th>1954400510</th>
      <td>20150218T000000</td>
      <td>510000</td>
      <td>3</td>
      <td>2</td>
      <td>1680</td>
      <td>8080</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>8</td>
      <td>1680</td>
      <td>0</td>
      <td>1987</td>
      <td>0</td>
      <td>98074</td>
      <td>48</td>
      <td>-122</td>
      <td>1800</td>
      <td>7503</td>
    </tr>
  </tbody>
</table>
</div>



### 1.2 Создать новый признак delta_renovated, который будет содержать разницу в годах между годом реновацией дома и годом постройки дома
Если реновации дома не было, то в новом признаке поставьте 0


```python
# Вычисление разницы между годом постройки и годом реновации
df['delta_renovated'] = np.where(df['yr_renovated'] == 0, 0, df['yr_renovated'] - df['yr_built'])

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
      <th>...</th>
      <th>sqft_above</th>
      <th>sqft_basement</th>
      <th>yr_built</th>
      <th>yr_renovated</th>
      <th>zipcode</th>
      <th>lat</th>
      <th>long</th>
      <th>sqft_living15</th>
      <th>sqft_lot15</th>
      <th>delta_renovated</th>
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
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7129300520</th>
      <td>20141013T000000</td>
      <td>221900</td>
      <td>3</td>
      <td>1</td>
      <td>1180</td>
      <td>5650</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>...</td>
      <td>1180</td>
      <td>0</td>
      <td>1955</td>
      <td>0</td>
      <td>98178</td>
      <td>48</td>
      <td>-122</td>
      <td>1340</td>
      <td>5650</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6414100192</th>
      <td>20141209T000000</td>
      <td>538000</td>
      <td>3</td>
      <td>2</td>
      <td>2570</td>
      <td>7242</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>...</td>
      <td>2170</td>
      <td>400</td>
      <td>1951</td>
      <td>1991</td>
      <td>98125</td>
      <td>48</td>
      <td>-122</td>
      <td>1690</td>
      <td>7639</td>
      <td>40</td>
    </tr>
    <tr>
      <th>5631500400</th>
      <td>20150225T000000</td>
      <td>180000</td>
      <td>2</td>
      <td>1</td>
      <td>770</td>
      <td>10000</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>...</td>
      <td>770</td>
      <td>0</td>
      <td>1933</td>
      <td>0</td>
      <td>98028</td>
      <td>48</td>
      <td>-122</td>
      <td>2720</td>
      <td>8062</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2487200875</th>
      <td>20141209T000000</td>
      <td>604000</td>
      <td>4</td>
      <td>3</td>
      <td>1960</td>
      <td>5000</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>...</td>
      <td>1050</td>
      <td>910</td>
      <td>1965</td>
      <td>0</td>
      <td>98136</td>
      <td>48</td>
      <td>-122</td>
      <td>1360</td>
      <td>5000</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1954400510</th>
      <td>20150218T000000</td>
      <td>510000</td>
      <td>3</td>
      <td>2</td>
      <td>1680</td>
      <td>8080</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>...</td>
      <td>1680</td>
      <td>0</td>
      <td>1987</td>
      <td>0</td>
      <td>98074</td>
      <td>48</td>
      <td>-122</td>
      <td>1800</td>
      <td>7503</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 21 columns</p>
</div>



### 1.3 Создайте признаки года продажи, месяца продажи


```python
# Преобразование столбца 'date' в формат даты и времени
df['date'] = pd.to_datetime(df['date'], format='%Y%m%dT%H%M%S')

# Создание признака 'год продажи'
df['year_sold'] = df['date'].dt.year

# Создание признака 'месяц продажи'
df['month_sold'] = df['date'].dt.month

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
      <th>...</th>
      <th>yr_built</th>
      <th>yr_renovated</th>
      <th>zipcode</th>
      <th>lat</th>
      <th>long</th>
      <th>sqft_living15</th>
      <th>sqft_lot15</th>
      <th>delta_renovated</th>
      <th>year_sold</th>
      <th>month_sold</th>
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
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7129300520</th>
      <td>2014-10-13</td>
      <td>221900</td>
      <td>3</td>
      <td>1</td>
      <td>1180</td>
      <td>5650</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>...</td>
      <td>1955</td>
      <td>0</td>
      <td>98178</td>
      <td>48</td>
      <td>-122</td>
      <td>1340</td>
      <td>5650</td>
      <td>0</td>
      <td>2014</td>
      <td>10</td>
    </tr>
    <tr>
      <th>6414100192</th>
      <td>2014-12-09</td>
      <td>538000</td>
      <td>3</td>
      <td>2</td>
      <td>2570</td>
      <td>7242</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>...</td>
      <td>1951</td>
      <td>1991</td>
      <td>98125</td>
      <td>48</td>
      <td>-122</td>
      <td>1690</td>
      <td>7639</td>
      <td>40</td>
      <td>2014</td>
      <td>12</td>
    </tr>
    <tr>
      <th>5631500400</th>
      <td>2015-02-25</td>
      <td>180000</td>
      <td>2</td>
      <td>1</td>
      <td>770</td>
      <td>10000</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>...</td>
      <td>1933</td>
      <td>0</td>
      <td>98028</td>
      <td>48</td>
      <td>-122</td>
      <td>2720</td>
      <td>8062</td>
      <td>0</td>
      <td>2015</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2487200875</th>
      <td>2014-12-09</td>
      <td>604000</td>
      <td>4</td>
      <td>3</td>
      <td>1960</td>
      <td>5000</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>...</td>
      <td>1965</td>
      <td>0</td>
      <td>98136</td>
      <td>48</td>
      <td>-122</td>
      <td>1360</td>
      <td>5000</td>
      <td>0</td>
      <td>2014</td>
      <td>12</td>
    </tr>
    <tr>
      <th>1954400510</th>
      <td>2015-02-18</td>
      <td>510000</td>
      <td>3</td>
      <td>2</td>
      <td>1680</td>
      <td>8080</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>...</td>
      <td>1987</td>
      <td>0</td>
      <td>98074</td>
      <td>48</td>
      <td>-122</td>
      <td>1800</td>
      <td>7503</td>
      <td>0</td>
      <td>2015</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 23 columns</p>
</div>



### 1.4 Удалите признаки date, zipcode, lat, long


```python
# Удаление признаков 'date', 'zipcode', 'lat' и 'long'
df = df.drop(['date', 'zipcode', 'lat', 'long'], axis=1)

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
      <th>sqft_living15</th>
      <th>sqft_lot15</th>
      <th>delta_renovated</th>
      <th>year_sold</th>
      <th>month_sold</th>
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
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7129300520</th>
      <td>221900</td>
      <td>3</td>
      <td>1</td>
      <td>1180</td>
      <td>5650</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>1180</td>
      <td>0</td>
      <td>1955</td>
      <td>0</td>
      <td>1340</td>
      <td>5650</td>
      <td>0</td>
      <td>2014</td>
      <td>10</td>
    </tr>
    <tr>
      <th>6414100192</th>
      <td>538000</td>
      <td>3</td>
      <td>2</td>
      <td>2570</td>
      <td>7242</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>7</td>
      <td>2170</td>
      <td>400</td>
      <td>1951</td>
      <td>1991</td>
      <td>1690</td>
      <td>7639</td>
      <td>40</td>
      <td>2014</td>
      <td>12</td>
    </tr>
    <tr>
      <th>5631500400</th>
      <td>180000</td>
      <td>2</td>
      <td>1</td>
      <td>770</td>
      <td>10000</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>6</td>
      <td>770</td>
      <td>0</td>
      <td>1933</td>
      <td>0</td>
      <td>2720</td>
      <td>8062</td>
      <td>0</td>
      <td>2015</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2487200875</th>
      <td>604000</td>
      <td>4</td>
      <td>3</td>
      <td>1960</td>
      <td>5000</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>5</td>
      <td>7</td>
      <td>1050</td>
      <td>910</td>
      <td>1965</td>
      <td>0</td>
      <td>1360</td>
      <td>5000</td>
      <td>0</td>
      <td>2014</td>
      <td>12</td>
    </tr>
    <tr>
      <th>1954400510</th>
      <td>510000</td>
      <td>3</td>
      <td>2</td>
      <td>1680</td>
      <td>8080</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>8</td>
      <td>1680</td>
      <td>0</td>
      <td>1987</td>
      <td>0</td>
      <td>1800</td>
      <td>7503</td>
      <td>0</td>
      <td>2015</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>



## 2 задача
Создайте датафрейм с клиентами:
clients = pd.DataFrame({
'client_id': [1459, 4684, 3498, 3942, 4535, 2308, 2866, 2765, 1472, 4236, 2295,
939, 3840, 280, 20, 4332, 3475, 4213, 3113, 4809, 2134, 2242,
2068, 4929, 1384, 1589, 3317, 2260, 1727, 1764, 1611, 1474],
'house_id': [8965450190, 6823100225, 5104540330, 2131701075, 1522700060,
1189000207, 6821600300, 7137950720, 9510920050, 6131600255,
5428000070, 1788800910, 8100400160, 3123049142, 6306800010,
5083000375, 7920100025, 1951600150, 809001400, 339600110,
1622049154, 1099600250, 8563000110, 2768100205, 3995700435,
8861700030, 3303980210, 7731100066, 8146100580, 825069097,
3889100029, 9524100196]
})


```python
clients = pd.DataFrame({
    'client_id': [1459, 4684, 3498, 3942, 4535, 2308, 2866, 2765, 1472, 4236, 2295, 939, 3840, 280, 20, 4332, 3475, 4213, 3113, 4809, 2134, 2242, 2068, 4929, 1384, 1589, 3317, 2260, 1727, 1764, 1611, 1474],
    'house_id': [8965450190, 6823100225, 5104540330, 2131701075, 1522700060, 1189000207, 6821600300, 7137950720, 9510920050, 6131600255, 5428000070, 1788800910, 8100400160, 3123049142, 6306800010, 5083000375, 7920100025, 1951600150, 809001400, 339600110, 1622049154, 1099600250, 8563000110, 2768100205, 3995700435, 8861700030, 3303980210, 7731100066, 8146100580, 825069097, 3889100029, 9524100196]
})

```

### 2.1 Присоедините к таблице clients данные по домам через метод join


```python
# Создание датафрейма houses
houses = pd.DataFrame({
    'house_id': [8965450190, 6823100225, 5104540330, 2131701075, 1522700060,
                 1189000207, 6821600300, 7137950720, 9510920050, 6131600255,
                 5428000070, 1788800910, 8100400160, 3123049142, 6306800010,
                 5083000375, 7920100025, 1951600150, 809001400, 339600110,
                 1622049154, 1099600250, 8563000110, 2768100205, 3995700435,
                 8861700030, 3303980210, 7731100066, 8146100580, 825069097,
                 3889100029, 9524100196],
})
    
# Присоединение таблицы clients к таблице houses
clients = clients.join(houses.set_index('house_id'), on='house_id')
```

### 2.2 Присоедините к таблице clients данные по домам через метод merge
Это нужно, чтобы понимать, какие дома покупались клиентами
house_id - это индексы датафрейма с домами


```python
# Присоединение данных о домах к таблице клиентов
clients = clients.merge(houses, on='house_id', how='left')
```

## 3 задача
Составьте несколько сводных таблиц
### 3.1 Найдите среднюю стоимость домов в зависимости от количества спален
Отсортируйте от меньшей стоимости к большей


```python
# Создание сводной таблицы
pivot_table = df.pivot_table(values='price', index='bedrooms', aggfunc='mean')

# Сортировка по возрастанию стоимости
sorted_table = pivot_table.sort_values(by='price')

# Вывод отсортированной сводной таблицы
print(sorted_table)
```

               price
    bedrooms        
    1         317643
    2         401373
    0         409504
    3         466232
    11        520000
    4         635420
    33        640000
    5         786600
    10        819333
    6         825521
    9         894000
    7         951185
    8        1105077


### 3.2 Найдите минимальную, среднюю и максимальную стоимости домов в зависимости от состояния дома


```python
# Создание сводной таблицы
pivot_table = df.pivot_table(values='price', index='condition', aggfunc=['min', 'mean', 'max'])

# Вывод сводной таблицы
print(pivot_table)
```

                 min   mean     max
               price  price   price
    condition                      
    1          78000 334432 1500000
    2          80000 327287 2555000
    3          75000 542013 7062500
    4          89000 521200 7700000
    5         110000 612418 3650000


### 3.3 Постройте таблицу с подсчетом количества домов в данных в зависимости от вида на набережную и оценкой вида


```python
# Создание таблицы с подсчетом
count_table = df.groupby(['waterfront', 'view']).size().reset_index(name='count')

# Вывод таблицы с подсчетом
print(count_table)
```

       waterfront  view  count
    0           0     0  19489
    1           0     1    331
    2           0     2    955
    3           0     3    491
    4           0     4    184
    5           1     1      1
    6           1     2      8
    7           1     3     19
    8           1     4    135


### 3.4 Каких домов в зависимости от этажности и количества спален больше?


```python
# Создание сводной таблицы с подсчетом количества домов по этажности и количеству спален
count_table = df.groupby(['floors', 'bedrooms']).size().reset_index(name='count')

# Поиск категории домов с наибольшим количеством
max_category = count_table[count_table['count'] == count_table['count'].max()]

# Вывод результатов
print("Самая многочисленная категория домов:")
print(max_category)
```

    Самая многочисленная категория домов:
       floors  bedrooms  count
    3       1         3   5455


### 3.5 Постройте таблицу с подсчетом медианной стоимости домов в данных в зависимости от состояния дома и оценки дома


```python
# Создание сводной таблицы с медианной стоимостью домов
median_table = df.groupby(['condition', 'grade'])['price'].median().reset_index(name='median_price')

# Вывод результатов
print("Таблица с медианной стоимостью домов:")
print(median_table)
```

    Таблица с медианной стоимостью домов:
        condition  grade  median_price
    0           1      1        142000
    1           1      4        150000
    2           1      5        190000
    3           1      6        255000
    4           1      7        403500
    5           1      8        932500
    6           2      3        280000
    7           2      4        145000
    8           2      5        180000
    9           2      6        235000
    10          2      7        305000
    11          2      8        429000
    12          2      9        715000
    13          2     10       1752500
    14          3      3         75000
    15          3      4        205000
    16          3      5        234475
    17          3      6        265000
    18          3      7        357500
    19          3      8        485000
    20          3      9        689000
    21          3     10        890000
    22          3     11       1209500
    23          3     12       1807500
    24          3     13       2888000
    25          4      4        238525
    26          4      5        229975
    27          4      6        295000
    28          4      7        390000
    29          4      8        571250
    30          4      9        823500
    31          4     10       1030000
    32          4     11       1685000
    33          4     12       2125000
    34          4     13       5750000
    35          5      3        262000
    36          5      5        227450
    37          5      6        285475
    38          5      7        456000
    39          5      8        696000
    40          5      9       1078000
    41          5     10       1650000
    42          5     11       2050000
    43          5     12       1990000



```python

```
