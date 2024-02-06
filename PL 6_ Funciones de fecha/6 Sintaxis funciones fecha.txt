
Profesor: Edgar A. Catalán Salgado

FUNCIONES DE FECHA

now(); regresa la fecha y hora actuales

extract(PARTEFECHA from FECHA). -  Extrae la PARTEFECHA  de FECHA 

to_char(fecha,parteFormatofecha) Convierte la fecha a texto, mostrando la parte de la fecha indicada con el formato indicado

date_part(PARTEFECHA, FECHA) - date_part(PARTEFECHA, FECHA)  Para obtener la diferencia entre dos fechas

FECHA + cast('NUMERO PARTEFECHA' as interval) Para sumar y restar valores a una fecha, se utilizan los operadores aritmŽticos +, -, y se especifica lo que se suma o resta (d’as, meses, etc)

   Select now() + cast('2 day' as interval)


age(Fecha1,Fecha2) Genera el intervalo transcurrido en tŽrminos de a–os, meses, d’as... entre las dos fechas


Ejemplo
    age(now(),(fechaalta))

ParteFEcha: 
milliseconds
second
minute
hour
day
dow     -- Day of week
week
month
quarter
year
decade
century
millennium


parteFormatofecha

Y,YYY	year in 4 digits with comma
YYYY	year in 4 digits
YYY	last 3 digits of year
YY	last 2 digits of year
Y	The last digit of year
IYYY	ISO 8601 week-numbering year (4 or more digits)
IYY	Last 3 digits of ISO 8601 week-numbering year
IY	Last 2 digits of ISO 8601 week-numbering year
I	Last digit of ISO 8601 week-numbering year
BC, bc, AD or ad	Era indicator without periods
B.C., b.c., A.D. ora.d.	Era indicator with periods
MONTH	English month name in uppercase
Month	Full capitalized English month name
month	Full lowercase English month name
MON	Abbreviated uppercase month name e.g., JAN, FEB, etc.
Mon	Abbreviated capitalized month name e.g, Jan, Feb,  etc.
mon	Abbreviated lowercase month name e.g., jan, feb, etc.
MM	month number from 01 to 12
DAY	Full uppercase day name
Day	Full capitalized day name
day	Full lowercase day name
DY	Abbreviated uppercase day name
Dy	Abbreviated capitalized day name
dy	Abbreviated lowercase day name
DDD	Day of year (001-366)
IDDD	Day of ISO 8601 week-numbering year (001-371; day 1 of the year is Monday of the first ISO week)
DD	Day of month (01-31)
D	Day of the week, Sunday (1) to Saturday (7)
ID	ISO 8601 day of the week, Monday (1) to Sunday (7)
W	Week of month (1-5) (the first week starts on the first day of the month)
WW	Week number of year (1-53) (the first week starts on the first day of the year)
IW	Week number of ISO 8601 week-numbering year (01-53; the first Thursday of the year is in week 1)
CC	Century e.g, 21, 22, etc.
J	Julian Day (integer days since November 24, 4714 BC at midnight UTC)
RM	Month in upper case Roman numerals (I-XII; >
rm	Month in lowercase Roman numerals (i-xii; >
HH	Hour of day (0-12)
HH12	Hour of day (0-12)
HH24	Hour of day (0-23)
MI	Minute (0-59)
SS	Second (0-59)
MS	Millisecond (000-999)
US	Microsecond (000000-999999)
SSSS	Seconds past midnight (0-86399)
AM, am, PM or pm	Meridiem indicator (without periods)
A.M., a.m., P.M. or p.m.	Meridiem indicator (with periods)
