<!--
Posible prompt:
<prompt>
Tengo un cuestionario con preguntas sobre "Encapsulación". Debes tener en cuenta que los conocimientos previos que tengo (y por tanto tus respuestas deben ser adaptadas), son:
- C/C++ sin orientación a objetos.
- Temas de Java previos: Clases y Objetos.

Cada respuesta debe tener entre 2 - 4 párrafos de longitud (sin contar los trozos de código).

Por favor, escribe en impersonal las respuestas.

</prompt>
----
-->
# TEMA 2. Encapsulación

## 1. En Programación Orientada a Objetos (POO), ¿Qué buscan la **encapsulación** y **la ocultación** de información? Enumera brevemente algunas ventajas de la ocultación de información.

### En Programación Orientada a Objetos, la encapsulación y la ocultación de información buscan limitar el acceso directo a los datos internos de un objeto, concentrando su manipulación a través de métodos específicos. Esta idea establece una separación clara entre cómo funciona internamente un objeto y cómo puede utilizarse desde el exterior, evitando que otras partes del programa dependan de detalles internos susceptibles de cambiar. De esta forma, se promueve que el estado de un objeto solo pueda modificarse mediante operaciones controladas, lo que ayuda a mantener la coherencia y validez de los datos.

### La ocultación de información complementa a la encapsulación al restringir qué atributos y métodos se hacen visibles desde fuera de la clase. No se pretende únicamente impedir el acceso directo, sino también reducir la complejidad expuesta al programador que utilice esa clase. Esto conduce a interfaces más claras y sencillas, donde solo se muestran los elementos necesarios para el uso correcto del objeto, manteniendo en segundo plano los detalles internos que podrían resultar irrelevantes o confusos.

### Entre las ventajas de la ocultación de información se incluye una mayor seguridad del estado interno, ya que se impide que otros módulos modifiquen valores sin control. Además, facilita el mantenimiento del software, puesto que los cambios internos de una clase no afectan al código que la utiliza, siempre que la interfaz pública permanezca estable. También contribuye a una reducción de errores, al evitar usos indebidos de los datos, y favorece la modularidad, permitiendo desarrollar, probar y mejorar cada clase de manera independiente.


## 2. ¿Qué se entiende por la **interfaz pública** de un objeto o clase en POO? Describe brevemente cómo se relaciona con la ocultación de información.

### La interfaz pública de un objeto o clase se entiende como el conjunto de métodos y atributos accesibles desde fuera de dicha clase. Representa la “puerta de entrada” a las funcionalidades que la clase ofrece, y define exactamente qué operaciones pueden realizar otros objetos o módulos del programa sobre ella. En lenguajes como Java, esta interfaz se establece principalmente mediante el uso del modificador public aplicado a métodos que se desea exponer, mientras que el estado interno suele mantenerse privado.

### La interfaz pública actúa como un contrato: especifica cómo puede utilizarse la clase sin necesidad de conocer su implementación interna. Esto permite que el usuario de la clase trabaje con ella de forma segura y coherente, apoyándose exclusivamente en las operaciones previstas por su diseñador. Además, una interfaz pública bien definida contribuye a que el código sea más claro, ya que delimita lo que es esencial para interactuar con el objeto.

### Su relación con la ocultación de información es directa, ya que esta última implica restringir el acceso a los detalles internos para que sean manipulados únicamente a través de la interfaz pública. Mantener los atributos como private y exponer únicamente los métodos necesarios asegura que el objeto controle cómo debe modificarse su estado. De este modo, se evita que partes externas del programa alteren información delicada o dependan de elementos que podrían cambiar en el futuro, lo que facilita el mantenimiento y mejora la robustez del software.


## 3. Brevemente: ¿Por qué hay que ser conscientes y diseñar con cuidado la **interfaz pública** de una clase? ¿Es fácil cambiarla?

### Diseñar con cuidado la interfaz pública de una clase es fundamental porque constituye el conjunto de elementos mediante los cuales el resto del programa interactúa con dicha clase. Si la interfaz está mal pensada, puede obligar a exponer más información de la necesaria o permitir usos incorrectos del objeto, lo que incrementa la posibilidad de errores y dificulta mantener la coherencia interna del estado. Una interfaz clara, reducida y bien estructurada facilita el uso correcto de la clase y delimita con precisión qué operaciones están permitidas.

### Además, la interfaz pública actúa como un contrato estable entre la clase y el código que depende de ella. Cuando muchas partes del sistema utilizan una misma clase, un diseño deficiente impone restricciones que luego serán difíciles de eliminar sin introducir incompatibilidades. Por este motivo, conviene planificar qué métodos deben ser realmente públicos, qué responsabilidades debe asumir cada uno y qué detalles deben permanecer ocultos mediante modificadores de acceso.

