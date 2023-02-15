# **Packet Tracer: Comunicaciones de TCP y UDP**

# Objetivos

Parte 1: Generar tráfico de red en el modo de simulación

Parte 2: Examinar la funcionalidad de los protocolos TCP y UDP

# Aspectos básicos

Esta actividad de simulación está destinada a proporcionar una base para comprender TCP y UDP en detalle. El modo de simulación Packet Tracer le proporciona la capacidad de ver el estado de diferentes PDU a medida que viajan a través de la red.

El modo de simulación de Packet Tracer le permite ver cada uno de los protocolos y las PDU asociadas. Los pasos descritos a continuación lo guían a través del proceso de solicitud de servicios de red utilizando diversas aplicaciones que están disponibles en una PC cliente. Explorará la funcionalidad de los protocolos TCP y UDP, la multiplexación y la función de los números de puerto para determinar qué aplicación local solicitó los datos o los envía. Packet Tracer no marcará esta actividad.

# Instrucciones

## Parte 1: Genere tráfico de red en modo de simulación y vea multiplexación

### Paso 1: Generar tráfico para completar las tablas del protocolo de resolución de direcciones (ARP)

Realice la siguiente tarea para reducir la cantidad de tráfico de red que se ve en la simulación.

a.     Haga clic en **MultiServer** y luego haga click en **Desktop** tab > **Command Prompt**.

b.     Ingrese el comando **ping -n 1 192.168.1.255** . Está haciendo ping a la dirección de difusión de la LAN del cliente. La opción de comando enviará sólo una solicitud de ping en lugar de las cuatro habituales. Esto tomará unos segundos ya que cada dispositivo en la red responde a la solicitud de ping de MultiServer.

c.     Cierre la ventana **MultiServer**.

### Paso 2: Generar tráfico web (HTTP).

a.     Cambie a modo de simulación.

b.     Haga clic en **HTTP Client** (Cliente HTTP) y abra el **Web Browser** (Explorador Web) desde el escritorio.

c.     En el campo URL, introduzca **192.168.1.254** y haga clic en **Go** (Ir). Los sobres (PDU) aparecerán en la ventana de topología.

d.     Minimice, pero no cierre, la ventana de configuración de **HTTP Client** (Cliente HTTP).

### Paso 3: Generar tráfico FTP.

a.     Haga clic en **FTP Client** y abra el **Command Prompt** (Símbolo del Sistema) desde el escritorio.

b.     Introduzca el comando **ftp 192.168.1.254**. Las PDU aparecerán en la ventana de simulación.

c.     Minimice, pero no cierre, la ventana de configuración de **FTP Client**.

### Paso 4: Generar tráfico DNS.

a.     Haga clic en DNS Client y abra el **Command Prompt** (Símbolo del Sistema).

b.     Introduzca el comando **nslookup multiserver.pt.ptu**. Aparecerá una PDU en la ventana de simulación.

c.     Minimice, pero no cierre, la ventana de configuración de **DNS Client**.

### Paso 5: Generar tráfico de correo electrónico.

a.     Haga clic en **E-Mail Client** y abra la herramienta **E Mail** desde el escritorio.

b.     Haga clic en **Compose** (Redactar) y escriba la siguiente información:

1)    **To:** user@multiserver.pt.ptu

2)    **Subject:** Personalizar la línea de asunto

3)    **E-Mail Body:** personalizar el correo electrónico

c.     Haga clic en **Send** (Enviar).

d.     Minimice, pero no cierre, la ventana de configuración de **E-Mail Client**.

### Paso 6: Verificar que se haya generado tráfico y que esté preparado para la simulación.

Ahora debería haber entradas de PDU en el panel de simulación para cada uno de los equipos cliente.

### Paso 7: Examinar la multiplexión a medida que el tráfico cruza la red.

Ahora utilizará el **botón Capture/Forward** (Capturar/Reenviar) del Panel de Simulación para observar los diferentes protocolos que viajan por la red.

**Nota**: El botón Capture/Forward ' **>|** ' es una flecha pequeña que apunta a la derecha con una barra vertical al lado.

a.     Haga clic una vez en **Capture/Forward** (Capturar/Reenviar). Todas las PDU se transfieren al switch.

b.     Haga clic en **Capture/Forward** (Capturar/Reenviar) seis veces y observe las PDU de los diferentes hosts mientras viajan por la red. Observe que solo una PDU puede cruzar un cable en cada dirección en un momento determinado.

#### Preguntas:

¿Cómo se llama esto?
>Conversación multiplexación.

Aparece una variedad de PDU en la lista de eventos en el Panel de simulación. ¿Cuál es el significado de los diferentes colores?
>Representan diferentes protocolos.

## Parte 2: Examinar la funcionalidad de los protocolos TCP y UDP

### Paso 1: Examinar el tráfico HTTP cuando los clientes se comunican con el servidor.

a.     Haga clic en **Reset Simulation (Restablecer simulación)**.

b.     Filtrar el tráfico que se muestra actualmente sólo a las PDU **HTTP** y **TCP** . Para filtrar el tráfico que se muestra actualmente:

