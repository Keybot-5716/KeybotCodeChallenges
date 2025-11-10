Solución 3 Ejercicio 7
======================

Explicación:
IntStream es una secuencia de valores enteros en la cual puedes hacer funciones como el filtrado, mapeo, reducción, aumento, entre muchas  otras.

.. important::
    **IntBinaryOperator** representa una operación entre 2 números operandos enteros y que produce un número entero como resultado.

    **Función acomulativa asociativa** es una operación binaria que cuenta con que el orden en el que agrupas los operandos no afecta el resultado (las únicas operaciones que cuentan con esto es la suma y la multiplicación).

    **OptionalInt** es un contenedor en el cual te puede decir si es que hay un entero o no.

Por ejemplo, .rangeClosed toma como primer parámetro el valor inicial al que va a empezar y como segundo el valor al que se quiere acercar el primero (esto lo podemos pensar como si fuera un for loop en el que iniciamos una variable i a un número cualquiera, la condición es que ese número inicial es menor que el número al que queremos llegar y aumentamos ese número más 1). 

.reduce puede tomar 1 o dos parámetros, cuando solamente toma 1 es siempre un **IntBinaryOperator**, usa una **Función acomulativa asociativa** y regresa un **OptionalInt** describiendo el valor reducido si es que hay; mientras que cuando le pones 2 parámetros toma como primero un número entero que sirve como identidad y por segundo un **IntBinaryOperator**, este toma la función acumulativa asociativa y el número de identidad proporcionado y regresa un valor reducido. 

Por último se hace uso de la expresión lambda adentro de .reduce despues de poner que el valor nuevo dentro de este loop sea 1, el lambda tiene como objetivo pasar como argumento un **IntBinaryOperator** sin ser este un **IntBinaryOperator**, en paréntesis tenemos 2 argumentos, el primero sirve para ir actualizando la identidad y el segundo va a tomar los valores que va ir aumentando del .rangeClosed, posteriormente se hace una multiplicación de estos 2 números.

.. code-block:: java
   :linenos:

   import java.util.Scanner;
    import java.util.stream.IntStream;

    public class factorial3 {
        public static void main(String[] args) {
            Scanner scn = new Scanner(System.in);
            int factorial = scn.nextInt();
            int resultado = IntStream.rangeClosed(1, factorial).reduce(1, (a, b) -> a * b);
            System.out.println(resultado);
            scn.close();
        }
    }