### Cambiar la interfaz pública no suele ser fácil, especialmente si ya está siendo utilizada por múltiples módulos del programa. Una modificación puede exigir rehacer partes importantes del código que dependen de la clase, generar errores inesperados o forzar adaptaciones complejas para mantener la compatibilidad. Por ello, se considera buena práctica exponer solamente lo estrictamente necesario, de forma que los cambios internos puedan realizarse sin afectar al exterior y se preserve la estabilidad a largo plazo del software.


## 4. ¿Qué son las **invariantes de clase** y por qué la ocultación de información nos ayuda?

### Las invariantes de clase son condiciones lógicas que deben cumplirse siempre para que el estado interno de un objeto se considere válido. Estas condiciones se mantienen verdaderas antes y después de la ejecución de cualquier método público de la clase. Por ejemplo, si una clase representa una cuenta bancaria, una invariante podría ser que el saldo nunca sea negativo. Las invariantes actúan como reglas internas que garantizan que el objeto se mantenga en un estado coherente durante toda su vida útil.

### La ocultación de información ayuda porque permite que solo los métodos de la propia clase modifiquen su estado interno. Al impedir que código externo altere directamente los atributos, se garantiza que cualquier cambio pase por métodos que pueden verificar, mantener o restaurar las invariantes. De este modo, si una operación no cumple las condiciones necesarias para que la invariante siga siendo cierta, la clase tiene la oportunidad de corregir el error, lanzar una excepción o impedir la modificación.

### Al controlar todas las modificaciones del estado a través de la interfaz pública, resulta más sencillo asegurar que las invariantes no se rompen accidentalmente. La clase puede validar sus datos, asegurar límites, impedir asignaciones erróneas o aplicar transformaciones necesarias antes de actualizar el estado final. En consecuencia, la ocultación de información se convierte en una herramienta fundamental para proteger la consistencia interna y evitar comportamientos impredecibles en el programa.


## 5. Pon un ejemplo de una clase `Punto` en `Java`, con dos coordenadas, `x` e `y`, de tipo `double`, con un método `calcularDistanciaAOrigen`, y que haga uso de la ocultación de información. ¿Cuál es la interfaz pública de la clase `Punto`? ¿Qué significa `public` y `private`?

### La interfaz pública de Punto está formada por los miembros public que pueden usarse desde fuera de la clase: el constructor Punto(double, double) y el método funcional calcularDistanciaAOrigen(). Los valores x e y no se pueden invocar directamente desde otros módulos. Esta separación permite cambiar la implementación interna (por ejemplo, añadir setX/setY o almacenar en otra estructura) sin romper el código cliente que solo depende de la interfaz.

### En cuanto a los modificadores, public significa accesible desde cualquier lugar (código externo, otros paquetes, etc.), y se usa para definir la API de la clase. Por su parte, private significa accesible únicamente desde dentro de la propia clase, y se utiliza para ocultar el estado y los detalles internos (como los campos x e y). Esta ocultación de información impide que código externo manipule libremente los datos, obligando a pasar por métodos controlados, lo que favorece mantener invariantes de clase y evita dependencias frágiles con la implementación.

public class Punto {
    private double x;
    private double y;

    public Punto(double x, double y) {
        this.x = x;
        this.y = y;
    }

    public double calcularDistanciaAOrigen() {
        return Math.sqrt(x * x + y * y);
    }
}



## 6. En Java, ¿A quiénes se pueden aplicar los modificadores `public` o `private`?

### En Java, los modificadores public y private pueden aplicarse principalmente a clases, atributos, métodos y constructores. Su función es definir el nivel de visibilidad de cada uno de estos elementos y, por tanto, controlar desde qué partes del programa pueden utilizarse. Esto permite establecer fronteras claras entre lo que forma parte de la interfaz pública y lo que debe mantenerse oculto dentro de la implementación interna de una clase.

### El modificador public puede aplicarse tanto a clases de primer nivel (siempre y cuando el archivo contenga solo una clase pública) como a clases internas, además de a cualquier atributo, método o constructor. Declarar un elemento como public implica que es accesible desde cualquier otro punto del programa, incluso desde otros paquetes, lo que permite que forme parte de la API que ofrece la clase hacia el exterior.