1)    Haga clic en **Edit Filters** y alternar el botón **Show All/None** .

2)    Seleccione **HTTP y TCP**. Haga clic en la «x» roja en la esquina superior derecha del cuadro Editar filtros para cerrarla. Los eventos visibles ahora deberían mostrar solo las PDU **HTTP** y **TCP** .

c.     Abra el navegador en HTTP Client e ingrese **192.168.1.254** en el campo URL. Haga clic en **Go** (Ir) para conectarse al servidor a través de HTTP. Minimice la ventana del Cliente HTTP.

d.     Haga clic en **Capture/Forward** (Capturar/Reenviar) hasta que aparezca una PDU para HTTP. Tenga en cuenta que el color del envolvente de la ventana de topología coincide con el código de color de la PDU HTTP del Panel de simulación.

#### Pregunta:

¿Por qué tardó tanto en aparecer la PDU HTTP?
>Porque TCP primero debe establecer la conexión para que el tráfico HTTP pueda comenzar.

e.     Haga clic en el sobre de la PDU para mostrar los detalles de la PDU. Haga clic en **Outbound PDU Details** y desplácese hacia abajo hasta la segunda sección.

#### Preguntas:

¿Cómo se rotula la sección?
>TCP.

¿Se consideran confiables estas comunicaciones?
>Sí, porque usa TCP. 

Registre los valores de **SRC PORT** (PUERTO DE ORIGEN), **DEST PORT** (PUERTO DE DESTINO), **SEQUENCE NUM** (NÚMERO DE SECUENCIA) y **ACK NUM** (NÚMERO DE RECONOCIMIENTO).
>1029, 80, 1, 1

f.      Mire el valor en el campo Indicadores, que se encuentra junto al campo Ventana. Los valores a la derecha de la «b» representan los indicadores TCP que se establecen para esta etapa de la conversación de datos. Cada uno de los seis lugares corresponde a una bandera. La presencia de un «1» en cualquier lugar indica que el indicador está establecido. Se puede configurar más de una bandera a la vez. Los valores de las banderas se muestran a continuación.

| Lugar de la bandera |  6  |  5  |  4  |  3  |  2  |  1  |
| ------------------- |:---:|:---:|:---:|:---:|:---:|:---:|
| Valor               | URG | ACK | PSH | RST | SYN | FIN | 

¿Qué indicadores TCP se establecen en esta PDU?
>ACK y PSH

g.     Cierre la PDU y haga clic en **Capture/Forward** (Capturar/Reenviar) hasta que una PDU con una marca de verificación regrese al **HTTP Client**.

h.     Cierre el sobre de PDU y seleccione **Inbound PDU Details**.

#### Pregunta:

¿En qué cambiaron los números de puerto y de secuencia?
>Los puertos de origen y destino están invertidos, y el número de reconocimiento es 1. Las banderas han cambiado a SYN + ACK.

i.      Haga clic en la PDU HTTP que **HTTP Client** ha preparado para enviar a **MultiServer** . Este es el comienzo de la comunicación HTTP. Haga clic en este segundo sobre de PDU y seleccione **Outbound PDU Details** (Detalles de PDU saliente).

#### Pregunta:

¿Qué información aparece ahora en la sección TCP? ¿En qué se diferencian los números de puerto y de secuencia con respecto a las dos PDU anteriores?
>Los puertos de origen y destino se invierten, el número de secuencia es 1, el número de reconocimiento es 103 (el valor puede variar) y los indicadores son PSH y ACK.

j.      Restablecer la simulación.

### Paso 2: Examinar el tráfico FTP cuando los clientes se comunican con el servidor.

a.     Abra el símbolo del sistema en el escritorio del cliente FTP. Inicie una conexión FTP ingresando **ftp 192.168.1.254**.

b.     En el panel de simulación, modifique las opciones de **Edit Filters** para que solo se muestren **FTP** y **TCP**.

c.     Haga clic en **Capture/Forward** (Capturar/Reenviar). Haga clic en el segundo sobre PDU para abrirlo.

Haga clic en la pestaña **Outbound PDU Details** y desplácese hacia abajo hasta la sección TCP.

#### Pregunta:

¿Se consideran confiables estas comunicaciones?
>Sí.

d.     Registre los valores de **SRC PORT** (PUERTO DE ORIGEN), **DEST PORT** (PUERTO DE DESTINO), **SEQUENCE NUM** (NÚMERO DE SECUENCIA) y **ACK NUM** (NÚMERO DE RECONOCIMIENTO).

#### Pregunta:

¿Cuál es el valor en el campo de bandera?
>1025, 21, 0, 0. SYN

e.     Cierre la PDU y haga clic en **Capture/Forward** (Capturar/Reenviar) hasta que una PDU vuelva a **FTP Client** con una marca de verificación.

f.      Cierre el sobre de PDU y seleccione **Inbound PDU Details**.

#### Pregunta:

¿En qué cambiaron los números de puerto y de secuencia?
>21, 1025, 0, 1. SYN+ACK. Los puertos de origen y destino están invertidos, y el número de reconocimiento es 1.

