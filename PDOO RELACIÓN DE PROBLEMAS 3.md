# PDOO: RELACIÓN DE PROBLEMAS 3

##### Ejercicio 1. UML es un lenguaje “universal”. Escribe el código Java y Ruby correspondiente a la declaración de la siguiente clase en danés (incluyendo la declaración de atributos y la cabecera de los métodos). 

![image-20200203184729957](/home/clara/.config/Typora/typora-user-images/image-20200203184729957.png)

```
public class Kursus{
	private int antalStuderende;
	private String navn;
	
	public int getAntalStuderende(){(...)}
	public void setAntalStuderende(int antalStuderende);
	public String getNavn(){(...)}
	public void setNavn(String navn){(...)};
}
```

```
class Kursus
	@antalStuderende
	@navn
	
	attr_accesor :antalStuderende
	attr_accesor :navn
end
```



##### Ejercicio 2. A partir del siguiente diagrama de clases, obtén un esquema en el que se muestren los objetos y sus enlaces (relaciones) para el siguiente caso: 2 objetos PlanEstudios, 6 objetos Asignatura, 5 objetos Estudiante. Haz las suposiciones que consideres oportunas.

![image-20200203184745912](/home/clara/.config/Typora/typora-user-images/image-20200203184745912.png)

//TODO

##### Ejercicio 3. El siguiente diagrama de clases representa hoteles con sus habitaciones y las reservas hechas por sus clientes: 

![image-20200203201954833](/home/clara/.config/Typora/typora-user-images/image-20200203201954833.png)

- Complétalo con los atributos de las clases y el nombre, roles, multiplicidad y navegabilidad de las asociaciones, haciendo las suposiciones que consideres oportunas. 

  - Hotel:
    - Ciudad (1) ciudad
    - Habitacion (1..*) habitaciones
    - String nombre
  - Ciudad
    - String nombre
    - String calle
    - int numero
  - Habitacion
    - int camas (0..4)
    - Reserva reserva (1..*)
  - Cliente
    - String nombre
    - String dni
    - Reserva reserva (1..*)

- Implementa en Java el resultado obtenido. 

  ```
  public class Ciudad{
  	private String nombre;
  	private String calle;
  	private String numero;
  }
  
  public class Hotel{
  	private String nombre;
  	private Ciudad ciudad;
  	private ArrayList<Habitacion> habitaciones = new ArrayList<Habitacion>();
  }
  
  public class Reserva{
  	private Cliente cliente;
  	private Habitacion habitacion;
  	private Date fecha;
  }
  
  public class Habitacion{
  	private static final int max_camas = 4;
  	private int camas;
  	private ArrayList<reserva> reservas;
  	
  }
  
  public class Cliente{
  	private String nombre;
  	private String dni;
  	private ArrayList<reserva> reservas;
  
  }
  ```

- Implementa en Ruby el resultado obtenido. 

  ```
  class Ciudad
  		@nombre
  		@calle
  		@numero
  end
  class Hotel
  	@nombre
  	@ciudad
  	@habitaciones = []
  end
  class Reserva
  	@habitacion
  	@cliente
  	@fecha
  end
  class Habitacion
  	@@max_camas = 4
  	@camas
  	@reservas = []
  end
  class Cliente
  	@nombre
  	@dni
  	@reservas = []
  end
  ```

##### Ejercicio 4. A partir del siguiente diagrama de clases.

![image-20200203202037836](/home/clara/.config/Typora/typora-user-images/image-20200203202037836.png)

- Indica el nombre o roles de las asociaciones. 

  - Sistema Reservas: 

    ```
    ArrayList<Evento> eventos;
    ```

  - Reserva:

    ```
    ArrayList<Sala> salas;
    ArrayList<Reserva> reservas;
    ```

  - Sala:

    ```
    ArrayList<Butaca> butacas;
    ```

- ¿La asociación que existe entre Sala y Butaca podría ser una agregación?¿Y una composición? 

  - No, porque no puede existir una butaca sin sala. Sí puede ser una composición y que no existan salas sin butacas. Además una misma butaca no puede pertenecer a dos salas distintas

- Partiendo de una sala, ¿podría saberse para qué eventos está siendo usada?

  - No: Evento contiene a Sala y es una relación unidireccional.

- Escribe el código Java correspondiente.  

  ```
  //TODO
  ```

- Escribe el código Ruby correspondiente. 

  ```
  //TODO
  ```

##### Ejercicio 5. Teniendo en cuenta el siguiente diagrama de clases:

![image-20200203202052163](/home/clara/.config/Typora/typora-user-images/image-20200203202052163.png)

