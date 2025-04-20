# RETO ALURA STORE
Este codigo es muy sencillo y busca presentar un analisis de datos que puedan ayudar al dueño de Alura Store para decidir que sucursal poner en venta de las 4 analizadas .

# DEPENDENCIAS
<p>
	Este codigo solo requiere dos dependencias:
		<li> Matplotlib </li>
		<li> Pandas</li>
		Las cuales se instalan en *Google Collab* con la siguiente linea de codigo:
`
	!pip install #Libreria
`
</p>


# FUNCIONES
Comprender las funciones es muy sencillo, el nombre da a entender lo que realizan cada una.

## PANDAS
```python
import pandas as pd

url = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_1%20.csv"
url2 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_2.csv"
url3 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_3.csv"
url4 = "https://raw.githubusercontent.com/alura-es-cursos/challenge1-data-science-latam/refs/heads/main/base-de-datos-challenge1-latam/tienda_4.csv"

tienda = pd.read_csv(url)
tienda2 = pd.read_csv(url2)
tienda3 = pd.read_csv(url3)
tienda4 = pd.read_csv(url4)
```
Aqui se muestra el como utilizando la funcion *read* de la libreria *Pandas* importamos las bases de datos de las sucursales al codigo para poder realizar los analisis requeridos.

##Análisis de facturación
```python
def facturacionTotal(tienda):
  total = tienda['Precio'].sum()
  return total
```
Esta funcion aprovecha *Pandas* para realizar una suma total de la columna "Precio" para obtener la facturacion total de la sucursal. El parametro que se utiliza al llamar la funcion es la variable que tiene almacenada el enlace con la base de datos. Al final la funcion nos retorna el valor obtenido.

##Ventas por categoría
```python
def ventaPorCategoria(tienda):
  conteo = tienda['Categoría del Producto'].value_counts()
  return conteo
```
Para obtener las ventas por categoria, se utiliza la funcion *value counts* de *Pandas*, funcion cual nos retorna la frecuencia con la que se repite un valor, en este caso una cadena la cual seria el nombre de la categoria del producto que se ha vendido. El parametro que se utiliza al llamar la funcion es la variable que tiene almacenada el enlace con la base de datos. Al final la funcion nos retorna la cantidad de veces que se repiten todas las cadenas que estan almacenadas en esta columna.

##Calificación promedio de la tienda
```python
def calificacionPromedio(tienda):
  promedio = tienda['Calificación'].sum() / len(tienda['Calificación'])
  return promedio
```
Funcion muy sencilla en la cual se calcula el promedio sumando las calificaciones de todas las ventas divido por la cantidad de ventas. Esto se logra utilizando las funciones* sum* para sumar todos los valores numericos de la columna y la funcion *len* para obtener la cantidad total de ventas realizadas. l parametro que se utiliza al llamar la funcion es la variable que tiene almacenada el enlace con la base de datos. Al final la funcion nos retorna el promedio.

## Productos mas y menos vendidos
```python
def conteoProductos(tienda):
  conteo = tienda['Producto'].value_counts()
  return conteo
```
Funciona igual que la funcion **Ventas por categoría**, solo que esta vez se utiliza la columna Producto.

## Envio Promedio por tienda
```python

def envioPromedio(tienda):
  promedio = tienda['Costo de envío'].sum() / len(tienda['Costo de envío'])
  return promedio

```
Funciona igual que la funcion **Calificación promedio de la tienda**, solo que esta vez sustuimos la columna por la de Costo de envio y nos retorna cuanto se calcula en promedio por cada envio que realiza la tienda.
