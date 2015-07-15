# lp_811.html
<!DOCTYPEhtml>
<html> 
<head> 

<link rel="stylesheet" type="text/css" href="style.css"> 
<script language="javascript">
</script>

<body> 
<form name="forma1"> 
РАСЧЁТ ВАЛЮТЫ <br/> <br/>
Введите натуральное число копеек: <input type="text" name="n" size="10" />
<br /><br />
<input type="button" value="вычислить" onclick="otvet();" /> 
<br /><br />
ответ: <input type="text" name="rub" size="10" /> руб. <input type="text" name="kop" size="1" /> коп. <br /><br /> 
<script>

function otvet()

{ var rub = document.forma1.n.value; <!-- тэг формы-->
var k = 0;  //счетчик для сравнения длины . Если вся вводимая строка из цифр, то выполняем программу. если нет, то выводит сообщение об ошибке. 
var i; 

for (i=0 ; i<=rub.length ; i++) 
{
if(rub.charCodeAt(i)>=48 && rub.charCodeAt(i) <= 57) // если символы введены в коде ASCII в промежутке от 48 до 57, то k увеличиваем на 1. 
{ 
k++; 
}
else 
{
break;
}
}

if(k == rub.length) 
{


	if(rub.length == 1) // если длина введенного символа =1, то в копейку добавляется 0, чтобы число было двухзначным и в рубли записываетсяя 0.
	{
	 document.forma1.rub.value = "0";
 	 document.forma1.kop.value = "0" + rub;
 	}
	else
	{
	 if(rub.length == 2) // если длина введенного символа =2, то в рубль записывается 0, а в копейки введенное число.
     {
	  document.forma1.rub.value = "0";
 	  document.forma1.kop.value = rub.slice(-2);
     }
	 else
         {           // в остальных случаях, когда длина больше 2. в копейки записывается последние 2 числа. а в рубль n.length-2.
		  document.forma1.kop.value = rub.slice(-2); 
		  document.forma1.rub.value = rub.substring(0,rub.length-2);
		 }
}

}
else // если символы вводятся вне диапозона кода ASCII от 48 до 57. то программа выдает сообщение об ошибке и просит вводит натуральные числа. А также обнуляет значения в рублях и копейках и в n.
{
 alert("Ошибка! Вводите натуральные числа")
 document.forma1.n.value = "";
 document.forma1.rub.value = "";
 document.forma1.kop.value = "";
}
}


</script>