### El modificador private, por el contrario, solo puede aplicarse a los miembros de una clase (atributos, métodos y constructores), pero no a una clase de primer nivel. Una clase interna sí puede ser privada, pero no una clase que esté al nivel superior del archivo .java. Declarar algo como private implica que solo puede utilizarse desde dentro de la propia clase, lo que resulta esencial para la encapsulación y la protección del estado interno.

### Gracias a esta distinción, el programador puede controlar qué partes de la clase se exponen al exterior y cuáles quedan protegidas, lo que permite construir software más modular, más seguro frente a usos incorrectos y más fácil de mantener. 


## 7. En POO, la visibilidad puede ser pública o privada, pero ¿existen más tipos de visibilidad? ¿Qué ocurre en Java? ¿Y en otros lenguajes?

### En POO, aunque suele hablarse de visibilidad pública y privada como los extremos más claros, existen más niveles de acceso en función del lenguaje. Algunos lenguajes orientados a objetos permiten distinguir grados intermedios para controlar con más precisión qué partes del código pueden interactuar con una clase. Estos niveles adicionales suelen estar diseñados para equilibrar la encapsulación con la flexibilidad necesaria en proyectos grandes, donde varias clases relacionadas pueden necesitar compartir ciertos detalles internos sin exponerlos completamente al exterior.

### En Java, además de public y private, existen los modificadores protected y (default) o “paquete”. El nivel protected permite que un atributo o método sea accesible desde clases del mismo paquete y también desde subclases, incluso si están en paquetes distintos. Por otro lado, la visibilidad por defecto —cuando no se especifica ningún modificador— limita el acceso únicamente a las clases que se encuentran dentro del mismo paquete. Estos niveles adicionales permiten crear una exposición más controlada, especialmente útil cuando las clases forman parte de un mismo módulo y deben colaborar sin romper la encapsulación hacia el exterior.

### En otros lenguajes, los esquemas de visibilidad pueden variar. Por ejemplo, en C++, además de public, private y protected, existen matices adicionales cuando se hereda con diferentes tipos de acceso. Lenguajes como Python no imponen visibilidad estricta, pero emplean convenciones como guiones bajos para indicar elementos internos, mientras que otros, como C#, disponen de niveles adicionales (internal, protected internal, etc.) que combinan restricciones entre ensamblados y herencia. En conjunto, estas variaciones muestran que la visibilidad en POO no se limita a dos opciones, sino que se adapta a las necesidades de diseño propias de cada lenguaje y del tipo de proyecto que se desarrolla.


## 8. Responde: Los miembros de instancia privados de un objeto están ocultos para (a) otras clases o (b) otras instancias, aunque sean de la misma clase. Pon un ejemplo añadiendo un método `calcularDistanciaAPunto(Punto otro)` y explica la respuesta.

### Los miembros de instancia privados están ocultos para otras clases (opción a), pero no para otras instancias de la misma clase cuando el acceso se realiza desde el propio código de la clase. En Java, el modificador private restringe la visibilidad al cuerpo de la clase que declara los miembros; por tanto, cualquier método de Punto puede leer los campos privados de cualquier objeto Punto que reciba como argumento, ya que sigue operando dentro de la clase Punto. Lo que queda prohibido es que código externo a la clase acceda a esos campos.


public class Punto {
    private double x;
    private double y;

    public Punto(double x, double y) {
        this.x = x;
        this.y = y;
    }

    public double calcularDistanciaAOrigen() {
        return Math.sqrt(x * x + y * y);
    }

    public double calcularDistanciaAPunto(Punto otro) {
        double dx = this.x - otro.x;  
        double dy = this.y - otro.y; 
        return Math.sqrt(dx * dx + dy * dy);
    }
}

### private protege frente a otras clases, no frente a otros objetos del mismo tipo cuando el acceso se realiza desde el código de la propia clase. Esto permite implementar operaciones “entre pares” (como comparaciones, copias o distancias) sin romper la encapsulación, ya que las reglas de integridad y las invariantes de clase siguen centralizadas y controladas por los métodos de Punto.

## 9. ¿Qué son los métodos "getter" y "setter" en los lenguajes orientados a objetos?

### Los métodos getter y setter son funciones que permiten acceder y modificar de forma controlada los atributos privados de una clase en los lenguajes orientados a objetos. Se emplean como parte de la interfaz pública de la clase para ofrecer un mecanismo seguro de acceso, evitando que el código externo manipule directamente los campos internos. Un getter se usa para devolver el valor de un atributo, mientras que un setter permite asignarle un nuevo valor, normalmente aplicando validaciones o restricciones cuando es necesario.

