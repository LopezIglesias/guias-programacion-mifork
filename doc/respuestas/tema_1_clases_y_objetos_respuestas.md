<!--
Posible prompt:
<prompt>
Tengo un cuestionario con preguntas sobre "Clases y Objetos". Debes tener en cuenta que los conocimientos previos que tengo (y por tanto tus respuestas deben ser adaptadas), son:
- C/C++ sin orientación a objetos.
- Temas de Java previos: ninguno.

Cada respuesta debe tener entre 2 - 4 párrafos de longitud (sin contar los trozos de código).

Por favor, escribe en impersonal las respuestas.

</prompt>
----
-->

# TEMA 1. Clases y objetos

## 1. ¿Cuáles son las cuatro características básicas de la programación orientada a objetos? Describe brevemente cada una

### - Abstracción: olvidarse de los detalles, ayuda a manejar mejor temas complejos y facilita el mantenimiento de código.
### - Encapsulación: unir información y funciones sobre esa información en el mismo código. Sirve para ocultar información y facilitar la abstacción
### - Herencia: permite crear jerarquías.
### - Polimorfismo: misma función con distintas implementaciones.


## 2. Cita cuatro lenguajes populares que permitan la programación orientada a objetos

### Python, C++,C# ,JavaScript, Java, PHP, Rust.


## 3. Los paradigmas anteriores a la POO, ¿Qué es la **programación estructurada**? y, todavía mejor, ¿Qué es la **programación modular**?

### Ensamblador: secuencia de instrucciones y saltos arbitrarios.
### Estructurada: introduce secuencias, bifurcaciones e iteraciones. Elimina los saltos arbitrarios.
### Modular: introduce librerias, paquetes, interfaz,... . Ayuda a encapsular y reutilizar código.

## 4. ¿Qué tres elementos definen a un objeto en programación orientada a objetos?

### - Identidad: todo objeto tiene identidad única
### - Estado (atributos): valor de los atributos del objeto.
### - Comportamiento (módulos): funciones que puede hacer el objeto.

## 5. ¿Qué es una clase? ¿Es lo mismo que un objeto? ¿Qué es una instancia? ¿Todos los lenguajes orientados a objetos manejan el concepto de clase?

### -Clase: molde que define el estado y comportamiento.
### - Objetos o instancias: cada una de las instancias concretas de una clase.


## 6. ¿Dónde se almacenan en memoria los objetos? ¿Es igual en todos los lenguajes? ¿Qué es la **recolección de basura**? 

### Los objetos suelen almacenarse en memoria dinámica, una zona que se reserva durante la ejecución del programa cuando se crean instancias de clases. En lenguajes como Java, esta memoria corresponde al heap, un espacio gestionado automáticamente por la máquina virtual. A diferencia de C, donde la reserva dinámica se hace manualmente con malloc o new, en Java no se especifica dónde se ubica el objeto, ya que su administración queda completamente delegada al tiempo de ejecución. Las referencias a esos objetos suelen almacenarse en la pila (stack), similar a cómo se manejan los punteros en C.
### No todos los lenguajes gestionan la memoria de la misma manera. En C++ los objetos pueden crearse tanto en la pila como en el heap según cómo se declaren, mientras que en lenguajes como Java o Python, los objetos residen siempre en memoria dinámica. Otros lenguajes de bajo nivel permiten un control más explícito sobre la ubicación exacta del objeto, mientras que los lenguajes de alto nivel priorizan la abstracción y simplificación del manejo de memoria.
### La recolección de basura (garbage collection) es un mecanismo automático que identifica y libera memoria ocupada por objetos que ya no son accesibles por el programa. Su finalidad es evitar fugas de memoria sin requerir que el programador libere los recursos manualmente, lo que reduce errores típicos de lenguajes como C, como el uso de memoria liberada o la falta de liberación. En Java, el recolector de basura se ejecuta periódicamente y determina qué objetos ya no tienen referencias activas.


## 7. ¿Qué es un método? ¿Qué es la **sobrecarga de métodos**? 

### Un método es una función asociada a una clase que define un comportamiento que los objetos de esa clase pueden realizar. En Java desempeña un papel equivalente a las funciones en C, pero integrado dentro de la estructura de un objeto. Así, un método puede acceder a los atributos del objeto y operar sobre ellos, lo que permite relacionar datos y operaciones de forma organizada. En la práctica, los métodos representan las acciones que un objeto puede ejecutar, como calcular un valor, modificar su estado interno o interactuar con otros objetos del programa.
### La sobrecarga de métodos consiste en definir varios métodos con el mismo nombre dentro de una misma clase, pero diferenciados por la lista de parámetros. Esta técnica permite ofrecer distintas versiones de una acción según las necesidades del contexto, sin crear nombres diferentes para cada variación. Por ejemplo, se puede disponer de un método que sume dos enteros y otro que sume tres, manteniendo el mismo nombre “sumar” pero cambiando el número o tipo de parámetros.


