
INTRODUCCION BASE DE DATOS

En algún momento nuestra aplicación va a necesitar algún tipo de persistencia de datos, es decir que lo datos queden guardados en el disco, y no importa si reinicio el servidor, o modifico mi aplicación u otras cosas que puedan ocurrir. 

*Base de datos: Es una colección de datos de un mismo dominio y organizada sistemáticamente para su posterior uso. Esta organización, en general, está construida de tal manera que modele el problema de la mejor forma.
*DBMS (Database Management System): es una aplicación que interactua con el usuario, otras aplicación y la base de datos misma, de tal forma que pueda definir, crear, borrar, modificar, consultar y administrar bases de datos y datos en sí.


Lo que vamos a hacer entonces, es usar un DBMS para que nos ayude a guardar los datos. Como se imaginan hay muchos sabores de BDMS para elegir. Lo primero es elegir si queremos uno que sea relacional (SQL) o uno no relacional (noSQL).

BASE DE DATOS RELACIONALES

Las ventajas de usar una base de datos SQL son:

*Cómo nos obliga a definir un modelo de antemano, la aplicación va a ser muy estable y dificilmente llegué un dato no deseado a la BD. El problema es que es poco flexible y hacer cambios una vez arrancado el proyecto puede ser muy costoso.

*Estás bases de datos son transaccionales, es decir que el motor de DB nos asegura que las operaciones que hagamos van a hacerse atómicamente, es decir que jamás vamos a tener datos corruptos.

*Es una tecnología muy estudiada, hace años que ya está estable, en contrapartida con las bases de datos NoSQL que son relativamente nuevas.

MODELO ENTIDAD-RELACION

Los diagramas entidad-relación o el modelo entidad relación son un tipo de diagrama de flujo que posee entidades, atributos y relaciones. Estos elementos son indispensables en el ERD y su función es representarlos gráficamente y diseñar un modelo conceptual que permita señalar cómo los diferentes elementos se relacionan entre sí.
Generalmente, cuando se quiere hacer una base de datos, uno de los primeros pasos es diseñar el diagrama ER, ya que este brinda la perspectiva general de lo que será el modelo de datos, el conjunto de entidades y relaciones y su respectivo conjunto de atributo.
Un modelo entidad-relación nos ayuda, entre otras cosas, a entender las diferentes clases e identificadores de nuestra base de datos, clases que posteriormente pasarán a convertirse en tablas y atributos que se transformarán en campos.
Los modelos entidad relación se realizan en las primeras fases de desarrollo del proyecto. Usualmente es en la fase de análisis, después de hacer la especificación de requerimientos, ya que estos son los medios con los cuales se trabaja el diagrama entidad-relación.

 *Elementos del modelo entidad-relación
 
 ENTIDAD
 Las entidades representan cosas u objetos (ya sean reales o abstractos), que se diferencian claramente entre sí.
Para poder seguir un ejemplo durante el artículo añadiré ejemplos sobre un taller mecánico, donde se podría crear las siguientes entidades:

Coches (objeto físico): contiene la información de cada taller.

Empleado (objeto físico): información de los trabajadores.

Cargo del empleado (cosa abstracta): información de la función del empleado.

ATRIBUTOS
Los atributos definen o identifican las características de entidad (es el contenido de esta entidad). Cada entidad contiene distintos atributos, que dan información sobre esta entidad. Estos atributos pueden ser de distintos tipos (numéricos, texto, fecha...).

RELACION
Es un vínculo que nos permite definir una dependencia entre varias entidades, es decir, nos permite exigir que varias entidades compartan ciertos atributos de forma indispensable.

Relaciones de cardinalidad
Podemos encontrar distintos tipos de relaciones según como participen en ellas las entidades

*Uno a uno: Una entidad se relaciona únicamente con otra y viceversa. Por ejemplo, si tuviésemos una entidad con distintos chasis y otra con matrículas deberíamos de determinar que cada chasis solo puede tener una matrícula (y cada matrícula un chasis, ni más en ningún caso).

*Uno a varios o varios a uno: determina que un registro de una entidad puede estar relacionado con varios de otra entidad, pero en esta entidad existir solo una vez.En el caso anterior cada empleado puede tener un cargo, pero un mismo cargo lo pueden compartir varios empleados.

*Varios a varios: determina que una entidad puede relacionarse con otra con ninguno o varios registros y viceversa. Por ejemplo, en el taller un coche puede ser reparado por varios mecánicos distintos y esos mecánicos pueden reparar varios coches distintos.

CLAVES

Es el atributo de una entidad, al que le aplicamos una restricción que lo distingue de los demás registros (no permitiendo que el atributo específico se repita en la entidad) o le aplica un vínculo (exactamente como comentábamos en las relaciones). Estos son los distintos tipos:

Superclave: aplica una clave o restricción a varios atributos de la entidad, para así asegurarse que en su conjunto no se repitan varias veces y así no poder entrar en dudas al querer identificar un registro.

Clave primaria: identifica inequívocamente un solo atributo no permitiendo que se repita en la misma entidad. Como sería la matrícula o el número de chasis de un coche (no puede existir dos veces el mismo).

Clave externa o clave foránea: este campo tiene que estar estrictamente relacionado con la clave primaria de otra entidad, para así exigir que exista previamente ese clave. Anteriormente hemos hablado de ello cuando comentábamos que un empleado indispensablemente tiene que tener un cargo (que lo hemos representado numéricamente), por lo cual si intentásemos darle un cargo inexistente el gestor de bases de datos nos devolvería un error.
