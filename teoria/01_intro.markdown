## Preámbulo

### Objetos: qué son??!!?!?!!?
Son los elementos que componen a los programas orientados a objetos.

### Cómo están formados?
* datos y métodos implementados: ambos privados.
* interfaz pública: los mensajes que se les pueden enviar.

### La interfaz
Los objetos admiten que se le manden a hacer cosas. Lo que se le puede mandar a hacer a un objeto está definido por su interfaz; son todos aquellos mensajes a los que el objeto sabrá responder.
Cuando dos (o más) objetos soportan la misma interfaz, se dice que son del mismo tipo.

### Cómo es eso de los tipos?
En el diseño orientado a objetos, no es lo importante que dos objetos sean del mismo tipo de dato (dado el dominio, sería más adecuado decir clase), sino que respeten la misma interfaz; es decir, que entiendan los mismos mensajes.
Esto provoca que no importe que el cliente no se preocupe por cuál es la clase a la que pertenece un objeto al cual le está por enviar un mensaje: basta con que entienda el mensaje que va a recibir.

### El cliente?
Se dice cliente de un objeto a aquel que le envía un mensaje.

### Interfaz, implementación y encapsulamiento
Siendo yo cliente de un objeto, conozco su interfaz y no conozco su implementación, la cual tampoco me importa. Esto se conoce como encapsulamiento: un objeto tiene una responsabilidad, la forma de delegársela es mediante el envío de un mensaje (interfaz), y su forma de llevarla a cabo (implementación) es privada, no se conoce desde afuera (encapsulamiento); el cliente confía en el objeto, se asume que se va a llevar a cabo de forma correcta.

### Clase
Una clase define todo un objeto en sí. Define cuáles serán los datos que contenga (estructura interna), cuáles serán los mensajes que entienda (interfaz) y cuál será la forma de efectuar las reponsabilidades plasmadas en la interfaz (implementación).

### Herencia de clases e interfaces
Este concepto está muy mezclado en la práctica. Siendo que una subclase hereda todo de una superclase, en dónde está la diferencia entre la herencia de clases y de interfaces?
La herencia de clases implica herencia tanto de interfaz, como de estructura interna, como de implementación. Se usa para reutilizar código y añadir clases con comportamiento similar sin mayor esfuerzo.
La herencia de interfaces sólo implica interfaz, mensajes que podrán entender dos objetos; implica herencia de tipos: dos objetos que heredan la misma interfaz, serán del mismo tipo más allá de que sean de la misma clase o no. Se usa justamente para hacer a dos objetos del mismo tipo: polimórficos.
Vale aclarar que dos objetos pueden ser del mismo tipo siendo o no de la misma clase, y que un mismo objeto puede ser de diferentes tipos, ya que para eso basta con que implemente n interfaces.
`Smalltalk: acá la herencia de clases e interfaces es transparente. Una subclase hereda de una superclase la parte de clase y, en el caso de las clases abstractas, su parte abstracta que en definitiva es sólo interfaz.`

### Polimorfismo
Hablamos de un cliente despreocupado por cuál es el objeto que conoce; sólo le importa que sea del mismo tipo. Esto se llama polimorfismo: un conjunto de objetos que entienden los mismos mensajes y responden a los mismos a su manera, es decir que tienen una implementación diferente (o bueno, quizá no, no lo sabemos porque esta es privada).

## Principios del diseño orientado a objetos

### Programar para interfaces, no para implementaciones
Se desprende de lo ya tratado.
* Programar para implementaciones significa tener en cuenta elementos propios de la implementación, como ser la clase del objeto al que un cliente le pide algo.
* Programar para interfaces significa abstraerse de las cuestiones de implementación, como ser la clase del objeto, teniendo en cuenta sólo lo que es relevante a la situación: en este caso, la interfaz del tipo.
Qué es lo bueno acá? Lo que ya se explicó en el polimorfismo: a mi no me importa qué objeto me pongan adelante (de qué clase es), sólo me importa que sea del tipo que yo espero (cumpla con la interfaz), ya que esto implicará que entenderá lo que voy a decir, y cumplirá con dicha responsabilidad.

## Reutilización de código
Tenía pinta de ser bastante complejo este apartado, pero al final parece que no lo es tanto. Es simplemente la respuesta a la pregunta "¿Cómo puedo reutilizar el código de un objeto?".

### Herencia
Mediante esta, una subclase hereda todo de su superclase. Hereda atributos y, principalmente, interfaz (para clases abstractas) e implementación (para clases concretas).
La reutilización del código está dada en la herencia de un método implementado. De repente una nueva clase encuentra como parte suya un código que ya había sido escrito, y lo puede usar.

### Composición - Delegación
Dijimos (o quizá no) que los objetos tienen responsabilidades. La interfaz es una lista de las responsabilidades que tienen y que saben solventar.
La composición/delegación es la forma más limpia de reutilización. Hay un objeto que es el responsable de llevar a cabo determinada acción, yo lo conozco, yo necesito que alguien lleve a cabo esa acción, yo delego en el objeto la realización de la acción.
Apartado: capaz en algún momento los desarrolladores se enloquecieron con la herencia y hacían desastres, como para hacer la aclaración tan fuerte.

### Herencia vs. Composición
El libro hace la distinción entre reutilización de caja blanca y de caja negra. Habla de romper el encapsulamiento al conocer la implementación.
El verdadero trade-off está en heredar todo vs sólo utilizarlo. Opino yo que cada caso debe ser evaluado para definir qué conviene:
* **Heredar** toda la implementación de una clase, añadiendo luego los métodos propios o redefiniendo los existentes.
* **Usar al objeto**, conocerlo, comunicarse con él mediante su interfaz y sin conocer su implementación, y delegar en él.
Un ejemplo bien típico:
La clase Cola no tendría sentido que herede de OrderedCollection, más bien que use un objeto OrderedCollection.
La clase ColaDoble no podría usar un objeto Cola porque debe agregar funcionalidad y la Cola no se lo permite, podría usar un objeto OrderedCollection, o, aún mejor, podría heredar de Cola y sólo agregar los métodos que correpondan, en este caso push y pop.
La clase Pila podría usar una ColaDoble y sólo utilizar los métodos que le sirve. Heredar de ColaDoble no sería lo mejor ya que debería renunciar a funcionalidad, más allá de que Pila no "es una" ColaDoble. Lo más adecuado sería usar una ColaDoble, ya que estaríamos reutilizando código a pleno.
Recordar: OrderedCollection, Cola, ColaDoble, Pila.