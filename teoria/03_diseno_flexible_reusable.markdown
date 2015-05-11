## El modelo estático vs el dinámico
El modelo estático es el que se desprende del software "quieto": en tiempo de compilación. Se compone de las clases y las relaciones entre ellas.
El modelo dinámico es el de los objetos en acción: en tiempo de ejecución. Se compone de los objetos y las colaboraciones entre ellos.

## Diseñar para el cambio
Lo primero que se requiere para prepararse para los cambios es, claro, prepararse para los cambios: determinar cuáles son los cambios que puede llegar a sufrir, y diseñar el sistema con esta flexibilidad como base.
Los patrones de diseño son técnicas que admiten el reuso y la flexibilidad buscados. En este aspecto, podríamos pensar en la herencia y el polimorfismo como patrones (yo, de hecho, los considero así).

### Las mejores formas de atarse a la implementación y no "diseñar para el cambio"
* **Crear objetos especificando su clase de forma explícita**.
* **Dependencia de operaciones concretas**: performar las operaciones hardcodeándolas, en lugar de abstraerse mediante métodos intermedios.
* **Dependencia de plataformas**: implementar la comunicación con el software o hardware subyacente de manera directa, sin aislarse de cuál sea.
* **Dependencia de las representaciones o implementaciones de objetos**: implementar objetos clientes a partir de la implementación de los objetos que usa, haciéndolos dependientes y poco desacoplados.
* **Dependencias algorítmicas**: no aislar los algoritmos, acoplándolos a los objetos sin tener en cuenta que pueden cambiar.
* **Fuerte acoplamiento entre clases**: gran dependencia entre las clases, evitando que se puedan reutilizar por separado o que puedan ser reemplazadas por otras sin tener que modificar a las demás.
* **Añadir funcionalidad mediante la herencia**: heredar para reusar en situaciones en que la mejor solución sería la composición. Querer añadir funcionalidad heredando en vez de usando.
* **Incapacidad para modificar clases convenientemente**: modificar clases que no resulta conveniente modificar. Por ejemplo, cuando se tiene una librería externa que va a actualizarse constantemente.

### El diseño para el cambio y los patrones en los distintos tipos de software
* Programas de aplicación: 
* Toolkits / librerías: 
* Frameworks: 