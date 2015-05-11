# Principios del diseño orientado a objetos

## Programar para interfaces, no para implementaciones
Se desprende de lo ya tratado.
* Programar para implementaciones significa tener en cuenta elementos propios de la implementación, como ser la clase del objeto al que un cliente le pide algo.
* Programar para interfaces significa abstraerse de las cuestiones de implementación, como ser la clase del objeto, teniendo en cuenta sólo lo que es relevante a la situación: en este caso, la interfaz del tipo.
Qué es lo bueno acá? Lo que ya se explicó en el polimorfismo: a mi no me importa qué objeto me pongan adelante (de qué clase es), sólo me importa que sea del tipo que yo espero (cumpla con la interfaz), ya que esto implicará que entenderá lo que voy a decir, y cumplirá con dicha responsabilidad.
`Programar para interfaces, no para implementaciones`

## Reutilización de código
Tenía pinta de ser bastante complejo este apartado, pero al final parece que no lo es tanto. Es simplemente la respuesta a la pregunta "¿Cómo puedo reutilizar el código de un objeto?".

### Herencia
Mediante esta, una subclase hereda todo de su superclase. Hereda atributos y, principalmente, interfaz (para clases abstractas) e implementación (para clases concretas).
La reutilización del código está dada en la herencia de un método implementado. De repente una nueva clase encuentra como parte suya un código que ya había sido escrito, y lo puede usar.

### Composición - Delegación
Dijimos (o quizá no) que los objetos tienen responsabilidades. La interfaz es una lista de las responsabilidades que tienen y que saben solventar.
La composición/delegación es la forma más limpia de reutilización. Hay un objeto que es el responsable de llevar a cabo determinada acción, yo lo conozco, yo necesito que alguien lleve a cabo esa acción, yo delego en el objeto la realización de la acción.
Apartado: capaz en algún momento los desarrolladores se enloquecieron con la herencia y hacían desastres, como para hacer la aclaración tan fuerte.

`Favorecer a la composición vs la herencia`
Esto ha probado ser más flexible y resultar en un diseño menos enquilombado.

### Herencia vs. Composición
El libro hace la distinción entre reutilización de caja blanca y de caja negra. Habla de romper el encapsulamiento al conocer la implementación.
El verdadero trade-off está en heredar todo vs sólo utilizarlo. Opino yo que cada caso debe ser evaluado para definir qué conviene:
* **Heredar** toda la implementación de una clase, añadiendo luego los métodos propios o redefiniendo los existentes.
* **Usar al objeto**, conocerlo, comunicarse con él mediante su interfaz y sin conocer su implementación, y delegar en él.
Un ejemplo bien típico:
La clase Cola no tendría sentido que herede de OrderedCollection, más bien que use un objeto OrderedCollection.
La clase ColaDoble no podría usar un objeto Cola porque debe agregar funcionalidad y la Cola no se lo permite; podría usar un objeto OrderedCollection, o, aún mejor, podría heredar de Cola, reutilizar el código ya escrito y que le sirve, y sólo agregar los métodos que correspondan, en este caso push y pop.
La clase Pila podría usar una ColaDoble y sólo utilizar los métodos que le sirven, reusando código mediante la composición. Heredar de ColaDoble no sería lo mejor ya que debería renunciar a funcionalidad, más allá de que Pila no "es una" ColaDoble. Igual me parece medio chancho que Pila use una ColaDoble, pero bueno no viene al caso.
**Recordar: OrderedCollection, Cola, ColaDoble, Pila.**