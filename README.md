# CLASE-12-DE-FEBRERO
El control en cascada es una estrategia avanzada de control que se utiliza en sistemas complejos donde es necesario manejar múltiples variables interrelacionadas. Este método se basa en la implementación de dos o más lazos de control anidados, donde el lazo interno (secundario) actúa más rápidamente para rechazar perturbaciones antes de que afecten al lazo externo (primario). En el contexto de un esquema de Proceso y Diseño (P&D), el control en cascada es particularmente útil para mejorar la estabilidad y la precisión del sistema. El lazo interno se encarga de controlar variables que cambian rápidamente, como la corriente en un sistema eléctrico, mientras que el lazo externo gestiona variables de mayor nivel, como la temperatura o la presión, que son más lentas en su respuesta.

Uno de los objetivos principales del control en cascada es rechazar todas las perturbaciones que puedan afectar al sistema. En este caso, los cambios en la corriente son considerados perturbaciones, ya que pueden alterar el funcionamiento óptimo del proceso. El lazo interno detecta y corrige estas variaciones de corriente de manera inmediata, evitando que se propaguen y afecten al lazo externo. Esto se logra mediante el uso de sensores y actuadores que monitorean y ajustan la corriente en tiempo real, manteniendo el sistema en un estado estable.


C2 MAS RAPIDO QUE C1

