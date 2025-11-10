Solución 1 Ejercicio 7
======================

Primeramente se piensa en el problema como 

.. code-block:: java
   :linenos:

   import java.util.Scanner;

   public class factorial {
       public static void main(String[] args) {
           // Leer el número entero como un long por si es muy largo el número
           Scanner scn = new Scanner(System.in);
           long factorial = scn.nextLong();
           scn.close();
           // Tener una condición por si es negativo
           if (factorial < 0){
               System.out.println("No se permite números negativos");
           }else{
               // Creamos una variable para la multiplicación
               long resultado = 1;
               // Creamos un bucle en el cual mientras no sea 0 el factorial va a ponerlo en la variable de multiplicación y va a restarle uno a ese factorial
               for (; factorial != 0; factorial--){
                   resultado *= factorial;
               }
               // Lo imprimimos en terminal
               System.out.println(resultado);
           }
       }
   }