- Escribe el código Java correspondiente, sin olvidar las asociaciones y su navegabilidad y haciendo uso del nombre de los roles que figuran en el diagrama. 
- Impleméntalo en Ruby. 
- Si modificamos la navegabilidad en el siguiente sentido: Customer ----> LoyaltyProgram ---> ServiceLevel ---> Membership ¿Qué habría que modificar en el código desarrollado anteriormente? 
- ¿Qué implicación tendrá la restricción {ordered}? ¿qué habría que hacer en el código para asegurar que se cumple?

##### Ejercicio 6. Dado el siguiente diagrama de paquetes:

![image-20200203202107381](/home/clara/.config/Typora/typora-user-images/image-20200203202107381.png)

- Indica cómo implementarías esta estructura en Java y en Ruby 

  ```
  package paqueteA
  	(...)
  	
  package paqueteA.paqueteB
  	(...)
  	
  package paqueteA.paqueteC
  	import paqueteD
  	public class X
  	(...)
  	
  package paqueteD
  	(...)
  ```

  ```
  module paqueteA
  	module paqueteB
  		(...)
  	end
  	module paqueteC
  	require_relative paqueteD
  		class X
  			(...)
  		end
  		end
  		(...)
  	end
  	(...)
  end
  
  (...)
  
  module paqueteD
  	(...)
  end
  ```

- Justifica si sería accesible en Java un atributo de la clase X declarado con visibilidad de paquete desde: 

  - Una clase de paqueteB
    - No: aunque paqueteA contenga a PaqueteB siguen siendo dos paquetes distintos
  - Una clase de paqueteA que no esté en paqueteB ni en paqueteC  
    - De nuevo, no porque no está en paqueteB
  - Una clase de paqueteD 
    - Sí, la clase X contiene al paqueteD

- Responde a los mismos casos anteriores pero considerando visibilidad pública.

  - Una clase de paqueteB
    - Sí
  - Una clase de paqueteA que no esté en paqueteB ni en paqueteC  
    - Sí
  - Una clase de paqueteD 
    - Sí

##### Ejercicio 7. Dado el siguiente diagrama de paquetes:

![image-20200204011850672](/home/clara/.config/Typora/typora-user-images/image-20200204011850672.png)

- Indica cómo implementarías esta estructura en Java y en Ruby 

  ```
  package X
  import X.Y
  import X.Z.V
  	(...)
  public class E
  	(...)
  package X.Y
  	(...)
  	package X.Y.C
  		(...)
  	package X.Y.U
  	import X.Z.V.B
  		(...)
  		public class A
  			(...)
  package X.Z
  	(...)
  	public class D
  		(...)
  	package X.Z.V
  			(...)
  		public class B
  			(...)
  		private class F
  ```

  ```
  module X
  require_relative Y
  require_relative V
  	(...)
  	class E
  		(...)
  	end
  	module Y
  		module C
  			(...)
  		end
  		module U
  		require_relative B
  			class A
  				(...)
  			end
  			(...)
  		end
  		(...)
  	end
  	module Z
  		module D
  			(...)
  		end
  		module V
  			class B
  				(...)
  			end
  			private class F
  				(...)
  			end
  			(...)
  		end
  		(...)
  	end
  end
  ```

  

- Justifica si sería accesible en Java un atributo de la clase B declarado con visibilidad de paquete desde: 

  - Desde la clase F 
    - Sí, pertenecen al mismo paquete
  - Desde la clase D 
    - No: no pertenecen al mismo paquete aunque estén anidados
  - Desde la clase A 
    - Sí porque importamos la clase B al paquete U

- Si en Ruby implementamos los paquetes como módulos y cada clase está implementada en un fichero llamado <nombre_clase>.rb su módulo correspondiente: ¿Qué tendríamos que escribir en el fichero de la clase C, para poder usar un método definido como público en la clase D desde la clase C?

  - //TODO

##### Ejercicio 8. A partir del siguiente diagrama de clases, responde a las cuestiones planteadas:

![image-20200204012252163](/home/clara/.config/Typora/typora-user-images/image-20200204012252163.png)

- A) La asociación que hay entre Empresa y Departamento, ¿es de tipo agregación o composición? ¿podría ser del otro tipo? Razona por qué. 
  - Agregación.
- B) ¿Cuál es la multiplicidad de dicha asociación en el lado de Empresa? ¿podría ser distinta? Razona por qué. 
  - Una empresa contiene varios departamentos. 
- C) La asociación que hay entre Departamentos, ¿es de tipo agregación o composición? ¿podría ser del otro tipo? Razona por qué 
  - Agregación.
