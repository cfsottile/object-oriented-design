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