### Los getters y setters tienen como objetivo reforzar la encapsulación y proteger las invariantes de clase. Al obligar a que cualquier modificación del estado se realice mediante un método específico, se garantiza que la clase pueda comprobar si el nuevo valor es válido, evitar estados inconsistentes o ejecutar lógica adicional cuando cambia un atributo. En lugar de exponer directamente los campos, se ofrece un acceso más seguro y flexible que facilita el mantenimiento del código.

### Además, este enfoque permite modificar la implementación interna sin afectar al código que utiliza la clase. Si en algún momento se decide cambiar el tipo interno de un atributo, añadir validaciones o registrar modificaciones, basta con ajustar la lógica de los setters o getters sin alterar la interfaz pública. De esta manera, el uso de estos métodos contribuye a una mayor modularidad y a que los objetos mantengan su coherencia interna durante toda su vida útil.


## 10. Cuando nos referimos a que la ocultación de información mejora la "seguridad" del programa, ¿nos referimos a que no pueda ser "hackeado"?

### No, cuando se afirma que la ocultación de información mejora la “seguridad” del programa, no se hace referencia a protegerlo frente a ataques externos o a evitar que sea “hackeado”. En este contexto, el término “seguridad” se entiende en un sentido interno al diseño del software, es decir, como la capacidad de un programa para mantener su estado consistente, evitar errores lógicos y reducir la probabilidad de usos incorrectos por parte de otras partes del código. Por tanto, la seguridad aquí no es de tipo criptográfico ni relacionada con ciberseguridad, sino con la robustez y fiabilidad del diseño orientado a objetos.

### La ocultación de información contribuye a esta seguridad interna porque restringe la modificación directa del estado de los objetos y obliga a interactuar con ellos mediante métodos controlados. Esto permite validar entradas, asegurar invariantes y mantener la coherencia interna, lo que reduce la posibilidad de que el programa entre en estados inválidos o difíciles de depurar. En otras palabras, se protege el programa de sí mismo, evitando errores comunes derivados de un uso inapropiado de los datos.

### Este tipo de seguridad, por tanto, está orientado a facilitar el mantenimiento, la extensibilidad y la estabilidad del software, no a prevenir ataques malintencionados. Un código mal encapsulado puede funcionar, pero es más propenso a comportamientos impredecibles, fallos silenciosos y dependencias frágiles entre módulos. De ahí la importancia de distinguir entre seguridad en el sentido de buen diseño de software y seguridad en el sentido de protección frente a amenazas externas, que es un ámbito completamente distinto.


## 11. ¿Qué diferencia hay entre **miembro de instancia** y **miembro de clase**? ¿Los miembros de clase también se pueden ocultar?

### Un miembro de instancia es aquel que pertenece a cada objeto individual creado a partir de una clase. Cada instancia mantiene su propia copia de esos atributos y métodos, de modo que el estado puede diferir entre objetos. Por ejemplo, en la clase Punto, los campos x e y son miembros de instancia: cada objeto Punto tiene sus propias coordenadas, independientes de las demás instancias. Este tipo de miembro representa información o comportamiento asociado al estado particular de cada objeto.

### Por otro lado, un miembro de clase (también llamado estático, usando el modificador static) pertenece a la clase en sí misma, no a las instancias. Esto implica que existe una única copia compartida por todos los objetos de esa clase. Los miembros estáticos se usan para información o comportamientos que no dependen del estado individual, como contadores globales, constantes o métodos utilitarios. Por ejemplo, una constante static final double PI = 3.14159 sería un miembro de clase que todos los objetos comparten sin duplicación.

### En cuanto a la visibilidad, los miembros de clase también pueden ocultarse usando los mismos modificadores de acceso (private, public, protected, o visibilidad por defecto). Declarar un miembro estático como private significa que solo puede utilizarse dentro del propio cuerpo de la clase, del mismo modo que ocurre con un miembro de instancia privado. Esto permite encapsular datos o comportamientos globales evitando que otras partes del programa los manipulen libremente, lo cual es útil para mantener coherencia y control sobre información compartida.

### En conjunto, la diferencia fundamental reside en a quién pertenecen y cuántas copias existen: los miembros de instancia son propios de cada objeto, mientras que los miembros de clase existen una sola vez; y ambos pueden protegerse mediante ocultación para preservar la integridad del diseño orientado a objetos.


## 12. Brevemente: ¿Tiene sentido que los constructores sean privados?

