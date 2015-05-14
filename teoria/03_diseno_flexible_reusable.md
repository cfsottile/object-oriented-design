## El modelo estático vs el dinámico

El modelo estático es el que se desprende del software "quieto": en tiempo de compilación. Se compone de las clases y las relaciones entre ellas.

El modelo dinámico es el de los objetos en acción: en tiempo de ejecución. Se compone de los objetos y las colaboraciones entre ellos.

## Diseñar para el cambio

Lo primero que se requiere para prepararse para los cambios es, claro, prepararse para los cambios: determinar cuáles son los cambios que puede llegar a sufrir, y diseñar el sistema con esta flexibilidad como base.

Los patrones de diseño son técnicas que añaden el reuso y la flexibilidad buscados. En este aspecto, podríamos pensar en la herencia y el polimorfismo como patrones (yo, de hecho, los considero así).

### Las mejores formas de atarse a la implementación y no "diseñar para el cambio"
* __Crear objetos especificando su clase de forma explícita__.

* __Dependencia de operaciones concretas__: performar las operaciones hardcodeándolas, en lugar de abstraerse mediante métodos intermedios. _Por ej.: se realiza un cálculo complejo en vez de llamar a un método_.

* __Dependencia de plataformas__: implementar la comunicación con el software o hardware subyacente de manera directa, sin aislarse de cuál sea. _Por ej.: llamando a las system calls de windows de una_.

* __Dependencia de las representaciones o implementaciones de objetos__: implementar objetos clientes a partir de la implementación de los objetos que usa, haciéndolos dependientes y poco desacoplados.

* __Dependencias algorítmicas__: no aislar los algoritmos, acoplándolos a los objetos sin tener en cuenta que pueden cambiar.

* __Fuerte acoplamiento entre clases__: gran dependencia entre las clases, evitando que se puedan reutilizar por separado o que puedan ser reemplazadas por otras sin tener que modificar a las demás.

* __Añadir funcionalidad mediante la herencia__: heredar para reusar en situaciones en que la mejor solución sería la composición. Querer añadir funcionalidad heredando en vez de usando.

* __Incapacidad para modificar clases convenientemente__: modificar clases que no resulta conveniente modificar. _Por ej.: modificar una librería externa que va a actualizarse constantemente, por lo que se pisarán nuestros cambios_.

### El diseño para el cambio en los distintos tipos de aplicación

Qué tan útil es el diseño para el cambio en el desarrollo de las aplicaciones?

##### Programas de aplicación

El desacoplamiento (de clases) y la independencia (de plataformas, operaciones, algoritmos e implementación/representación) permiten la reutilización de los objetos en diferentes contextos, una mayor extensibilidad del modelo, portabilidad, y una mejor ledibilidad.

#### Toolkits / librerías

#### Frameworks