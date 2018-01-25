# mi-programa-favorito-en-java

Es difícil escoger cuál sería mi programa favorito de los que he hecho hasta ahora, no porque haya hecho muchos y fascinantes, sino porque todavía no he encontrado **ese** programa que me haya proporcionado un sentimiendo de autorrealización. No obstante, si he encontrado un programa que me ha despertado un sentimiento lúdico y que podría decirse que le tengo una pizca de ***apego***, ya que ha salido de mi puño y tecla.

## La máquina tragaperras.

```Java
import java.util.Scanner;
public class Pruebas2 {
 public static void main(String[] args) {
    int figuras = 0;
    int monedas = 3;
    int figura1 = 0;
    int figura2 = 0;
    int figura3 = 0;
    String tirada;
    System.out.println("Bienvenido a la máquina tragaperras.");
    System.out.println("Tiene " + monedas + " monedas");
    Scanner s = new Scanner(System.in);

//    while (monedas == 0); { //no entiendo por qué no funciona el sistema de monedas
    do {

      System.out.println("Pulse 'i' para insertar una moneda ");
      tirada = s.nextLine();
//      monedas--;

      if (tirada.equals("i")) {

        for (int i = 1; i <= 3; i++) {

          figuras = (int) (Math.random() * 5) + 1;

          switch (figuras) {
            case 1:
              System.out.print(" Corazon ");
              break;
            case 2:
              System.out.print(" Diamante ");
              break;
            case 3:
              System.out.print(" Herradura ");
              break;
            case 4:
              System.out.print(" Campana ");
              break;
            case 5:
              System.out.print(" Limón ");
              break;
            default:
          }

          switch (i) {
            /**
             * En esta parte consigo que los strings anteriores tengan un valor
             * para poder así aplicarles condicionales
             */
            case 0:
              figura1 = figuras;
              break;
            case 1:
              figura2 = figuras;
              break;
            case 2:
              figura3 = figuras;
              break;
            default:
          }
        }

        if ((figura1 != figura2) && (figura2 != figura3) && (figura1 != figura3)) {
          System.out.println("\nLo siento, ha perdido.");
          monedas--;
          System.out.println("\nTiene " + monedas + " monedas");
        } else if ((figura1 == figura2) && (figura2 == figura3)) {
          System.out.println("\nEnhorabuena, ha ganado 10 monedas.");
          monedas += 10;
          System.out.println("\nTiene " + monedas + " monedas");
        } else {
          System.out.println("\nBien, ha recuperado su moneda.");
          monedas++;
          System.out.println("\nTiene " + monedas + " monedas");
        }
      } else {
        System.out.println("Debes pulsar la 'i' ");
      }
    } while (monedas > 0);
    System.out.println("Vuelva mañana");
  }

}
```
En el código podemos observar líneas comentadas que no hacen más que mostrar lo que una vez fué (y sigue siendo) un programador novato que no era capaz de ver el más simple error ni aunque se lo pusieran delante de sus narices.

*Bueno dejémonos de chorradas*

El ejercicio es sencillo, hay que realizar una máquina tragaperras con ```Math.random()``` y que el programa sepa cuando se da una combinación ganadora, o no, y que lo imprima por pantalla. Con una pequeña particularidad que **quise** añadir, un sistema de monedas, es decir, una virtualización de lo que sería jugar a una máquina tragaperras en la realidad, así que cuando te quedas sin monedas, ya no puedes jugar.

<img src="imagenes/hulio1.png">