### Sí, tiene sentido que los constructores sean privados en ciertos patrones de diseño y situaciones concretas. Un constructor privado impide que otras clases creen instancias directamente, lo que permite controlar estrictamente cuándo y cómo se generan los objetos. Esta técnica se emplea, por ejemplo, cuando se desea limitar la creación de instancias o centralizarla en un conjunto concreto de métodos. De esta manera, la clase mantiene el control total sobre su propio ciclo de vida y evita usos indebidos por parte del código cliente.


## 13. ¿Cómo se indican los **miembros de clase** en Java? Pon un ejemplo, en la clase `Punto` definida anteriormente, para que incluya miembros de clase que permitan saber cuáles son los valores `x` e `y` máximos que se han establecido en todos los puntos que se hayan creado hasta el momento.

### En Java, los miembros de clase son aquellos que pertenecen a la clase y no a cada objeto concreto; se declaran con la palabra clave static. Se accede a ellos mediante el nombre de la clase (por ejemplo, Punto.maxX) y comparten su valor entre todas las instancias. Esto contrasta con los miembros de instancia (sin static), que son propios de cada objeto. Además, se pueden combinar con modificadores de acceso (private, public) para mantener la encapsulación y exponer solo lo necesario a través de métodos de acceso (getters) o métodos estáticos.

### Para registrar los valores máximos de x e y establecidos en cualquier objeto Punto creado, se pueden definir campos static que se actualicen en el constructor y en los setters. De este modo, cada vez que se cree o modifique un punto, los máximos globales se recalculan. Para respetar la encapsulación, conviene mantener estos campos como private y ofrecer métodos public static de solo lectura para consultarlos.


public class Punto {
    private int x;
    private int y;

    private static int maxX = Integer.MIN_VALUE;
    private static int maxY = Integer.MIN_VALUE;

    public Punto(int x, int y) {
        this.x = x;
        this.y = y;
        actualizarMaximos(x, y);
    }

    public int getX() { return x; }
    public int getY() { return y; }

    public void setX(int x) {
        this.x = x;
        actualizarMaximos(this.x, this.y);
    }

    public void setY(int y) {
        this.y = y;
        actualizarMaximos(this.x, this.y);
    }

    public static int getMaxX() { return maxX; }
    public static int getMaxY() { return maxY; }

    private static void actualizarMaximos(int x, int y) {
        if (x > maxX) maxX = x;
        if (y > maxY) maxY = y;
    }
}



## 14. Como sería un método factoría dentro de la clase `Punto` para construir un `Punto` a partir de dos coordenadas, pero que las redondee al entero más cercano. Escribe sólo el código del método, no toda la clase ¿Has usado `static`? 


public static Punto desdeCoordenadasRedondeadas(double x, double y) {
    int rx = (int) Math.round(x);
    int ry = (int) Math.round(y);
    return new Punto(rx, ry);
}



## 15. Cambia la implementación de `Punto`. En vez de dos `double`, emplea un array interno de dos posiciones, intentando no modificar la interfaz pública de la clase.

public class Punto {
    private final double[] coords = new double[2];

    private static int maxX = Integer.MIN_VALUE;
    private static int maxY = Integer.MIN_VALUE;

    public Punto(double x, double y) {
        this.coords[0] = x; 
        this.coords[1] = y; 
    }

    public double getX() { return this.coords[0]; }
    public double getY() { return this.coords[1]; }

    public void setX(int x) {
        this.coords[0] = x;
        actualizarMaximos(this.coords[0], this.coords[1]);
    }

    public void setY(int y) {
        this.coords[1] = y;
        actualizarMaximos(this.coords[0], this.coords[1]);
    }

    public static int getMaxX() { return maxX; }
    public static int getMaxY() { return maxY; }

    private static void actualizarMaximos(int x, int y) {
        if (x > maxX) maxX = x;
        if (y > maxY) maxY = y;
    }
}



## 16. Si un atributo va a tener un método "getter" y "setter" públicos, ¿no es mejor declararlo público? ¿Cuál es la convención más habitual sobre los atributos, que sean públicos o privados? ¿Tiene esto algo que ver con las "invariantes de clase"?

### La presencia de getters y setters públicos no justifica que el atributo sea también público. Incluso cuando se ofrece acceso de lectura y escritura, declarar el atributo como private permite mantener el control sobre cómo se accede a él. Los métodos permiten añadir validaciones, comprobaciones de rango, cálculos derivados o futuras modificaciones sin afectar al código que utiliza la clase. Si el atributo fuese público, cualquier cambio en su representación interna rompería a los clientes, haciendo la clase mucho menos flexible.