![Image](https://github.com/user-attachments/assets/ba2b77fb-e946-44b2-9069-22d5d53e176e)


## 1. TIPOS DE CONTROLADORES
En el diseño de sistemas de control, la selección adecuada de los tipos de controladores para cada lazo es fundamental para garantizar un funcionamiento óptimo. En el caso del control en cascada, el lazo más interno juega un papel crítico, ya que es el encargado de rechazar las perturbaciones de manera rápida y eficiente. Para este lazo, se recomienda utilizar un controlador proporcional (P) o un controlador proporcional-integral (PI). El control proporcional permite una respuesta rápida a los cambios, mientras que la acción integral ayuda a eliminar el error en estado estacionario. Sin embargo, es importante evitar el uso de un controlador derivativo (D) en este lazo, ya que puede ralentizar el sistema y hacerlo menos reaccionar ante perturbaciones rápidas, como cambios en la corriente o en otras variables dinámicas.

Por otro lado, el lazo externo, que gestiona variables de mayor nivel y más lentas, como la temperatura o la presión, puede beneficiarse de un controlador proporcional-integral (PI) o incluso de un controlador proporcional-integral-derivativo (PID). El controlador PI es adecuado para mantener la estabilidad y corregir errores de estado estacionario, mientras que el controlador PID añade la acción derivativa, lo que permite una respuesta más suave y precisa, especialmente útil para garantizar que el sistema alcance el punto de consigna sin oscilaciones excesivas. La acción derivativa en el lazo externo ayuda a anticipar cambios y a reducir el tiempo de estabilización, lo que es crucial para procesos que requieren alta precisión.

* **Caso 1: Donde las perturbaciones afectan mucho el funcionamiento del sistema.**
En sistemas donde las perturbaciones externas o internas tienen un impacto significativo en el desempeño, el control en cascada es ideal para mitigar estos efectos. Por ejemplo, en un proceso químico donde cambios bruscos en la temperatura ambiente o en la presión de alimentación pueden alterar la estabilidad del sistema, el lazo interno del control en cascada se encarga de rechazar rápidamente estas perturbaciones antes de que afecten al lazo externo. Esto asegura que el sistema mantenga su operación óptima, incluso en presencia de factores externos impredecibles.

* **Caso 2: Donde se tienen disponibles variables más rápidas que la variable controlada.**
El control en cascada es especialmente útil cuando se dispone de variables secundarias que responden más rápidamente que la variable principal que se desea controlar. Por ejemplo, en un sistema de control de temperatura en un reactor químico, la corriente eléctrica que alimenta un calentador puede ser una variable rápida, mientras que la temperatura del reactor es una variable más lenta. El lazo interno controla la corriente de manera rápida y precisa, mientras que el lazo externo ajusta la temperatura global. Esta jerarquía permite una respuesta más ágil y un control más efectivo del proceso.

* **Caso 3: Donde se desea hacer más rápida la dinámica de la variable controlada.**
En situaciones donde se necesita acelerar la respuesta del sistema, el control en cascada puede mejorar significativamente la dinámica de la variable controlada. Por ejemplo, en un sistema de control de nivel en un tanque, el flujo de entrada puede ser controlado por el lazo interno, mientras que el nivel del tanque es gestionado por el lazo externo. Al utilizar un controlador rápido en el lazo interno, se reduce el tiempo de respuesta del sistema, permitiendo que el nivel del tanque se ajuste de manera más rápida y precisa a los cambios en la demanda o en las condiciones de operación.

## 3. METODOS DE SINTONIZACIÓN

Estos métodos se basan en la experimentación y la observación del comportamiento del sistema, sin requerir un modelo matemático detallado. Son útiles cuando el sistema es complejo o no se dispone de información precisa sobre su dinámica.

* **Lazo Abierto:**
En este método, se aplica una entrada conocida al sistema (como un escalón o una rampa) y se observa la respuesta del sistema en ausencia de retroalimentación. A partir de esta respuesta, se pueden determinar parámetros clave, como el tiempo de retardo, la constante de tiempo y la ganancia del sistema. Estos parámetros se utilizan luego para ajustar los controladores (P, PI, PID) utilizando reglas prácticas, como las de Ziegler-Nichols. Este enfoque es sencillo pero puede ser menos preciso en sistemas con perturbaciones o no linealidades.

* **Lazo Cerrado:**
A diferencia del método de lazo abierto, aquí se utiliza retroalimentación para ajustar los parámetros del controlador. Un ejemplo clásico es el método de Ziegler-Nichols en lazo cerrado, donde se incrementa la ganancia del controlador proporcional hasta que el sistema alcanza una oscilación sostenida. A partir de la frecuencia y la amplitud de estas oscilaciones, se calculan los parámetros del controlador PID. Este método es más robusto que el de lazo abierto, ya que considera la dinámica del sistema en condiciones reales de operación.

Métodos Basados en Modelos Rigurosos:
Estos métodos requieren un modelo matemático preciso del sistema, lo que permite un diseño y sintonización más exactos del controlador. Son ideales para sistemas complejos donde se necesita un alto nivel de precisión.

* **Modelado Matemático:**
Se utiliza un modelo matemático detallado del sistema, que puede incluir ecuaciones diferenciales, funciones de transferencia o representaciones en espacio de estados. A partir de este modelo, se aplican técnicas como el lugar geométrico de las raíces, el criterio de Routh-Hurwitz o métodos de optimización para ajustar los parámetros del controlador. Este enfoque es muy preciso pero requiere un conocimiento profundo del sistema y su dinámica.

* **Inteligencia Computacional:**
En este enfoque, se utilizan técnicas avanzadas como redes neuronales, algoritmos genéticos, lógica difusa o sistemas de aprendizaje automático para sintonizar los controladores. Estos métodos son especialmente útiles en sistemas no lineales, multivariables o con incertidumbres, donde los métodos tradicionales pueden fallar. Por ejemplo, un algoritmo genético puede explorar múltiples combinaciones de parámetros del controlador para encontrar la que optimice el desempeño del sistema según un criterio específico, como el error cuadrático medio o el tiempo de estabilización.

### 3.1 EMPIRICO LAZO ABIERTO

En el método de sintonización empírica en lazo abierto, se utiliza un modelo de la variable principal para analizar su respuesta dinámica. Por ejemplo, si la variable principal es la temperatura en un reactor, se aplica una entrada en escalón al sistema (como un cambio en la potencia del calentador) y se mide cómo evoluciona la temperatura en el tiempo. A partir de esta respuesta, se identifican parámetros como la ganancia estática (K), el tiempo de retardo (L) y la constante de tiempo (T), que permiten diseñar el controlador utilizando reglas como las de Ziegler-Nichols.

Para modelar las demás variables, como la presión o el flujo en el mismo reactor, se sigue un procedimiento similar. Cada variable secundaria se analiza individualmente, aplicando una entrada en escalón y observando su respuesta. Estos modelos permiten entender cómo las variables secundarias interactúan con la principal y cómo afectan la dinámica global del sistema. Sin embargo, al trabajar en lazo abierto, este método no considera perturbaciones ni interacciones dinámicas complejas, lo que puede limitar su precisión en sistemas con múltiples variables interdependientes.

**Ejercicio:**

![Image](https://github.com/user-attachments/assets/b1298e4e-62fb-4099-a6dc-4604228441d3)

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

El método de sintonización en lazo abierto Austin es una técnica empírica que permite ajustar los controladores primarios y secundarios sin necesidad de separar los modelos de las variables involucradas. A diferencia de otros métodos que requieren analizar cada variable por separado, este enfoque realiza una única prueba para sintonizar ambos controladores de manera simultánea.

En este método, se aplica una entrada en escalón al sistema y se observa la respuesta conjunta de las variables primarias y secundarias. A partir de esta respuesta, se identifican los parámetros clave, como las constantes de tiempo (τ) y las ganancias (K), para ambos lazos. Luego, utilizando reglas empíricas o algoritmos de ajuste, se calculan los parámetros de los controladores primario y secundario en un solo paso.

La ventaja de este enfoque es que simplifica el proceso de sintonización, especialmente en sistemas donde las variables están fuertemente acopladas y no es práctico separar sus dinámicas. Sin embargo, puede ser menos preciso en sistemas con interacciones complejas o no linealidades significativas, ya que no considera por completo las perturbaciones o las dinámicas individuales de cada variable.

#### Sintonizar

*El primer lazo que se sintoniza es el interno

* El lazo externo tiene unas formulas estandar

* Se consideran las entradas del sistema

| **condiciones** | **PI** |        **PID**        |
|-----------------|--------|-----------------------|
|      ...        | To<To1 |         To<To1        |
|      ...        |   ...  |  (To1-To2)/(2)>0.08   |

*Con el metodo de cascada muy rara ves se sobre pasa del setpoint

### 3.3 LAZO CERRADO

#### Metodo Hang

* Sintonizar metodo rele

* Se sintetiza por aparte, es una sintonización mas facil de realizar

* Se mide el periodo Ultimo y amplitud tener la ganacia ultima

![Image](https://github.com/user-attachments/assets/e629fbe3-d516-40a5-84c6-73a2da2065c6)

$To2=0.39$

$Ku2=\frac{4d}{pixa}$ 

![Image](https://github.com/user-attachments/assets/557e7767-b8f5-4373-8759-39e0b8814fdd)