## 8. Ejemplo mínimo de clase en Java, que se llame Punto, con dos atributos, x e y, con un método que se llame `calculaDistanciaAOrigen`, que calcule la distancia a la posición 0,0. Por sencillez, los atributos deben tener visibilidad por defecto. Crea además un ejemplo de uso con una instancia y uso del método

 
### class Punto {
###     // Atributos 
###     double x;
###     double y;
###
###     // Constructor 
###     Punto(double x, double y) {
###         this.x = x;
###         this.y = y;
###     }
###
###     double calculaDistanciaAOrigen() {
###         return Math.sqrt(x * x + y * y);
###     }
### }

### Exemplo de uso:

### public class Main {
###     public static void main(String[] args) {
###         Punto p = new Punto(3, 4);
###         System.out.println("Distancia al origen: " + p.calculaDistanciaAOrigen());
###     }
### }




## 9. ¿Cuál es el punto de entrada en un programa en Java? ¿Qué es `static` y para qué vale? ¿Sólo se emplea para ese método `main`? ¿Para qué se combina con `final`?

### El punto de entrada de un programa en Java es siempre el método main, cuyo encabezado estándar es
### public static void main(String[] args). Este método es la primera función que ejecuta la Máquina Virtual de Java cuando se inicia un programa.
### La palabra clave static indica que el método o atributo pertenece a la clase y no a una instancia concreta. En el caso de main, esto permite que la JVM lo invoque sin necesidad de crear un objeto primero, lo cual sería imposible si no fuera estático. En general, static se utiliza para atributos compartidos entre todos los objetos y para métodos que realizan operaciones independientes del estado interno de una instancia.
### La combinación de static con final se emplea para definir constantes. final indica que un valor no puede modificarse después de asignarse. Cuando un atributo se declara como static final, significa que es un valor compartido por toda la clase y que además no se puede modificar durante la ejecución.

## 10. Intenta ejecutar un poco de Java de forma básica, con los comandos `javac` y `java`. ¿Cómo podemos compilar el programa y ejecutarlo desde linea de comandos? ¿Java es compilado? ¿Qué es la **máquina virtual**? ¿Qué es el *byte-code* y los ficheros `.class`?

### Para compilar y ejecutar desde línea de comandos se suele crear un archivo HelloWorld.java cuyo nombre coincide con la clase pública. 
### Javapublic class HelloWorld {    public static void main(String[] args) {        System.out.println("Hola, Java");    }}Mostrar más líneas
### Luego, se compila con javac HelloWorld.java, lo que genera HelloWorld.class. Para ejecutarlo se usa java HelloWorld (sin la extensión .class ni la ruta del archivo). Si el archivo está en un paquete, por ejemplo package demo;, el comando de ejecución debe invocarse desde el directorio raíz del proyecto con java demo.HelloWorld, y conviene respetar la estructura de carpetas (demo/HelloWorld.java). Si se requiere añadir rutas de clases/jars, se ajusta el classpath con -cp (Linux/macOS) o -classpath (Windows).
### Java no es “compilado a código máquina nativo” en el sentido tradicional como en C/C++; en su lugar, es compilado a bytecode intermedio y luego ejecutado por una máquina virtual. A efectos prácticos, el modelo es mixto: el bytecode puede interpretarse y también compilarse en caliente a nativo mediante un compilador JIT (Just-In-Time). Así se logra portabilidad (mismo bytecode en distintos sistemas) sin renunciar del todo al rendimiento, porque las partes “calientes” se optimizan dinámicamente durante la ejecución.
### La Máquina Virtual de Java (JVM) es el entorno de ejecución que carga bytecode, gestiona memoria (con garbage collection), aplica verificaciones de seguridad y realiza la ejecución (interpretación y/o JIT). A diferencia de un binario nativo, el programa Java no conversa directamente con el sistema operativo; lo hace a través de la JVM, que ofrece una abstracción común sobre plataformas diferentes. Esto explica por qué el mismo .class puede ejecutarse en Windows, Linux o macOS sin recompilar, siempre que exista una JVM compatible instalada.
### El bytecode es el formato intermedio generado por javac, contenido en los ficheros .class. Es un conjunto de instrucciones para una máquina virtual hipotética (la JVM), no para una CPU real. Cada clase fuente suele producir al menos un .class homónimo; clases internas o anidadas generan archivos adicionales (por ejemplo, Outer$Inner.class). En tiempo de carga, el class loader resuelve estas clases, la JVM las verifica por seguridad y tipo, y posteriormente las interpreta o compila con el JIT para ejecutarlas eficientemente.


