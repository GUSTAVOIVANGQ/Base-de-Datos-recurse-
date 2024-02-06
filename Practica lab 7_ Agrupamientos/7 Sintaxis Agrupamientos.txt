
Alumno:__________________________
Grupo:___________________________
Profesor: Edgar A. Catalán Salgado



1 FUNCIONES DE AGRUPAMIENTO

Las funciones de agrupamiento, de grupo, de agregado o multilinea, son un conjunto de funciones que como su nombre lo indica, reciben un conjunto de datos como par‡metro y realizan alguna funci—n sobre ese grupo, tales como encontrar el m‡ximo o el promedio de los valores. Entre las funciones de grupo mas comunes tenemos:

SUM (Dato) Calcula la suma del grupo
AVG (Dato) Calcula el promedio del grupo
Max (Dato) Obtiene el valor mas grande del grupo
MIN (Dato) Obtiene el valor mas peque–o del grupo
COUNT (Dato) Cuenta los valores no nulos del grupo
COUNT(*) 

Las funciones de agrupamiento trabajan sobre el resultado de la consulta en la que est‡n, si no ponemos condiciones aplica sobre la totalidad de registros.

Algo importante a remarcar es que las funciones de agrupamiento, reciben un conjunto  de datos, los cuales existen en la tabla y generan un œnico valor de salida, por lo cual tambiŽn se conocen como de resumen. Esto tiene la implicaci—n de que no se pueden revolver datos de resumen con datos puros de la base datos directamente en la misma consulta. Por ejemplo, si se calcula el promedio de deuda de los 10 clientes actualmente registrado y pedimos un nombre, el compilador no sabe cual nombre se debe mostrar.

Funciones de grupo sobre los registros resultado de una consulta

Sintaxis

select FAgrupamiento(Campo)
from tabla
[where condici—n]

Ejemplo

Muestra el numero de clientes registrados, el numero de crŽditos asignados y la suma de la deuda de los clientes

Select count(*) as "Clientes Registrados"
       , Count(credito) as "Creditos asignados"
       , sum(deuda) as "sumatoria Deuda clientes"
From cliente

Muestra el numero de clientes registrados, el numero de crŽditos asignados y la suma de la deuda de los clientes de la delegaci—n Iztacalco

Select count(*) as "Clientes Registrados"
       , Count(credito) as "Creditos asignados"
       , sum(deuda) as "sumatoria Deuda clientes"
  From cliente
  where direccion_delegacion='Iztacalco'

Muestra el numero de clientes registrados, el numero de crŽditos asignados y la suma de la deuda de los clientes cuya deuda esta entre 10000y 15000

Select count(*) as "Clientes Registrados"
       , Count(credito) as "Creditos asignados"
       , sum(deuda) as "sumatoria Deuda clientes"
	   , 2 as "TTT" 
  From cliente
where deuda between 10000 and 15000  


Criterios de agrupamiento

Un criterio de agrupamiento establece la forma en que se van agrupar los registros, asi por ejemplo podemos crear grupos de acuerdo a pa’s o estado o mismo apellido o tipo sanguinio. Incluso pueden ser por edad o cualquiera otro que nos interese. En otras palabras se generara un grupo, para cada valor diferente del criterio de agrupamiento, y de cada grupo podemos obtener la informaci—n que necesitemos usando las funciones de agrupamiento
Para establecer los criterios a travŽs de los que se van a crear los grupos se utiliza la clausula group by.
Cabe resaltar que como el criterio de agrupamiento es el mismo para todos los miembros de un mismo grupo, entonces podemos seleccionarlo en la consulta

Sintaxis
select FAgrupamiento(Campo), CriterioDeAgrupamiento
from tabla
group by CriterioDeAgrupamiento

Ejemplo

select COUNT(Nombre),Delegacion
from Cliente
group by Delegacion


CONDICIONANDO GRUPOS

Podemos observar que la clausula group by genera una tabla de resumen a partir de los datos puros, es decir , aunque en la tabla cliente existan nombre, primer apellido, segundo apellido, crŽdito y deuda; en la tabla de resumen, solo existir‡n los criterios de agrupamiento y el resultado de las funciones de agrupamiento aplicadas. 

Debido a lo anterior, la parte de la condici—n where, determina los registros de la tabla base a ser considerados para geenerar los grupos, por lo que en esa parte no se puede utilizar ninguna funci—n de agrupamiento.  

Sin embargo hay veces que se quiere restringir los grupos a mostrar, por ejemplo las delegaci—n con mas de 3 clientes, las ventas de mas de 15000 en total, etc. Para hacer esto se utiliza la clausula having, la cual permite establecer una condici—n a los grupos que se mostraran como resultado. En s’ntesis, having es lo mismo que el where, pero trabaja en el resultado de la clausula group by, por lo que solo existen las funciones de agrupamiento y los criterios de agrupamiento


Sintaxis

Ejemplo
Muestra las delegaciones con mas de 5 clientes
select COUNT(IdCliente),Delegacion
from Cliente
group by Delegacion
having COUNT(IdCliente)>5

