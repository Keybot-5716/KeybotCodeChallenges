Solución 2 Ejercicio 7
======================

.. code-block:: java
   :linenos:

   import java.util.ArrayList;
    import java.util.List;
    import java.util.Scanner;

    public class factorial2 {
        public static void main(String[] args) {
            // Pedimos un número a través de scanner
            Scanner scn = new Scanner(System.in);

            // Ponemos un número entero
            int factorial = scn.nextInt();

            // Revisamos si es negativo
            if (factorial < 0){
                System.out.println("No se puede un número negativo");
            }else{    
                // Creamos una lista en la cual vamos a almacenar los valores hasta llegar al número recibido
                List<Integer> factores = new ArrayList<>();

                // Hacemos un bucle en el cual pongamos todos los números hasta llegar al número recibido
                for (int i = 1; i <= factorial; i++) {
                    factores.add(i);
                }

                // Creamos una variable para poner el resultado
                int resultado = 1;
                // El bucle for each itera sobre cada elemento de la lista de factores y multiplica hasta número
                for (int num : factores) {
                    resultado *= num;
                }
                // Cerramos el escanner
                scn.close();

                // Imprimimos el valor 
                System.out.println(resultado);
            }
        }
    }

