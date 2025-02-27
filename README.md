# CLASE-12-DE-FEBRERO
# CONTROL METODO CASCADA
* Tener en cuenta el esquema P&D.
* Busca rechazar todas las pertubaciones.
* Los cambios en la corriente son perturbaciones.
C2 MAS RAPIDO QUE C1
(imagen)

## 1. TIPOS DE CONTROLADORES
LAZO MAS INTERNO:
* Lazo que quiero rechazar
* Poner un proporcional o controlador PI
* No poner controlador D ya que vuelve lento el sistema
LAZO EXTERNO:
* Utilizar PI
* Utilizar PID para garantizar llegar de la forma mas suave y eliminar el error de estado estacionario

Se utiliza para medir mas de una variable

## 2. CASOS DE APLICACIONES

**Caso 1:** Donde las perturbaciones afenten mucho el funcionamiento del sistema.

**Caso 2:** Donde tienen disponibles varibles mas rapidas que la variable controlada.

**Caso 3:** Donde se desea hacer mas rapida la dinamica de la variable controlada.


## 3. METODOS DE SINTONIZACIÓN
**Empiricas:**
* lazo Abierto

* Lazo Cerrado

**Basados en modelos rigurosos**
* Inteligencia computacional*

### 3.1 EMPIRICO LAZO ABIERTO
* Modelo e la variable principal

* Modelo de las demas variables

**Ejercicio:**
(imagen 2)
(imagen 3)

  $G2=\frac{0.5e^-s}{2s+1}$
  
  $G1=\frac{e^-10s}{15s+1}$  

  G2 es mas rapido, esto se puede deducir gracias al tao.

  De acuerdo a esto vamos a realizar el siguente despeje
  
  $Kc2=\frac{0.9xT2}{k2xtm}$
  $R=\frac{0.9*2}{0.5}$  
  $=36$
  
  $Ti2=3.33$
  
  $tm=3.33$

  ### 3.2 SINTONIZACION LAZO PRIMARIO

  $KTotal=k1x1=1$

  $Tmtotal=tm1+tm2$

  $Kc1=\frac{1.2 x tTotal}{KTotal x tmTotal}=\frac{1.2 x 15}{1 x 11}=1.63$
  
  $Tc1=2 tmTotal=2 x 11=22$

 ### 3.2 LAZO ABIERTO EMPIRICO AUSTIN

*Sin realizar separacion de los modelos

*Sintonizar controladores primarios y secundarios en una sola prueba

#### Sintonizar

*El primer lazo que se sintoniza es el interno

* El lazo externo tiene unas formulas estandar

* Se consideran las entradas del sistema

| **condiciones** | **PI** |        **PID**        |
|-----------------| To<To1 |         To<To1        |
|       S         |        |$\frac{To1=To1}{2}>0.08|

## 4. Ejemplos
Si en algún caso pretende dar un ejemplo explicativo ya sea a través de texto o através de ecuaciones matemáticos, utilizar la palabra 'Ejemplo' seguido de una numeración consecutiva dentro de la clase. Utilice el emoji 💡 antecediendo la palabra.

## 5. Ecuaciones
Para la edición de ecuaciones debe utilizar la etiqueta '$$' al comienzo y final de la ecuación para que la ecuación quede centrada ocupando una línea. Si se quiere que la ecuación quede integrada en el texto debe utilizar la etiqueta '$' al comienzo y final de la ecuación. Las ecuaciones pueden ser editadas utilizando el código LATEX, en el siguiente enlace encuentran un editor de ecuaciones que les genera el código. http://www.alciro.org/tools/matematicas/editor-ecuaciones.jsp . Sin embargo hay muchas otras herramientas que pueden utilizar para esto.

💡**Ejemplo 1:** si se va a representar la ecuación de la ley de Ohm se puede mostrar así $R=\frac{V}{I}$ o también,

$$R=\frac{V}{I}$$

## 6. Figuras
Todas las figuras que incluya deben ser generadas por ustedes, **no utilizar las figuras de las presentaciones**. Para incluir figuras puede seguir los siguientes pasos:
* Primero escribimos ![]().
* Después escribimos, dentro de los corchetes, el texto alternativo. Este es opcional y solo entra en acción cuando no se puede cargar la imagen correctamente.
* Después escribimos, dentro de los paréntesis, la ubicación del archivo (ya sea una url o una ubicación dentro de algun folder local). Se recomienda poner las imágenes en una carpeta que se llame imágenes dentro del repositorio github para que no tengan problemas al cargar las imágenes.

💡**Ejemplo 2:**

![Figura de prueba](images/plantilla/Captura2.PNG)

Figura 1. Figura de prueba

Incluya la respectiva etiqueta a modo de descripción de la figura y mantenga numeración consecutiva para todas las figuras de la clase.

## 7. Tablas
En caso de necesitar la inclusión de tablas para organizar información se recomienda el uso de la herramienta del siguiente enlace https://www.tablesgenerator.com/markdown_tables , la cual permite organizar la información dentro de la tabla y genera el código markdown automáticamente:

💡**Ejemplo 3:** 

| **Resultado** | **x = número de intentos hasta primer éxito** |
|---------------|-----------------------------------------------|
|       S       |                       1                       |
|       FS      |                       2                       |
|      FFS      |                       3                       |
|      ...      |                      ...                      |
|    FFFFFFS    |                       7                       |
|      ...      |                      ...                      |

Tabla 1. Tabla de ejemplo

Cada tabla debe llevar la etiqueta que describa su contenido y numeración consecutiva para todas las tablas

## 8. Código
Teniendo en cuenta que el curso requiere del desarrollo de código matlab, c, c++ u otro. Si requiere incluir pequeños segmentos de código en los apuntes hágalos de la siguiente manera:

💡**Ejemplo 4:**
```
var sumar2 = function(numero) {
  return numero + 2;
}
```

## 9. Ejercicios
Deben agregar 2 ejercicios con su respectiva solución, referentes a los temas tratados en cada una de las clases. Para agregar estos, utilice la etiqueta #, es decir como un nuevo título dentro de la clase con la palabra 'Ejercicios'. Cada uno de los ejercicios debe estar numerado y con su respectiva solución inmediatamente despues del enunciado. Antes del subtitulo de cada ejercicio incluya el emoji 📚

## Rúbrica
| 0-1                                                                                   | 1-2                                                                                  | 2-3                                                                                                                                                                               | 3-4                                                                                                                                                                       | 4-5                                                                                                                                                                               |
|---------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Presenta menos del 10% de los temas o no presenta por  el medio y formato  solicitado | Presenta menos del 40% de los temas solicitados, y  cumple parcialmente la plantilla | Presenta menos del 60% de los temas solicitados (con descripciones, gráficos tablas, etc), y cumple  parcialmente la plantilla. No presenta la totalidad  de ejercicios resueltos | Presenta menos del 80% de los temas solicitados (con descripciones, gráficos, tablas, etc) y cumple con  la plantilla. No presenta  la totalidad de ejercicios  resueltos | Presenta el 100% de los temas vistos en clase (con descripciones, gráficos, tablas, etc), siguiendo totalmente la plantilla. presenta la  totalidad de los ejercicios solicitados |

## 10. Conclusiones
Agregue unas breves conclusiones sobre los temas trabajados en cada clase, puede ser a modo de resumen de lo trabajado o a indicando lo aprendido en cada clase

## 11. Referencias
Agregue un subtítulo al final donde pueda poner todas las referencias consultadas incluyendo el origen o fuente de los ejercicios planteados. Tambien dentro del texto referencie los textos o artículos consultados y las figuras y tablas dentro de la explicación de las mismas.