- D) ¿Qué son GUIEmpresa y modeloEmpresa? 
  - Paquetes
- E) La relación que hay entre GUIEmpresa y Empresa ¿de qué tipo es?, es decir ¿qué significa \<\<import>> sobre ella? 
  - Dependencia. Significa que GUIempresa requiere de Empresa para funcionar, y puede utilizar las clases contenidas en su paquete
- F) ¿Cuál es la navegabilidad de la asociación adscrito entre Empleado y Departamento? ¿y de la asociación desarrolla entre Empresa y Proyectos?
  - //TODO 
- G) ¿Qué representa la línea discontinua entre las asociaciones adscrito y participa y cuál es su significado en este diagrama?
  - //TODO
- H) Hay dos asociaciones entre Proyectos y Empleado, ¿qué representan? 
  - Que dentro de Proyectos existen dos atributos Empleado y viceversa
- I) ¿Por qué hay 0..* y no 1..* en la multiplicidad de la asociación entre Empleado y Proyectos?
  - Porque un empleado puede no tener proyectos, sobre todo si ya cumple uno de sus atributos (p.ej. participa en 0 pero es responsable de 1)

##### Ejercicio 9. Partiendo del siguiente diagrama de clases de UML, resolver las cuestiones planteadas a continuación.

![image-20200204012958822](/home/clara/.config/Typora/typora-user-images/image-20200204012958822.png)

- A) ¿Qué cambio habría que hacer en el diagrama de clases para modelar que un barrio puede tener varias asociaciones de vecinos? 
  
  - Junto a Asociacion_Vecinos añadir 1..* 
  
- B) ¿Desde un objeto de la clase Ciudadano puede saberse si es presidente de la asociación de vecinos de su barrio?¿Por qué? 
  
  - No, desde Ciudadano la relación con Asociacion_Vecinos es unidireccional
  
- C) ¿De qué tipo es la relación entre Ciudad y Barrio? ¿qué significa? 
  
  - Composición. Una ciudad se compone de barrios, y un barrio no puede existir sin ciudad
  
- D) ¿De qué tipo es la relación entre Barrio y Ciudadano? ¿qué significa? ¿podría ser de otro tipo? 
  
  - Agregación. Un barrio tiene Ciudadanos que son vecinos, pero puede haber ciudadanos sin ser vecinos ni del barrio
  
- E) ¿Qué significa la línea discontinua con la indicación “{subconjunto}” entre la asociaciones de Barrio---Ciudadano y Asociacion_Vecinos---Ciudadano? 
  
  - //TODO
  
- F) Si la junta directiva de una asociación de vecinos está formada por exactamente 6 ciudadanos, ¿cómo lo indicarías en el diagrama de clases? 
  
  - Sustituir el 1..* al lado de juntaDirectiva por un 6
  
- G) ¿Qué significa que la clase Cargo esté ligada a la asociación entre Asociacion_Vecinos y Ciudadano? 
  
  - 
  
- H) Implementa en Ruby los consultores/modificadores básicos de la clase Asociación_Vecinos. 
  
  - ```
    attr_accesor :nombre
    attr_accesor :cif
    ```
  
- I) ¿Cómo debería ser el constructor de Ciudadano para que inicialice el estado completo de una instancia? Impleméntalo en Java y Ruby. 

  - ```
    def initialize, cif
    	 @nombre = nom
    	 @cif = cif
    ```

    

- J) Suponiendo que la visibilidad de todas las clases del diagrama es pública y que estamos codificando la clase Voto en Java ¿A qué otras clases puede acceder ésta usando directamente su nombre, sin indicar el nombre del paquete al que pertenecen? 

- K) Define en Java los atributos de referencia de la clase Barrio. 

- L) ¿Desde qué clases es accesible el atributo nombre de la clase Asociacion_Vecinos? 

- M) Implementa en Java y Ruby las clases Asociacion_Vecinos y Mesa_Electoral completas (Ojo: no incluir nada que no esté en el diagrama de clases proporcionado).

##### Ejercicio 10. Partiendo del siguiente diagrama de clases de UML, responde verdadero (V) o falso (F) a las cuestiones:

![image-20200204013133098](/home/clara/.config/Typora/typora-user-images/image-20200204013133098.png)

