# JavaFX

![enter image description here](http://programaenlinea.net/wp-content/uploads/2015/06/FX.png)
**JavaFX** es un conjunto de paquetes de gráficos y medios que permite a los desarrolladores diseñar, crear, probar, depurar e implementar aplicaciones de cliente enriquecido que operan de forma consciente en diversas plataformas.

Con JavaFX, puede crear muchos tipos de aplicaciones. Por lo general, son aplicaciones que cumplen con las redes que se despliegan en múltiples plataformas y muestran información en una interfaz de usuario moderna de alto rendimiento que incluye audio, vídeo, gráficos y animación.

***Puedes crear aplicaciones muy complejas de manera muy sencilla***

JavaFX está disponible en *Windows, Mac OS X y Linux.*

Las interfaces se pueden hacer en código _xml_ o bien de forma visual con _Scene Builder_, que se instala aparte en el caso de Linux.

# JavaSwing

**Swing** es una biblioteca de clases que permite crear interfaces gráficas de usuario en Java.
Swing forma parte del paquete estándar, no hace falta importar ningún fichero adicional en nuestros proyectos.
Existen dos elementos básicos para la creación de interfaces gráficas de usuario usando Swing:
 - Contenedores: Elementos capaces de albergar otros elementos.
 -  Componentes: Elementos que se añaden a contenedores.
  Usualmente los   componentes tienen aspecto gráfico, como un botón.
  
Swing proporciona tres tipos de contenedores de alto nivel. Esto significa que, cualquier otro contenedor que no sea de alto nivel, o componente, debe ir en su interior.

Estos tres contenedores de alto nivel son: **JFrame, JDialog y JApplet**
• JFrame: Se visualiza como una ventana principal con marco y barra de título.

 - **JDialog**: Se visualiza como una ventana independiente de la ventana principal para mostrar información, como por ejemplo el contenido de un directorio.
-**JApplet** Permite crear aplicaciones con interface gráfica que se ejecutan en el contexto de un navegador web.

## JavaFX vs JavaSwing

The file explorer is accessible using the button in left corner of the navigation bar. You can create a new file by clicking the **New file** button in the file explorer. You can also create folders by clicking the **New folder** button.

## 

![enter image description here](https://cdn.educba.com/academy/wp-content/uploads/2018/11/Java-Swing-vs-Java-FX.jpg)

## Calculadora 
package sample;  
  
import javafx.fxml.FXML;  
import javafx.scene.control.Button;  
import javafx.scene.control.TextField;  
  
  
import java.util.Stack;  
  
public class Evaluar {  
  
   
  private TextField display;  
  
  
  private Button igual;  
  
   public static double EvaluarExp(){  
        String posfija="456*+"; //la expresión a evaluar  
  
  double num1,num2,valor=0; //creamos un double para los operandos y uno para el resultado de realizar la operación de dichos operandos.  
  Stack pila = new Stack(); // creamos la pila  
  for(int i=0;i<posfija.length();i++){ //hacemos un for con el num de iteraciones del tamñano de la longitud  
  char entrada=posfija.charAt(i); //la variable entrada toma el char que se encuentre en la posicion i en la expresión  
  if(!esOperador(entrada)){ //evaluamos si no es un operador  
  double num = new Double(entrada + "");// lo convertimos a double ya que lo estabamos manejando en char  
  
  pila.push(num);//lo metemos a la pila  
  }else{// si sí es un operador entonces  
  
  num2= (double) pila.pop(); //se saca de la pila el ultimo numero ingresado  
  num1= (double) pila.pop(); //se saca de la pila el penultimo numero  
  valor=(char)RealizarOperacion(entrada,num1,num2); //se realiza la operacion adecuada y se asigna a valor  
  pila.push(valor);//ingresar el resultado a la pila  
  }  
        }  
        System.out.println((int)valor); ;//se imprime el resultado  
  return 0;  
    }  
//evalua si es un operador  
  private static boolean esOperador(char entrada){   
  
        if(entrada=='*'||entrada=='/'||entrada=='+'||entrada=='-'||entrada=='^'){  
            return true;  
        }  
        return false;  
    }  
    //Realiza la operación adecuada.  
  private static double RealizarOperacion(char entrada,double num1,double num2){  
  

  if(entrada=='*')return num1*num2;  
        if(entrada=='/')return num1/num2;  
        if(entrada=='+')return num1+num2;  
        if(entrada=='-')return num1-num2;  
        if(entrada=='^')return Math.pow(num1,num2);  
        return 0;  
    }  
  
}

    