g.     Haga clic en la pestaña **Outbound** **PDU Details**.

#### Pregunta:

¿En qué se diferencian los números de puerto y secuencia de los resultados anteriores?
>1025, 21, 1, 1. Los puertos de origen y destino están invertidos, y tanto el número de secuencia como el de reconocimiento son 1.

h.     Cierre la PDU y haga clic en **Capture/Forward** (Capturar/Reenviar) hasta que una segunda PDU vuelva a **FTP Client**. La PDU es de un color diferente.

i.      Abra la PDU y seleccione **Inbound PDU Details**. Desplácese hasta después de la sección TCP.

#### Pregunta:

¿Cuál es el mensaje del servidor?
>«Bienvenido al servidor FTP PT»

j.      Haga clic en **Reset Simulation** (Restablecer simulación).

### Paso 3: Examinar el tráfico DNS cuando los clientes se comunican con el servidor.

a.     Repita los pasos de la Parte 1 para crear tráfico DNS.

b.     En el panel de simulación, modifique las opciones de **Edit Filters** para que solo se muestren **DNS** y **UDP**.

c.     Haga clic en el sobre de PDU para abrirlo.

d.     Mire los detalles del modelo OSI para la PDU saliente.

#### Pregunta:

¿Qué es el protocolo de capa 4?
>UDP.

¿Se consideran confiables estas comunicaciones?
>No.

e.     Abra la ficha Detalles de PDU saliente y busque la sección UDP de los formatos de PDU. Registre los valores de **SRC PORT** (PUERTO DE ORIGEN) y **DEST PORT** (PUERTO DE DESTINO).

#### Pregunta:

¿Por qué no hay números de secuencia y reconocimiento?
>UDP no utiliza esos campos

f.      Cierre la **PDU** y haga clic en **Capture/Forward** (Capturar/Reenviar) hasta que una PDU con una marca de verificación regrese al **DNS Client**.

g.     Cierre el sobre de PDU y seleccione **Inbound PDU Details**.

#### Pregunta:

¿En qué cambiaron los números de puerto y de secuencia?
>53, 1025. Los puertos de origen y destino están invertidos.

¿Cómo se llama la última sección de la **PDU**? ¿Cuál es la dirección IP para el nombre **multiserver.pt.ptu**?
>RESPUESTA DNS, 192.1681.254.

h.     Haga clic en **Reset Simulation** (Restablecer simulación).

### Paso 4: Examinar el tráfico de correo electrónico cuando los clientes se comunican con el servidor.

a.     Repita los pasos de la Parte 1 para enviar un correo electrónico a **user@multiserver.pt.ptu**.

b.     En el panel de simulación, modifique las opciones de **Edit Filters** para que solo se muestren **POP3, SMTP** y **TCP**.

c.     Haga clic en el primer sobre de la PDU para abrirlo.

d.     Haga clic en la pestaña **Outbound PDU Details** y desplácese hacia abajo hasta la última sección.

#### Preguntas:

¿Qué protocolo de la capa de transporte utiliza el tráfico de correo electrónico?
>TCP.

¿Se consideran confiables estas comunicaciones?
>Sí.

e.     Registre los valores de **SRC PORT** (PUERTO DE ORIGEN), **DEST PORT** (PUERTO DE DESTINO), **SEQUENCE NUM** (NÚMERO DE SECUENCIA) y **ACK NUM** (NÚMERO DE RECONOCIMIENTO). ¿Cuál es el valor del campo de bandera?
>1025 (el valor puede variar), 25, 0, 0. SYN

f.      Cierre la **PDU** y haga clic en **Capture/Forward** (Capturar/Reenviar) hasta que una PDU regrese al **E-Mail Client** con una marca de verificación.

g.     Haga clic en el sobre TCP PDU y seleccione **Inbound PDU Details**.

#### Pregunta:

¿En qué cambiaron los números de puerto y de secuencia?
>25, 1025, 0, 1. SYN+ACK. Los puertos de origen y destino están invertidos, y el número de reconocimiento es 1.

h.     Haga clic en la pestaña **Outbound** **PDU Details**.

#### Pregunta:

¿En qué se diferencian los números de puerto y de secuencia con respecto a los dos resultados anteriores?
>1025, 25, 1, 1. ACK. Los puertos de origen y destino están invertidos, y tanto el número de secuencia como el de reconocimiento son 1. ACK

i.      Hay una segunda **PDU** de un color diferente que **E-Mail Client** ha preparado para enviar a **MultiServer**. Este es el comienzo de la comunicación de correo electrónico. Haga clic en este segundo sobre de PDU y seleccione **Outbound PDU Details**.

#### Preguntas:

¿En qué se diferencian los números de puerto y de secuencia con respecto a las dos **PDU** anteriores?
>1025, 25, 1, 1. PSH+ACK. Los puertos de origen y destino están invertidos, y tanto el número de secuencia como el de reconocimiento son 1.

¿Qué protocolo de correo electrónico se relaciona con el puerto TCP 25? ¿Qué protocolo se relaciona con el puerto TCP 110?
>SMTP. POP3