### La convención más habitual en Java es declarar todos los atributos como privados y exponer únicamente los métodos necesarios para interactuar con ellos. Esto sigue el principio de encapsulación, que recomienda ocultar los detalles internos y ofrecer una interfaz clara y estable. Los getters y setters son la vía estándar para proporcionar acceso controlado, aunque en diseño orientado a objetos más riguroso se recomienda evitar setters cuando sea posible para preservar mejor la integridad del objeto.

### Esto se relaciona directamente con las invariantes de clase, que son condiciones que deben cumplirse siempre para que un objeto sea válido. Si los atributos fueran públicos, cualquier código externo podría modificar su estado de forma arbitraria, potencialmente violando dichas invariantes. Al mantenerlos privados y controlar toda modificación a través de métodos, la clase puede asegurarse de que su estado interno nunca quede en una situación inconsistente.


## 17. ¿Qué significa que una clase sea **inmutable**? ¿qué es un método modificador? ¿Un método modificador es siempre un "setter"? ¿Tiene ventajas que una clase sea inmutable?

### Una clase se considera inmutable cuando, una vez creado un objeto, su estado interno no puede cambiarse bajo ninguna circunstancia. Esto implica que todos sus atributos deben ser privados y no modificables tras la construcción, ya sea porque son final o porque no se exponen métodos que alteren su contenido. Una clase inmutable proporciona objetos cuyo comportamiento es predecible y que no cambian inesperadamente, lo cual facilita el razonamiento y evita muchos errores derivados de modificaciones no controladas.

### Un método modificador es cualquier método que cambia el estado interno del objeto, ya sea alterando un atributo directamente o a través de una operación que modifique su valor. Aunque los setters (setX, setY, etc.) son ejemplos típicos de métodos modificadores, no son los únicos: métodos como trasladar(dx, dy) o incrementar() también lo son porque transforman el estado del objeto sin ser setters formales. En una clase inmutable, este tipo de métodos no existen; en su lugar, si se necesita una modificación, se devuelve un nuevo objeto con el estado actualizado.

### La inmutabilidad aporta diversas ventajas. Por un lado, asegura que las invariantes de clase se mantengan siempre, ya que el estado no puede corromperse tras la creación del objeto. Por otro, resulta especialmente útil en programación concurrente, porque los objetos inmutables pueden compartirse entre hilos sin necesidad de sincronización adicional. Finalmente, simplifica el diseño y mejora la legibilidad, porque el comportamiento del objeto es estable y no admite cambios inesperados durante su ciclo de vida.


## 18. ¿Es recomendable incluir métodos "setter" siempre y como convención?

### No, no es recomendable incluir métodos setter siempre ni como una convención automática. Aunque en las primeras aproximaciones a la orientación a objetos pueda parecer razonable exponer setters para todos los atributos, hacerlo reduce significativamente la encapsulación. Al permitir que cualquier parte del código modifique los campos libremente, la clase pierde control sobre su propio estado y se dificulta garantizar que las invariantes internas se cumplan de forma consistente.

### La práctica recomendada es declarar los atributos como privados y exponer únicamente los setters que realmente sean necesarios para el comportamiento de la clase. Si un atributo debe permanecer estable una vez construido el objeto (por ejemplo, un identificador o una fecha de creación), no debe existir un setter que permita cambiarlo. Además, limitar los setters evita estados intermedios inválidos y facilita que los objetos sean más simples de razonar y de mantener correctos a largo plazo.

### Por otro lado, eliminar setters cuando no son necesarios acerca el diseño a la inmutabilidad, lo cual ofrece ventajas importantes como mayor seguridad, menor probabilidad de errores y mejor comportamiento en entornos concurrentes. Incluso en clases mutables, restringir los setters fuerza a que las modificaciones pasen por métodos bien definidos que pueden validar, transformar o proteger el estado, reforzando las invariantes de clase y mejorando la robustez del código.


## 19. ¿La clase `String` en Java es mutable o inmutable? ¿Qué ocurre al concatenar dos cadenas? ¿Qué debemos hacer si vamos a hacer una operación que implique concatenar muchas veces para construir paso a paso una cadena muy larga?

### La clase String en Java es inmutable, lo que significa que, una vez creada una cadena, su contenido no puede modificarse. Cada operación que aparentemente cambia una cadena —como concatenar, reemplazar caracteres o convertir mayúsculas/minúsculas— en realidad produce un nuevo objeto String. Esta inmutabilidad aporta seguridad y consistencia, ya que evita que distintas partes del programa alteren accidentalmente el mismo contenido compartido.