## 11. En el código anterior de la clase `Punto` ¿Qué es `new`? ¿Qué es un **constructor**? Pon un ejemplo de constructor en una clase `Empleado` que tenga DNI, nombre y apellidos

### new es el operador que reserva memoria en el montón (heap) y crea una instancia de una clase, devolviendo una referencia al objeto. A diferencia de C/C++ procedural, donde se podría usar malloc para reservar memoria “en bruto”, en Java new no solo reserva, sino que además invoca el constructor de la clase para dejar el objeto en un estado válido. La referencia devuelta se almacena en una variable del tipo de la clase (o de una superclase/interfaz compatible).
### Un constructor es un método especial que inicializa el objeto en el momento de su creación. Se caracteriza por tener el mismo nombre que la clase y no declarar tipo de retorno (ni siquiera void). Puede estar sobrecargado (varias variantes con diferentes parámetros) y puede ser privado (por ejemplo, en patrones como factory o singleton). Si no se define ningún constructor, el compilador provee un constructor por defecto sin parámetros; en cuanto se define alguno, el por defecto deja de generarse automáticamente.

### public class Empleado {
###     private final String dni;
###     private final String nombre;
###     private final String apellidos;
###     
###     public Empleado(String dni, String nombre, String apellidos) {
###         if (dni == null || dni.isBlank()) {
###             throw new IllegalArgumentException("El DNI no puede ser nulo o vacío");
###         }
###         this.dni = dni;
###         this.nombre = nombre;
###         this.apellidos = apellidos;
###     }
###     
###     public Empleado(String dni) {
###         this(dni, "", "");
###     }
### 
###     public String getDni() { return dni; }
###     public String getNombre() { return nombre; }
###     public String getApellidos() { return apellidos; }
### }


## 12. ¿Qué es la referencia `this`? ¿Se llama igual en todos los lenguajes? Pon un ejemplo del uso de `this` en la clase `Punto`

### this es la referencia al objeto actual dentro del contexto de una instancia. Permite acceder a los campos y métodos de ese objeto y se usa, entre otras cosas, para desambiguar entre parámetros del método y atributos con el mismo nombre (this.x frente a x). En Java, this también puede retornarse para encadenar llamadas (patrón fluent), pasarse como argumento a otros métodos, y usarse en encadenamiento de constructores (this(...)) dentro de la misma clase. En C++ existe igualmente this, pero es un puntero (de tipo Clase*), mientras que en Java es una referencia no modificable; en C# también se llama this y en Python se emplea el identificador convencional self como primer parámetro explícito, no una palabra reservada.
### Además de la desambiguación, this resulta útil para expresar de forma clara que se está operando sobre el estado del objeto receptor, especialmente cuando se mezclan variables locales, parámetros y atributos. Conviene notar que this no está disponible en contextos estáticos (por ejemplo, dentro de un método static), porque no hay instancia asociada. En constructores, this(...) permite reutilizar otra sobrecarga para centralizar la inicialización y evitar duplicación, mientras que super(...) invoca al constructor de la superclase.


### public class Punto {
###     private double x;
###     private double y;
### 
###     public Punto() {
###         this(0.0, 0.0);
###     }
###     public Punto(double x, double y) {
###         this.x = x;
###         this.y = y;
###     }
### }



## 13. Añade ahora otro nuevo método que se llame `distanciaA`, que reciba un `Punto` como parámetro y calcule la distancia entre `this` y el punto proporcionado

### public double distanciaA(Punto otro) {
###         double dx = this.x - otro.x;
###         double dy = this.y - otro.y;
###         return Math.sqrt(dx * dx + dy * dy)
### }



## 14. El paso del `Punto` como parámetro a un método, es **por copia** o **por referencia**, es decir, si se cambia el valor de algún atributo del punto pasado como parámetro, dichos cambios afectan al objeto fuera del método? ¿Qué ocurre si en vez de un `Punto`, se recibiese un entero (`int`) y dicho entero se modificase dentro de la función? 

