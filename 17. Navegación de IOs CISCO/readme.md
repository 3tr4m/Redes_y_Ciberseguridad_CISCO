**Packet Tracer - Navega por el IOS**

# Objetivos

Parte 1: Establecer conexiones básicas, acceder a la CLI y explorar la Ayuda

Parte 2: Explorar los modos EXEC

Parte 3: Configurar el reloj (tiempo)

# Antecedentes/Escenario

En esta actividad, practicará las habilidades necesarias para navegar dentro de Cisco IOS, tales como los distintos modos de acceso de usuario, diversos modos de configuración y comandos comunes que se utilizan habitualmente. También practicará el acceso a la ayuda contextual mediante la configuración del comando **clock**.

# Instrucciones

## Parte 1: Establecer conexiones básicas, acceder a la CLI y explorar la ayuda

### Paso 1: Conectar la PC1 a S1 mediante un cable de consola.

a.     Haga clic en el icono de **Connections** (conexiones) (el que parece un rayo) en la esquina inferior izquierda de la ventana de Packet Tracer.

b.     Haga clic en el cable de consola celeste para seleccionarlo. El puntero del mouse cambia a lo que parece ser un conector con un cable que cuelga de él.

c.     Haga clic en **PC1**. Aparece una ventana que muestra una opción para una conexión RS-232. Conecte el cable al puerto RS-232.

d.     Arrastre el otro extremo de la conexión de consola al switch S1 (conmutador) y haga clic en el switch para acceder a la lista de conexiones.

e.     Seleccione el puerto **Console** para completar la conexión.

### Paso 2: Establecer una sesión de terminal con el S1.

a.     Haga clic en **PC1** y luego en la pestaña **Desktop**.

b.     Haga clic en el ícono de la aplicación **Terminal**. Verifique que los parámetros predeterminados de la configuración de puertos sean correctos.

#### Pregunta:

¿Cuál es el parámetro de bits por segundo?
>9600

c.     Haga clic en **OK**.

d.     La pantalla que aparece puede mostrar varios mensajes. En alguna parte de la pantalla tiene que haber un mensaje que diga **Press RETURN to get started!** Presione INTRO (ENTER).

#### Pregunta:

¿Cuál es la petición de entrada que aparece en la pantalla?
>`S1>`
### Paso 3: Examinar la ayuda de IOS.

a.     El IOS puede proporcionar ayuda para los comandos según el nivel al que se accede. La petición de entrada que se muestra actualmente se denomina **User EXEC** (Modo EXEC del usuario) y el dispositivo está esperando un comando. La forma más básica de solicitar ayuda es escribir un signo de interrogación (?) en la petición de entrada para mostrar una lista de comandos.

Abra la ventana de configuración

S1> **?**

#### Pregunta:

¿Qué comando comienza con la letra “C”?
>`connect`

b.     En el indicador, escriba **t** y luego un signo de interrogación (?).

S1> **t?**

#### Pregunta:

¿Qué comandos se muestran?
>`telnet terminal traceroute`

En el indicador, escriba **te** y luego un signo de interrogación (?).

S1> **te?**

#### Pregunta:

¿Qué comandos se muestran?
>`telnet terminal`

Este tipo de ayuda se conoce como ayuda sensible al contexto. Proporciona más información a medida que se expanden los comandos.

## Parte 2: Explorar los modos EXEC

En la parte de la actividad, debe cambiar al modo EXEC privilegiado y emitir comandos adicionales.

### Paso 1: Ingresar al modo EXEC con privilegios.

a.     En la petición de entrada, escriba el signo de interrogación (**?**).

S1> **?**

#### Pregunta:

¿Qué información se muestra para el comando **enable**?
>`Turn on privileged commands`

b.     Escriba **en** y presione la tecla **Tabulación**.

S1> **en<Tab>**

#### Pregunta:

¿Qué se muestra después de presionar la tecla **Tabulación**?
>`S1>enable`

Esto se llama finalización de comando (o finalización de tabulación). Cuando se escribe parte de un comando, la tecla **Tab** se puede utilizar para completar el comando parcial. Si los caracteres que se escriben son suficientes para formar un comando único, como en el caso del comando **enable**, se muestra la parte restante.

#### Pregunta:

¿Qué ocurriría si escribiera **te<Tab>** en la petición de entrada?
>Hay más de un comando que comienza con las letras "te" porque "te" no proporciona suficientes caracteres para que el comando sea único. Los caracteres continuarán apareciendo, solicitando al usuario caracteres adicionales para que el comando sea único.

c.     Introduzca el comando **enable** y presione ENTER.

#### Pregunta:

¿Cómo cambia la petición de entrada?
>Cambia de `S1>` a `S1#`, que indica el modo EXEC privilegiado.