### Al concatenar dos cadenas con el operador +, internamente se crea un nuevo objeto que contiene el resultado de la concatenación. Si esta operación se repite muchas veces dentro de un bucle, se producen numerosos objetos temporales que son descartados, lo que tiene un coste significativo en tiempo y memoria debido a la creación y recolección de objetos. Por ello, concatenar repetidamente cadenas con + en un proceso incremental se considera una práctica ineficiente.

### Cuando se necesita construir una cadena paso a paso mediante múltiples operaciones, lo adecuado es emplear StringBuilder, que es mutable y permite añadir contenido sin crear objetos intermedios. Esta clase dispone de métodos como append() que modifican el contenido interno de forma eficiente, y solo al final, cuando se obtiene el resultado definitivo, se convierte a String mediante toString(). Esto mejora notablemente el rendimiento en escenarios donde la concatenación repetida resulta inevitable.


## 20. En POO ¿Cómo se comparan objetos de una misma clase? ¿Por su contenido o por su identidad? ¿Qué es el método equals en Java? ¿Qué hace por defecto? ¿Cómo se deben comparar dos cadenas en Java? 

### En POO, la comparación de objetos puede hacerse por identidad (si son exactamente el mismo objeto en memoria) o por contenido (si representan la misma información aunque sean instancias distintas). En Java, la comparación por identidad se realiza con el operador ==, que solo devuelve true si ambas referencias apuntan al mismo objeto. Para comparar por contenido, cada clase debe definir qué significa que dos objetos sean equivalentes y proporcionar un mecanismo adecuado para evaluarlo sin depender de la identidad de referencia.

### El método encargado de esta comparación lógica en Java es equals(), heredado de la clase Object. Por defecto, equals() se comporta igual que ==; es decir, compara la identidad de las referencias y no el contenido. Si una clase necesita comparación por contenido —como ocurre en String, Integer, o clases definidas por el usuario— debe sobrescribir equals() para especificar qué atributos determinan la igualdad. A menudo, esta redefinición se acompaña de una redefinición de hashCode() para mantener la coherencia en estructuras como HashSet o HashMap.

### En el caso concreto de las cadenas, Java ya sobrescribe equals() para comparar el contenido carácter por carácter, por lo que las cadenas deben compararse siempre con equals() y no con ==. Por ejemplo, "hola".equals("hola") devuelve true, mientras que "hola" == new String("hola") devolvería false porque se trata de objetos distintos. Esta distinción es fundamental para evitar errores habituales al trabajar con texto en Java.


## 21. ¿Qué son las clases "wrapper" en un lenguaje de programación orientado a objetos? ¿Cómo se hace? ¿Es un proceso automático? ¿Qué ventajas tienen? ¿Todos los lenguajes orientados a objetos tienen tipos primitivos y necesitan wrappers? 

### Las clases wrapper son clases que envuelven o representan un tipo primitivo mediante un objeto. En Java, cada tipo primitivo (int, double, char, etc.) tiene su correspondiente clase wrapper (Integer, Double, Character, etc.). Estas clases permiten tratar los valores primitivos como objetos, lo cual es necesario en contextos donde solo se aceptan referencias, como colecciones (ArrayList, HashMap) o ciertos mecanismos genéricos. La creación de un wrapper puede hacerse explícitamente, por ejemplo con new Integer(5) o Integer.valueOf(5), aunque esta última forma es preferida por eficiencia.

### Java incorpora además un mecanismo llamado autoboxing y unboxing, que convierte automáticamente entre tipos primitivos y sus wrappers. Por ejemplo, al asignar Integer n = 5, el compilador transforma ese 5 en un objeto Integer. Del mismo modo, al usar un Integer en un cálculo aritmético, se extrae automáticamente el valor primitivo. Esto simplifica el código y reduce la necesidad de conversiones manuales, pero implica que, aunque sea cómodo, sigue existiendo una creación y destrucción de objetos que puede tener un pequeño coste de rendimiento.

### No todos los lenguajes orientados a objetos tienen tipos primitivos ni necesitan wrappers. Algunos, como Python o Ruby, tratan absolutamente todo como objetos, incluidos los números. En cambio, lenguajes como Java o C# incluyen tipos primitivos para optimizar la eficiencia y, por ello, introducen wrappers para integrarlos en el modelo de objetos cuando es necesario. Las clases wrapper aportan así flexibilidad, facilitan el uso de estructuras genéricas y permiten métodos utilitarios asociados directamente al tipo, manteniendo al mismo tiempo el rendimiento que ofrecen los tipos primitivos.


## 22. ¿En POO qué es un **tipo de dato enumerado**? ¿En Java, un tipo de dato enumerado es una clase? ¿Qué ventajas tienen en términos de encapsulación los enumerados en Java?