- Desde la clase AyudaSolicitada se puede acceder a todos los elementos públicos del paquete GestorProgramas. 
- Un voluntario puede participar en cualquier acción de un programa sin ningún tipo de restricción. 
- El estado de un objeto de la clase Auditor viene determinado por el estado de un objeto de la clase ONG. 
- Un voluntario podría participar en acciones de distintos programas. 
- Un voluntario puede pertenecer a varias ONG. 
- Cuando se define un objeto de la clase Acción, éste tiene que asociarse a un determinado objeto de la clase Programa. 
- En una acción puede participar más de un voluntario como especialista. 
- Desde un objeto de la clase ONG se puede llegar a conocer a todos los especialistas de una determinada acción en un programa. 
- El estado de un objeto Voluntario está exclusivamente determinado por su dni, nombre y especialidad. 
- Todos los métodos de la clase Acción pueden ser accedidos desde la clases AyudaConcedida.

##### Ejercicio 11. Partiendo del diagrama de clases del ejercicio 10 responde a las siguientes preguntas: 

- A) Usando la siguiente nomenclatura: AS = Asociación, CO = Composición, AG = Agregación, DE = Dependencia, CA = Clase Asociación y RE = Restricción, etiqueta los elementos correspondientes en el propio diagrama de clases. 

  - 

- B) Implementa en Java y Ruby las clases Accion y AyudaConcedida.

  ```
  
  ```

  ```
  
  ```

##### Ejercicio 12. Partiendo del diagrama de clases del ejercicio 10, implementa en Java y en Ruby los atributos de referencia de todas las clases.

##### Ejercicio 13. Cuando se implemente en Java el siguiente diagrama de clases, responde si las afirmaciones son verdaderas (V) o falsas (F)

![image-20200204013617218](/home/clara/.config/Typora/typora-user-images/image-20200204013617218.png)

- Hotel tendrá dos atributos de referencia, uno relativo a las reservas y otro relativo a los clientes 

  - 

- Reserva tendrá los atributos de referencia: 

  ```
  private Hotel hotel; 
  private Cliente cliente;
  ```

  - 

##### Ejercicio 14. A partir del siguiente diagrama de clases, Responde verdadero (V) o falso (F) a las siguientes cuestiones:

![image-20200204013914496](/home/clara/.config/Typora/typora-user-images/image-20200204013914496.png)

- La asociación Piso-Habitación es de agregación 
  - 
- {propietario<>inquilino} es una restricción 
  - 
- Una persona puede saber de qué pisos es propietaria 
  - 
- Alquiler es una clase asociación
  -  
- vecinos es un rol 
  - 
- Puede haber una habitación sin inquilinos 
  - 
- Piso tiene un atributo de referencia de la clase Persona 
  - 
- El método getDireccion de Piso es método de clase, no de instancia 
  - 
- Desde la clase Piso se puede acceder directamente al atributo dni de un inquilino 
  - 
- Desde la clase Persona se puede acceder directamente al atributo num_padron de un objeto de la clase Padron 
  - 
- Los siguientes objetos de Piso tienen la misma identidad: 
  - Piso piso1= new Piso(“Calle Alta”, true, 600) 
  - Piso piso2= new Piso(“Calle Alta”, true, 600)
    - 

##### Ejercicio 15. Escribe el código necesario para hacer que piso1 y piso2 sean idénticos. 

##### Ejercicio 16. ¿Desde la clase Padrón se puede acceder al método getCalefacción de Piso? Justifica tu respuesta. 

##### Ejercicio 17. Indica si es correcto implementar en Ruby para la clase Padrón lo siguiente: 

- attr_reader :dirección, :mensualidad 
- attr_accessor :calefaccion 

##### Justifica tu respuesta.

##### Ejercicio 18. Teniendo en cuenta sólo la información presentada en el diagrama de clases del ejercicio 14, implementa en Java y Ruby las clases Persona, Alquiler y Padrón. Añade sus constructores para inicializar los atributos y métodos consultores para todos los atributos. No te olvides de incluir también el código necesario para indicar que cada clase está dentro de un paquete o módulo, y si precisa algo de otro paquete o módulo. Supón que en Ruby cada clase se implementa dentro de un fichero con el mismo nombre que la clase y que están todas en la misma carpeta. Dado que no tenemos información sobre los métodos de Persona, implementa solo sus cabeceras. 



##### Ejercicio 19. A continuación se muestran varios diseños, todos congruentes con la siguiente especificación: 

> “En un restaurante se dispone de un Gestor de Menú encargado de elaborar los menús para cada mes, cada menú está compuesto por tres platos: un primero, un segundo y un postre. A cada plato le corresponde una receta. Los ingredientes de la receta lo componen una lista de productos y las cantidades necesarias de cada producto. Para elaborar un menú para un día concreto hay que proporcionar un primero, un segundo y un postre.”