d.     Cuando se le solicite, escriba el signo de interrogación (**?**).

S1# **?**

Antes había un comando que comenzaba con la letra “C” en el modo EXEC del usuario.

#### Pregunta:

¿Cuántos comandos se muestran ahora que está activo el modo EXEC privilegiado? (**Ayuda**: puede escribir c? para que aparezcan solo los comandos que comienzan con la letra “C”)
>`clear clock configure connect copy`

### Paso 2: Ingresar al modo de configuración global

a.     Cuando se encuentra en el modo EXEC privilegiado, uno de los comandos que comienza con la letra “C” es **configure**. Escribe el comando completo o una parte suficiente como para que sea único. Presione la tecla <**Tabulación**> para emitir el comando y presione la tecla ENTER.

S1# **configure**

#### Pregunta:

¿Cuál es el mensaje que se muestra?
>`Configuring from terminal, memory, or network [terminal]?`

b.     Presione Enter para aceptar el parámetro predeterminado que se encuentra entre corchetes **[terminal]**.

#### Pregunta:

¿Cómo cambia la petición de entrada?

c.     Esto se denomina modo de configuración global. Este modo se analizará en más detalle en las próximas actividades y prácticas de laboratorio. Por el momento, escriba **end**, **exit** o **Ctrl-Z** para volver al modo EXEC privilegiado.

S1(config)# **exit**

S1#

## Parte 3: Configuración del reloj

### Paso 1: Utilizar el comando clock.

a.     Utilice el comando **clock** para explorar en más detalle la ayuda y la sintaxis de comandos. Escriba **show clock** en el indicador EXEC privilegiado.

S1# **show clock**

#### Pregunta:

¿Qué información aparece en pantalla? ¿Cuál es el año que se muestra?
>`*23:12:33.679 UTC Sun Feb 28 1993`

b.     Use la ayuda contextual y el comando **clock** para configurar la hora del interruptor a la hora actual. Introduzca el comando **clock** y presione la tecla Intro.

S1# **clock<ENTER>**

#### Pregunta

¿Qué información aparece en pantalla?
>`% Incomplete command.`

c.     El mensaje “% Incomplete command” se regresa a IOS. Esto significa que el comando **clock** necesita más parámetros. Cuando se necesita más información, se puede proporcionar ayuda escribiendo un espacio después del comando y el signo de interrogación (?).

S1# **clock ?**

#### Pregunta:

¿Qué información aparece en pantalla?
>`set Set the time and date`

d.     Configure el reloj con el comando **clock set**. Proceda por el comando un paso a la vez.

S1# **clock set ?**

#### Preguntas:

¿Qué información se solicita?
>`hh:mm:ss  Current Time`

¿Qué información se habría mostrado si solo se hubiera ingresado el comando **clock set** y no se hubiera solicitado ayuda con el signo de interrogación?
>`% Incomplete command.`

e.     En función de la información solicitada por la emisión del comando **clock set ?**, introduzca las 3:00 p.m. como hora utilizando el formato de 24 horas, esto será 15:00:00. Revise si se necesitan otros parámetros.

S1# **clock set 15:00:00 ?**

El resultado devuelve la solicitud de más información:

<1-31> Day of the month

MONTH Month of the year

f.      Intente establecer la fecha en 01/31/2035 con el formato solicitado. Puede ser necesario solicitar ayuda adicional utilizando ayuda sensible al contexto para completar el proceso. Cuando termine, emita el comando **show clock** para mostrar la configuración del reloj. El resultado del comando debe mostrar lo siguiente:

S1# **show clock**

*15:0:4.869 UTC Wed Jan 31 2035

g.     Si no pudo lograrlo, pruebe con el siguiente comando para obtener el resultado anterior:

S1# **clock set 15:00:00 31 Jan 2035**

### Paso 2: Explorar los mensajes adicionales del comando.

a.     El IOS proporciona diversos resultados para los comandos incorrectos o incompletos. Continúe utilizando el comando **clock** para explorar los mensajes adicionales con los que se puede encontrar mientras aprende a utilizar el IOS.

b.     Emita los siguientes comandos y grabe los mensajes:

S1# **cl<enter>**

#### Preguntas:

¿Qué información se devolvió?
>`% Ambiguous command: "cl"`

S1# **clock**

#### Pregunta:

¿Qué información se devolvió?
>`% Incomplete command.`

S1# **clock set 25:00:00**

#### Pregunta:

¿Qué información se devolvió?
>```S1# clock set 25:00:00
>						  ^
>% Invalid input detected at '^' marker.```

S1# **clock set 15:00:00 32**

#### Pregunta:

¿Qué información se devolvió?
S1# clock set 15:00:00 32  
									  ^  
% Invalid input detected at '^' marker.
