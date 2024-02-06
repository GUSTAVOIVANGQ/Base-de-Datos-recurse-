
PROYECCION
 	Select Dato1[, dato2....]  
	From OrigenDatos

        Para mostrar todos los campos se usa * como comodin en la parte del select
         Select *
         from NombreTabla
 Donde Dato puede ser:
   -- Numero
   -- Texto 
   -- Atributo
   -- Operacion aritmetica
   -- Funcion que regrese un valor
   -- Subconsulta que regrese un valor      

OrigenDatos:
  -- Tabla
  -- Vista
  -- Funcion que regrese tablas

-- 1. Muestra apellido paterno, materno y nombre
	Select ApPat, ApMat, nombre
	from tblClientes;

USO DE ALIAS para poner titulos a las columnas

	Select Campo as 'titulo de columna'
	from NombreTabla

-- 1. Cambia el titulo de la columna codigo postal a CODIGO POSTAL
	Select CodPost as 'CODIGO POSTAL'
	from TblClientes;

--COLUMNAS GENERADAS
	Concatenacion:
		||  Concatena cadenas de caracteres 
	Operadores aritmeticos:
		+  Suma
		-  Resta
		*  Multiplicacion
		/  Division
		() Sirven para agrupar expresiones aritmeticas e
 				   imponer un orden en su ejecucion

--1. Muestra el nombre completo de los clientes
Select nombre || ' ' ||  ApPaterno || ' ' || ApMaterno 
from TblClientes

CASTEO DE DATOS
Para cambiar el tipo de dato, se utiliza la siguiente sintaxis
Dato::NuevoTipo de dato

Ejemplo
Select nombre, deuda, deuda::Varchar(50), deuda::char(50)
From cliente 


