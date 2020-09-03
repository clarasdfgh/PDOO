# PDOO: RELACIÓN DE PROBLEMAS 1

### Conceptos de OO

##### 1. Plantéate la siguientes cuestiones: ¿Qué es un paradigma? 

Teoría o conjunto de teorías cuyos principios base se aceptan sin cuestionar. Son base y modelo para la resolución de problemas

##### ¿Qué es un paradigma de programación? 

Conjunto de teorías y reglas para el desarrollo de software

##### ¿Qué paradigmas de programación existen? Haz una lista con los distintos paradigmas de programación que encuentres, describiendo con tus propias palabras sus características principales. 

- **Imperativo**. Los programas se componen de un conjunto de  sentencias que cambian su estado. 
- **Declarativo**. Opuesto al imperativo. Los programas describen  los resultados esperados sin listar explícitamente los pasos a llevar a  cabo para alcanzarlos.
- **Lógico**. El problema se modela con enunciados de lógica de primer orden (como la vista en LMD)
- **Funcional**. Los programas se componen de funciones, es decir, implementaciones de comportamiento que reciben un conjunto de datos de  entrada y devuelven un valor de salida.
- **Orientado a objetos.** El comportamiento del programa es llevado a cabo por objetos, entidades que representan elementos del problema a resolver y tienen atributos y  comportamiento.

##### ¿Qué paradigma de programación has usado normalmente cuando has programado?

Hasta ahora principalmente aplicábamos el imperativo o el funcional, en esta asignatura seguiremos el orientado a objetos



##### 2. Responde a las siguientes cuestiones, no te conformes con lo expuesto en los primeros temas e investiga usando otras fuentes bibliográficas. 

##### a) En POO se suele decir: Todo es un objeto o un mensaje a un objeto, ¿se cumple esto en todos los lenguajes de programación? En caso negativo, cita al menos uno y explica por qué no lo cumple. 

Falso, esto es sólo cierto en lenguajes de POO. Por ejemplo, Prolog está basado en el paradigma lógico y no cumple esta afirmación.

##### b) Teniendo en cuenta los conocimientos que has adquirido previamente en otras asignaturas de programación, ¿cómo relacionarías los siguientes conceptos? clase, objeto, estado, método y envío de mensaje 

Una clase es un TDA que definimos, con métodos y atributos.

Un objeto es una instancia de la clase, o sea, una variable (o constante) del TDA que definimos con la clase.

El estado es el conjunto de atributos del objeto.

Un método es una función definida dentro de la clase que le aporta funcionalidad.

##### c) ¿Qué diferencia hay entre un tipo de dato y un tipo abstracto de dato (TAD)? y ¿entre un TAD y una clase? ¿Qué conceptos son específicos de la POO (no están presentes en el TAD)? 

Un tipo de dato es cualquier tipo de dato: desde datos predefinidos (p.ej. int), datos definidos por el usuario (struct) y datos creados por el usuario (clases). Los TDA/TAD son estos últimos.

No existe diferencia entre una clase y un TDA.

##### d) Pon un ejemplo que muestre el concepto de herencia de forma parecida a como se ha hecho en las diapositivas de los primeros temas. Usa ese mismo ejemplo para explicar el concepto de polimorfismo. 

El polimorfismo es como un mismo método puede realizar distintas acciones dependiendo del número de parámetros u otras condiciones (ej. métodos sobrecargados, varios constructores).

La herencia es utilizar de base una clase o método para otros similares (ej. heredar la clase Persona para crear la clase PersonaAlta).

##### e) ¿Qué entiendes por tiempo de ligadura? Si los tipos de ligadura que existen según el tiempo en el que se llevan a cabo son estática y dinámica ¿cuál crees que has usado cuando has programado? ¿con qué lenguaje? 

Es el momento en el que se relaciona la llamada a un método con el cuerpo de éste.

Hasta ahora hemos usado estática (c++). En POO se utiliza ligadura dinámica (java).

##### f) ¿Qué problemas puede presentar un sistema software con bajo ocultamiento de la información? 

Por motivos maliciosos o por error, la no ocultación de la información puede llevar a cambiar el estado del objeto de forma imprevista, produciendo errores.

##### g) ¿Qué ventajas crees que aporta la OO en el diseño de software?

- Estructura modular que da gran libertad a la hora de definir TDA con ocultación de información
- Los objetos se pueden reutilizar (herencia y polimorfismo)
- Más fácil de mantener: los cambios se localizan al módulo al que afectan

### Lenguajes y técnicas de OO

##### 1. Compara las características de Java y de Ruby con los lenguajes con los que hayas trabajo anteriormente (al menos con C++).

|                    | C++  | JAVA | RUBY |
| ------------------ | :--: | :--: | :--: |
| Compilación?       |  ✓   |  ✓   |  ✘   |
| Garbage collector? |  ✘   |  ✓   |  ✓   |
| Punteros?          |  ✓   |  ✘   |  ✓   |
| Corchetes?         |  ✓   |  ✓   |  ✘   |

##### 2. Realiza un estudio del uso y popularidad de los lenguajes de programación en los últimos años, para ello puedes visitar webs como el índice TIOBE, PYPL, el ranking RedMonk, el Programming Language Popularity Chart, o el Top Ten Programming Languages de IEEE. Añade algún otro ranking interesante a esta lista e intenta explicar a qué se deben las diferencias en la posición que ocupan los lenguajes en diferentes rankings.

| PYPL        | RedMonk    | TIOBE       |
| ----------- | ---------- | ----------- |
| Phyton      | JavaScript | Java        |
| Java        | Java       | C           |
| Javascript  | Phyton     | Phyton      |
| C#          | PHP        | C++         |
| PHP         | C++        | C#          |
| C/C++       | C#         | VisualBasic |
| R           | CSS        | Javascript  |
| Objective-C | Ruby       | PHP         |
| Swift       | C          | Swift       |
| Matlab      | TypeScript | SQL         |

Las posiciones dependen del sistema que siga el ranking:

- TIOBE monitoriza la popularidad con varios motores de búsqueda y el número de lineas de código que encuentra
- PYPL monitoriza la popularidad, en este caso utilizando solamente Google Trends
- RedMonk emplea el número de repositorios de Github y StackOverflow

##### 3. Investiga sobre la historia y características de UML y explica para qué sirven y cómo aparecieron los distintos tipos de diagramas, cuál es su uso en la actualidad, las ventajas e inconvenientes de su uso

El UML surge de unificar el método Booch y el OMT (Object Modelling Tool).

Tipos de diagramas:

- de Clases
- de Objetos
- de Casos de Uso
- de Estado
- de Secuencias
- de Actividades
- de Colaboraciones
- de Componentes
- de Distribución

Ventajas:

- Sirve para múltiples tipos de sistemas y lenguajes
- Consolida las notaciones de conceptos de POO
- Es fácilmente entendible

Inconvenientes:

- No es un método de desarrollo
- No es muy aplicable a sistemas distribuídos

##### 4. ¿Existen detractores de la UML?¿Cuál es su opinión?

Sí, algunas de las críticas a UML son:

- Realmente no es necesario: puedes transmitir la misma información sin reglas formales. Ya utilizamos un lenguaje formal de programación, usar UML es añadir otra capa de complicación a lo que se supone que es una representación esquemática.
- Hay demasiados tipos de diagramas, lo cual lo hace parecer inaccesible a gente que no lo conoce
- Ambos puntos confluyen en que, aunque UML es útil para hacer diagramas y transmitir la información bajo un marco común, debería haberse quedado ahí, en vez de convertirse en un lenguaje gráfico con cada vez más formalismos

