```python
# LABORATORIO 2
```

!pip install pandasql
import numpy as np
import pandas as pd
heroes = pd.read_csv("heroes_information.csv")


```python
###instalar desde anaconda navigator######
from pandasql import *
```


```python
pysqldf = lambda q: sqldf(q,globals())
```


```python
query2 = " SELECT * FROM heroes limit 10"
```


```python
pysqldf(query2)
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
      <th>id</th>
      <th>name</th>
      <th>Gender</th>
      <th>Eye color</th>
      <th>Race</th>
      <th>Hair color</th>
      <th>Height</th>
      <th>Publisher</th>
      <th>Skin color</th>
      <th>Alignment</th>
      <th>Weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>A-Bomb</td>
      <td>Male</td>
      <td>yellow</td>
      <td>Human</td>
      <td>No Hair</td>
      <td>203.0</td>
      <td>Marvel Comics</td>
      <td>None</td>
      <td>good</td>
      <td>441.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Abe Sapien</td>
      <td>Male</td>
      <td>blue</td>
      <td>Icthyo Sapien</td>
      <td>No Hair</td>
      <td>191.0</td>
      <td>Dark Horse Comics</td>
      <td>blue</td>
      <td>good</td>
      <td>65.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Abin Sur</td>
      <td>Male</td>
      <td>blue</td>
      <td>Ungaran</td>
      <td>No Hair</td>
      <td>185.0</td>
      <td>DC Comics</td>
      <td>red</td>
      <td>good</td>
      <td>90.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Abomination</td>
      <td>Male</td>
      <td>green</td>
      <td>Human / Radiation</td>
      <td>No Hair</td>
      <td>203.0</td>
      <td>Marvel Comics</td>
      <td>None</td>
      <td>bad</td>
      <td>441.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Abraxas</td>
      <td>Male</td>
      <td>blue</td>
      <td>Cosmic Entity</td>
      <td>Black</td>
      <td>-99.0</td>
      <td>Marvel Comics</td>
      <td>None</td>
      <td>bad</td>
      <td>-99.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Absorbing Man</td>
      <td>Male</td>
      <td>blue</td>
      <td>Human</td>
      <td>No Hair</td>
      <td>193.0</td>
      <td>Marvel Comics</td>
      <td>None</td>
      <td>bad</td>
      <td>122.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>Adam Monroe</td>
      <td>Male</td>
      <td>blue</td>
      <td>None</td>
      <td>Blond</td>
      <td>-99.0</td>
      <td>NBC - Heroes</td>
      <td>None</td>
      <td>good</td>
      <td>-99.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>Adam Strange</td>
      <td>Male</td>
      <td>blue</td>
      <td>Human</td>
      <td>Blond</td>
      <td>185.0</td>
      <td>DC Comics</td>
      <td>None</td>
      <td>good</td>
      <td>88.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>8</td>
      <td>Agent 13</td>
      <td>Female</td>
      <td>blue</td>
      <td>None</td>
      <td>Blond</td>
      <td>173.0</td>
      <td>Marvel Comics</td>
      <td>None</td>
      <td>good</td>
      <td>61.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>9</td>
      <td>Agent Bob</td>
      <td>Male</td>
      <td>brown</td>
      <td>Human</td>
      <td>Brown</td>
      <td>178.0</td>
      <td>Marvel Comics</td>
      <td>None</td>
      <td>good</td>
      <td>81.0</td>
    </tr>
  </tbody>
</table>
</div>



# Nombre del primer superhéroe de la tabla heroes


```python
pregunta_1 = " SELECT name FROM heroes limit 1 "
```


```python
pysqldf(pregunta_1)
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
      <th>name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A-Bomb</td>
    </tr>
  </tbody>
</table>
</div>



# Cantidad de casas publicadoras


```python
pregunta_2="SELECT COUNT(DISTINCT Publisher) FROM heroes"
```


```python
pysqldf(pregunta_2)
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
      <th>COUNT(DISTINCT Publisher)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>24</td>
    </tr>
  </tbody>
</table>
</div>



# ¿Cuántos superhéroes miden más de 2 metros (200 cms)?


```python
pregunta_3 = " SELECT COUNT(*) FROM heroes WHERE height > 200"
```


```python
pysqldf(pregunta_3)
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
      <th>COUNT(*)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>59</td>
    </tr>
  </tbody>
</table>
</div>



# ¿Cuántos superhéroes son humanos y miden más de 2 metros (200 cms)?


```python
pregunta_4= pregunta_4 ="SELECT count(*) FROM heroes WHERE height > 200 AND race = 'Human'"
```


```python
pysqldf(pregunta_4)
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
      <th>count(*)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>12</td>
    </tr>
  </tbody>
</table>
</div>



# ¿Cuántos superhéroes pesan más de 100 lbs y menos de 200 lbs?


```python
pregunta_5= "SELECT COUNT(*)FROM heroes WHERE weight > 100 AND weight < 200"
```


```python
pysqldf(pregunta_5)
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
      <th>COUNT(*)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>98</td>
    </tr>
  </tbody>
</table>
</div>



# ¿Cuántos superhéroes tienen los ojos de color azul o rojo?


```python
pregunta_6="SELECT COUNT(*) FROM heroes WHERE `Eye color` = 'blue' OR `Eye color`='red'"
```


```python
pysqldf(pregunta_6)
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
      <th>COUNT(*)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>271</td>
    </tr>
  </tbody>
</table>
</div>



# ¿Cuántos superhéroes son Human, Mutant y tienen el pelo color Verde o son Vampiros con pelo Negro?


```python
pregunta_7="SELECT COUNT(*) FROM heroes WHERE (Race in ('Human', 'Mutant') AND `Hair color` = 'Green') OR (Race = 'Vampire' AND `Hair color` = 'Black')"
```


```python
pysqldf(pregunta_7)
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
      <th>COUNT(*)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>



# ¿Cuál es el nombre del primer superhéroe si ordeno la tabla por raza en orden descendente?


```python
pregunta_8 ="SELECT name FROM heroes ORDER BY race DESC LIMIT 1"
```


```python
pysqldf(pregunta_8)
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
      <th>name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Solomon Grundy</td>
    </tr>
  </tbody>
</table>
</div>



# ¿Cuántos superhéroes son de género masculino y cuántas de género femenino?

pregunta_9="SELECT Gender, COUNT(*) FROM heroes GROUP BY Gender"


```python
pysqldf(pregunta_9)
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
      <th>Gender</th>
      <th>COUNT(*)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>None</td>
      <td>29</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Female</td>
      <td>200</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Male</td>
      <td>505</td>
    </tr>
  </tbody>
</table>
</div>



# ¿Cuántas casas publicadoras tienen más de 15 superhéroes?


```python
pregunta_10="SELECT Publisher, count(name) FROM heroes GROUP BY Publisher HAVING COUNT(Publisher) > 15"
```


```python
pysqldf(pregunta_10)
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
      <th>Publisher</th>
      <th>count(name)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>DC Comics</td>
      <td>215</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Dark Horse Comics</td>
      <td>18</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Marvel Comics</td>
      <td>388</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NBC - Heroes</td>
      <td>19</td>
    </tr>
  </tbody>
</table>
</div>




