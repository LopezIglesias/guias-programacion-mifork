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

### Respuesta


## 8. Ejemplo mínimo de clase en Java, que se llame Punto, con dos atributos, x e y, con un método que se llame `calculaDistanciaAOrigen`, que calcule la distancia a la posición 0,0. Por sencillez, los atributos deben tener visibilidad por defecto. Crea además un ejemplo de uso con una instancia y uso del método

### Respuesta


## 9. ¿Cuál es el punto de entrada en un programa en Java? ¿Qué es `static` y para qué vale? ¿Sólo se emplea para ese método `main`? ¿Para qué se combina con `final`?

### Respuesta

## 10. Intenta ejecutar un poco de Java de forma básica, con los comandos `javac` y `java`. ¿Cómo podemos compilar el programa y ejecutarlo desde linea de comandos? ¿Java es compilado? ¿Qué es la **máquina virtual**? ¿Qué es el *byte-code* y los ficheros `.class`?

### Respuesta


## 11. En el código anterior de la clase `Punto` ¿Qué es `new`? ¿Qué es un **constructor**? Pon un ejemplo de constructor en una clase `Empleado` que tenga DNI, nombre y apellidos

### Respuesta


## 12. ¿Qué es la referencia `this`? ¿Se llama igual en todos los lenguajes? Pon un ejemplo del uso de `this` en la clase `Punto`

### Respuesta


## 13. Añade ahora otro nuevo método que se llame `distanciaA`, que reciba un `Punto` como parámetro y calcule la distancia entre `this` y el punto proporcionado

### Respuesta


## 14. El paso del `Punto` como parámetro a un método, es **por copia** o **por referencia**, es decir, si se cambia el valor de algún atributo del punto pasado como parámetro, dichos cambios afectan al objeto fuera del método? ¿Qué ocurre si en vez de un `Punto`, se recibiese un entero (`int`) y dicho entero se modificase dentro de la función? 

### Respuesta


## 15. ¿Qué es el método `toString()` en Java? ¿Existe en otros lenguajes? Pon un ejemplo de `toString()` en la clase `Punto` en Java

### Respuesta


## 16. Reflexiona: ¿una clase es como un `struct` en C? ¿Qué le falta al `struct` para ser como una clase y las variables de ese tipo ser instancias?


### Respuesta


## 17. Quitemos un poco de magia a todo esto: ¿Como se podría “emular”, con `struct` en C, la clase `Punto`, con su función para calcular la distancia al origen? ¿Qué ha pasado con `this`?

### Respuesta
