

SELECCION DE REGISTROS
	select campo1,campo2
	from tabla
	where condicion

	Condicion se compone de la siguiente forma:
		Dato1 OperadorComparacion Dato2

	Dato puede ser un campo, valor o cualquier expresion que nos de un valor valido (funciones, expresiones aritmeticas, consulta, etc) 	

    Operadores de comparacion
	>	Mayor que
	>= 	Mayor o igual que
	=	Igual que
	<=	Menor igual que
	<	Menor que
	<> o !=	Diferente que


--1.- Los clientes con el nombre de Edgar
Select nombre ,Credito 
from clientes 
where nombre='Edgar'


SELECCION CON OPERADORES LOGICOS 

	NOT Condicion  Pide que no se cumpla la condicio
        Operadores logicos binarios: 
		Condicion1 AND Condicion2 pide que se cumplan las 2 condiciones
		Condicion1 OR Condicion2  pide que se cumpla por lo menos una de las dos

	Podemos usar parentesis para agrupar condiciones, de distintas formas, por ejemplo:
		(C1 OpLogicoBin C2) OpLogicoBin C3
		(C1 OpLogicoBin C2) OpLogicoBin (C3 OpLogicoBin C4)
		not (C1 OpLogicoBin C2)

-- Los clientes que no viven en Iztacalco
Select nombre, delegaci—n
From cliente
Where not delegacion='iztacalco'

-- Los que se llaman Edgar o Juan
Select nombre, delegaci—n
From cliente
Where nombre='Edgar' or nombre='Juan'

-- Los que tienen un credito entre 5000 y 10000
Select nombre, crŽdit
From cliente
Where credito>5000 and credito<10000



OPERADORES ESPECIALES

	Campo between LimiteInferior AND LimiteSuperior  La condicion se cumple cuando el valor en campo esta entre los limites indicados
	Campo in (Dato1, Dato2, etc)	La condicion se cumple cuando el valor en campo es cualquiera de los datos especificados

-- Credito entre 5000 y 10000 con between
Select nombre, crŽdit
from clientes
where credito between 5000 and 10000

-- Los de la delegacion Iztacalco, Coyoacan o Benito Juarez, con el op in
Select nombre, delegaci—n
from clientes
where delegation in ('Iztacalco', 'Coyoacan', 'Benito Juarez')


OPERADORES PARA BUSQUEDA DE PATRONES

Operador Like

	select nombre
	From	Tabla
	where nombre like 'texto'

	En el texto puede ir cualquiera de los siguientes comodines
		% 0 o mas caracteres, cualquiera que estos sean
		_ Un solo caracter, cualquiera que sea

Operador Similar to

	select nombre
	From	Tabla
	where nombre similar to 'texto'

Adicionalmente similar to tambiŽn permite los siguientes caracteres de las expresiones regulares POSIX:

	En el texto puede ir cualquiera de los siguientes comodines

	"*" Especifica 0 o mas instancias de lo que le precede. Si ponemos "_*" equivale a % en like 
	"+" Especifica 1 o mas instancias de lo que le precede.
	"?" Especifica 0 o 1 instancias de lo que le precede. Si ponemos "_?" equivale a _ en like 

Los corchetes permiten extender la funcionalidad del "_" de la siguiente forma:
veces. 
	"[CCC...]" Especifica un conjunto de caracteres  validos en una posicion 

      Las llaves permiten especificar el numero de veces lo que le precede:
	"{N,M}", el cual indica el numero minimo (N) y maximo (M) de veces debe aparecer lo que le precede. si se especifica solo un numero {N} es equivalente a {N,}, que lo podriamos interpretar como minimo N, maximo lo que sea.

     Podemos especificar cadenas opcionales con el s’mbolo "|":
	"Cadena1|Cadena1" indica que pude aparecer la cadena 1 o la 2
    
    Finalmente podemos agrupar elementos para tratarlos como uno solo utilizando parŽntesis. 

Les pongo los siguientes ejemplos:

Suponga los nombre Ana, Pedro, Edgar, Yalsiria y Blanca

Muestra a los que tienen por lo menos una A
	Select Nombre
	from tblClientes
	where nombre like'%A%' or nombre like '%a%';
	
	Select Nombre
	from tblClientes
	where nombre similar to '%(A|a)%';

	Select Nombre
	from tblClientes
	where nombre similar to '_*(A|a)_*';

Muestra a los que terminan con a
	Select Nombre
	from tblClientes
	where nombre like'%a';

	Select Nombre
	from tblClientes
	where nombre similar to '_*a';


Muestra los nombres que su segundo caracter es d 
	Select Nombre
	from tblClientes
	where nombre like '_d%';

	Select Nombre
	from tblClientes
	where nombre similar to '_d';


Muestra los nombres que su penultimo caracter es a
	Select Nombre
	from tblClientes
	where nombre like '%a_';

	Select Nombre
	from tblClientes
	where nombre similar to '_*a_';


Muestra a los que empiezan con vocal
	Select Nombre
	from tblClientes
	where nombre similar to '[AEIOU]_*';


Muestra a los que NO empiezan con vocal
	Select Nombre
	from tblClientes
	where not nombre similar to '[AEIOU]_*';

Muestra a los que NO empiezan con vocal
	Select Nombre
	from tblClientes
	where nombre not similar to '[AEIOU]_*';



SELECCION DE NULOS

Un valor nulo es un valor especial que indica que dicho valor es desconocido, es diferente de un 0 y de una cadena vacia en el sentido de que cualquier operacion que involucre a un nulo va a dar como resultado nulo.

numero/0=0  				numero/NULO=NULO
concat ('texto1', '')='Texto1'		concat('Texto1', NULO)=NULO

Por su naturaleza el valor nulo necesita de tratamiento especial, empezando por el condicionamito de registros, el cual se tiene que hacer de la siguiente forma:

select nombre, credito
from tblClientes
where credito is null