### En POO, un tipo de dato enumerado representa un conjunto finito y cerrado de valores posibles. Sirve para modelar conceptos donde solo son válidas unas pocas opciones predefinidas, como los días de la semana, los estados de una máquina o los colores de un semáforo. Su propósito es aportar claridad y seguridad, evitando el uso de constantes numéricas o cadenas que pueden inducir errores difíciles de detectar. En lugar de permitir cualquier valor arbitrario, un enumerado restringe explícitamente cuáles son las alternativas válidas dentro de un dominio concreto.

### En Java, un tipo enumerado (enum) es realmente una clase especial, más cercana a una clase final con instancias predefinidas y únicas. Cada valor del enumerado es un objeto creado internamente, y la propia sintaxis del lenguaje permite añadir atributos, métodos e incluso constructores privados. Esto hace que los enumerados en Java sean más potentes que los enum tradicionales de C/C++, ya que no se limitan a constantes simbólicas, sino que pueden comportarse como objetos completos y versátiles dentro del sistema.

### Los enumerados en Java proporcionan ventajas claras en términos de encapsulación, ya que ocultan la representación interna de los valores y garantizan que ningún código externo pueda crear nuevos estados no permitidos. Además, permiten agrupar comportamiento relacionado directamente con los valores enumerados, concentrando lógica dentro del propio enum en lugar de dispersarla en otras partes del programa. Esto refuerza la coherencia y facilita que las invariantes del dominio se mantengan automáticamente, ya que solo existen los valores válidos definidos por el propio tipo enumerado.


## 23. Crea un tipo enumerado en Java que se llame `Mes`, con doce posibles instancias y que además proporcione métodos para obtener cuántos días tiene ese mes, el ordinal de ese mes en el año (1-12), empleando atributos privados y constructores del tipo enumerado.


public enum Mes {
    ENERO     (31, 1),
    FEBRERO   (28, 2),  
    MARZO     (31, 3),
    ABRIL     (30, 4),
    MAYO      (31, 5),
    JUNIO     (30, 6),
    JULIO     (31, 7),
    AGOSTO    (31, 8),
    SEPTIEMBRE(30, 9),
    OCTUBRE   (31,10),
    NOVIEMBRE (30,11),
    DICIEMBRE (31,12);
    
    private final int diasBase;   
    private final int ordinal;    

    private Mes(int diasBase, int ordinal) {
        this.diasBase = diasBase;
        this.ordinal = ordinal;
    }

    public int getOrdinal() {
        return ordinal;
    }

    public int getDias(boolean esBisiesto) {
        if (this == FEBRERO && esBisiesto) {
            return 29;
        }
        return diasBase;
    }

    public int getDias(int anho) {
        return getDias(esBisiesto(anho));
    }

    public static boolean esBisiesto(int anho) {
        return (anho % 4 == 0 && anho % 100 != 0) || (anho % 400 == 0);
    }
}



## 24. Añade a la clase `Mes` del ejercicio anterior cuatro métodos para devolver si ese mes tiene algunos días de invierno, primavera, verano u otoño, indicando con un booleano el hemisferio (norte o sur, parámetro `enHemisferioNorte`). Es decir: `esDePrimavera(boolean esHemisferioNorte)`, `esDeVerano(boolean esHemisferioNorte)`, `esDeOtoño(boolean esHemisferioNorte)`, `esDeInvierno(boolean esHemisferioNorte)`


    public boolean esDePrimavera(boolean esHemisferioNorte) {
        if (esHemisferioNorte) {
            return this == MARZO || this == ABRIL || this == MAYO;
        } else {
            return this == SEPTIEMBRE || this == OCTUBRE || this == NOVIEMBRE;
        }
    }

    public boolean esDeVerano(boolean esHemisferioNorte) {
        if (esHemisferioNorte) {
            return this == JUNIO || this == JULIO || this == AGOSTO;
        } else {
            return this == DICIEMBRE || this == ENERO || this == FEBRERO;
        }
    }

    public boolean esDeOtoño(boolean esHemisferioNorte) {
        if (esHemisferioNorte) {
            return this == SEPTIEMBRE || this == OCTUBRE || this == NOVIEMBRE;
        } else {
            return this == MARZO || this == ABRIL || this == MAYO;
        }
    }

    public boolean esDeInvierno(boolean esHemisferioNorte) {
        if (esHemisferioNorte) {
            return this == DICIEMBRE || this == ENERO || this == FEBRERO;
        } else {
            return this == JUNIO || this == JULIO || this == AGOSTO;
        }
    }