### En Java, todo el paso de parámetros es por valor, pero en el caso de los objetos ese “valor” es la referencia al objeto, no el objeto en sí. Esto significa que, cuando un método recibe un Punto, se recibe una copia de la referencia, pero ambas referencias apuntan al mismo objeto en memoria. Por tanto, si dentro del método se modifica algún atributo del Punto recibido, esos cambios sí afectan al objeto original, porque no se está copiando el contenido del objeto, sino solo la referencia que lo señala.
### Sin embargo, aunque ambos nombres refieran al mismo objeto, la referencia no puede redirigirse desde fuera. Es decir, si dentro del método se hace p = new Punto(...), esa reasignación no afecta a la variable original que llamó al método; solo cambia la copia de la referencia dentro del método. Lo único que se propaga al exterior son las modificaciones sobre el estado del objeto apuntado (sus atributos), no las reasignaciones de la referencia.
### En contraste, cuando el parámetro es un tipo primitivo como int, lo que se pasa es simplemente una copia del valor numérico. Si dentro del método se modifica ese int, el cambio no afecta a la variable original del llamador. En otras palabras, los tipos primitivos se comportan igual que en C/C++ cuando se pasan por valor: cualquier modificación interna se pierde al salir del método.


## 15. ¿Qué es el método `toString()` en Java? ¿Existe en otros lenguajes? Pon un ejemplo de `toString()` en la clase `Punto` en Java

### toString() es el método que devuelve una representación textual de un objeto. Todas las clases en Java heredan uno desde Object; su versión por defecto produce algo poco útil (el nombre de la clase y un hash en hex). Por eso, se sobrescribe para obtener salidas legibles, útiles para logging, depuración o mostrar información al usuario. La anotación @Override ayuda a que el compilador verifique que realmente se está sobrescribiendo el método correcto.


### public String toString() {
###         return "Punto{x=" + x + ", y=" + y + "}";
###     }



## 16. Reflexiona: ¿una clase es como un `struct` en C? ¿Qué le falta al `struct` para ser como una clase y las variables de ese tipo ser instancias?


### Un struct no tiene constructor ni metodos.
### Una clase puede verse, en una primera aproximación, como una evolución del struct de C, ya que ambos permiten agrupar datos bajo un mismo tipo. Sin embargo, una clase no se limita a contener datos: incorpora también comportamiento, es decir, métodos que operan sobre esos datos. Mientras el struct de C es puramente un contenedor de campos, una clase combina estado + operaciones, lo que permite encapsular lógica y garantizar que los objetos se manipulen de forma coherente y segura.
### Al struct de C le faltan varios elementos esenciales para comportarse como una clase completa. En primer lugar, carece de constructores, por lo que no puede asegurar que sus campos queden inicializados adecuadamente cuando se crea una variable de ese tipo. Además, no tiene modificadores de acceso (private, public) que controlen qué partes del código pueden modificar sus campos, dificultando la encapsulación. Tampoco admite métodos asociados directamente al tipo, por lo que toda operación sobre un struct debe escribirse como una función externa, sin una relación formal con el propio tipo.
### Finalmente, en C no existe el concepto de instancia tal como se entiende en la programación orientada a objetos. Aunque una variable de tipo struct almacena datos, no dispone de un entorno que gestione automáticamente la memoria en el montón, el enlace entre datos y funciones o las normas internas de inicialización y comportamiento. En una clase de Java o C++, en cambio, cada objeto nace mediante un constructor, vive en la memoria conforme a las reglas del lenguaje y posee métodos que describen su comportamiento, lo que permite un diseño más modular y orientado a abstraer la complejidad.


## 17. Quitemos un poco de magia a todo esto: ¿Como se podría “emular”, con `struct` en C, la clase `Punto`, con su función para calcular la distancia al origen? ¿Qué ha pasado con `this`?

### Se puede “emular” una clase Punto en C usando un struct para los datos y funciones externas que operan sobre él. No existen métodos asociados al tipo ni constructores, pero puede definirse una función de inicialización y pasar un puntero al struct como primer parámetro, que hace el papel de this. Para calcular la distancia al origen x2+y2\sqrt{x^2 + y^2}x2+y2​, se usa hypot o sqrt(x*x + y*y) de <math.h>.
### Aquí, this no existe como palabra reservada: su papel lo desempeña explícitamente el puntero al struct (Punto* p) que se pasa a cada función “método”. Este enfoque implica escribir funciones con un namespace manual en el nombre (por ejemplo, Punto_*) y perder encapsulación (los campos son públicos). También se asume la gestión manual de memoria e inicialización (no hay new ni garbage collection), por lo que corresponde al programador garantizar que el struct está correctamente inicializado antes de usarlo.
