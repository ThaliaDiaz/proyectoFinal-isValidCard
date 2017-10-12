## TARJETA DE CREDITO VALIDA

Crea una web que pida, por medio de un prompt(), el número de una tarjeta de crédito y confirme su validez según el algoritmo de Luhn.
### ALGORITMO DE LUHN

La fórmula verifica un número contra su dígito de chequeo incluido, el cual el usualmente agregado a un número de cuenta parcial para generar el número de cuenta completo. Este número de cuenta debe pasar la siguiente prueba:

A partir del dígito de chequeo incluido, el cual está a la derecha de todo el número, ir de derecha a izquierda duplicando cada segundo dígito.
Sumar los dígitos del resultado: (ejemplo: 10 = 1 + 0 = 1, 14 = 1 + 4 = 5) juntos con los dígitos sin duplicar del número original.
Si el total de módulo 10 es igual a 0 (si el total termina en cero), entonces el número es válido de acuerdo con la fórmula Luhn, de lo contrario no es válido.

### **Consideraciones Específicas**

Tu código debe estar compuesto por 1 función: **isValidCard**
El usuario no debe poder ingresar un campo vacío

### DIAGRAMA DE FLUJO

![recursos](assets/image.png)

### PSEUDOCODIGO

*Algoritmo isValidCard
	Repetir
		var numCard<-prompt("Ingrese su numero de tarjeta");
		var arr<-numCard.split('');
		Si (arr[0]==''|| numCard=='' || numCard.length!==16) Entonces
			var op<-false;
		SiNo
			Si typeof(parseInt(arr[0]))=='number' Entonces
				Escribir 'El número de tarjeta ingresada es: '+numCard;
                Funcion msg <- Nombre ( numCard )
					Escribir arrInvertido <-arr.reverse();
					var prod<-1;
					var sum<-0;
					Para i<-0 Hasta arr.length Con Paso i+1 Hacer
						Si i%2==0 Entonces
							prod=arr[i]*2;
							Si prod<10 Entonces
								arr[i]<-prod;
							SiNo
								resul=Math.floor(prod/10)+(prod%10);
								arr[i]<-resul;
							Fin Si
						SiNo
							arr[i]<-arr[i]*1;
						Fin Si
					Fin Para
					Leer arr;
					Para i<-0 Hasta arr.length Con Paso i+1 Hacer
						sum=sum+arr[i];
					Fin Para

					Si sum%10==0 Entonces
						msg='Tarjeta de crédito válida';
					SiNo
						msg='Tarjeta de crédito no válida';
					Fin Si
				Fin Funcion
				Escribir isValidCard(numCard);
				op<-true;
			Fin Si
		Fin Si
	Hasta Que op==false;
FinAlgoritmo
