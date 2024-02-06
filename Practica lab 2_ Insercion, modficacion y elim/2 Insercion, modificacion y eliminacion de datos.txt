INSERCION, MODIFICACION Y ELIMINACION DE DATOS

Para la insercion de datos se utiliza la siguiente sintaxis:

insert into NombreTabla (campo1, Campo2,..., CampoN)
                 values (valor1, Valor2,..., valorN)


Donde 
  CampoX, es el nombre de cualquier campo de la tabla
  ValorX, es el valor que va a tener el campo


Para actualizar datos la instruccion es:

   update NombreTabla
       Set campo=valor[,campo2=valor2]
      [where condicion];


Para eliminar datos de una tabla la instruccion es:

    delete from NombreTabla
    [where Condicion];

En la sintaxis lo encerrado entre corchetes es opcional, en este caso si se omite la condicion TODOS los registros se elimiaran o actualizaran segun sea el caso, por lo que hay que ser cuidadosos.

Una condicion b‡sica se compone de la siguiente forma:
		Dato1 OperadorComparacion Dato2

 Dato puede ser un campo, valor o cualquier expresion que nos de un valor valido (funciones, expresiones aritmeticas, consulta, etc) 	

    Operadores de comparacion
	>	Mayor que
	>= 	Mayor o igual que
	=	Igual que
	<=	Menor igual que
	<	Menor que
	<> o !=	Diferente que



Ejemplos

  1. Da de alta al empleado Edgar Catalan Salgado, que nacio el 17 de marzo de 1981 a las 4:35 AM, con un salario de 10000
      insert into Empleados(Nombre, ApPaterno, ApMaterno, FechaNacimiento, Salario) 
                    values ('Edgar', 'Catalan', 'Salgado', '1981/03/17,0435', 10000)

  2. Modifica el salario de los empleados que se llaman Edgar para que ahora ganen 15000
       update Empleados
        set Salario= 15000
        where nombre='Edgar'
 
 3 Borra a los empleados que llaman Edgar
     Delete from Empleados
          where nombre='Edgar'


