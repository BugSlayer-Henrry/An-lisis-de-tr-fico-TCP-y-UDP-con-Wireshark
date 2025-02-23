# Análisis de tráfico TCP y UDP con Wireshark
# Laboratorio: Analizando Tráfico TCP y UDP con Wireshark


## Objetivos
Después de completar este laboratorio, podrás analizar el tráfico de red TCP y UDP. También podrás demostrar las habilidades necesarias para instalar, configurar y utilizar una herramienta de análisis de red de código abierto, Wireshark, para realizar estas tareas.

## Herramientas Necesarias
Wireshark, una herramienta de análisis de red de código abierto y sin costo, instalada en tu computadora.

**Nota:** Wireshark está disponible para MacOS así como para Microsoft Windows. Este laboratorio utiliza la versión de Windows de esta aplicación.

## Instrucciones para Descargar e Instalar Wireshark

### Descargando Wireshark
Para descargar Wireshark, visita el sitio web oficial de Wireshark:

[https://www.wireshark.org/download.html](https://www.wireshark.org/download.html)

Selecciona el instalador de Windows para descargar la última versión estable de Wireshark.

### Instalación de Wireshark
1. Localiza el instalador en tu máquina.
2. Haz clic en el instalador y sigue las instrucciones en pantalla, aceptando las opciones predeterminadas.
3. Durante la instalación, es posible que se te pida instalar WinPcap o Npcap (necesarios para capturar tráfico de red). Si es así, elige **Sí** y completa la instalación.
4. **Importante:** Si ejecutas Wireshark en un entorno virtual, no reinicies ni reinicies el entorno.

## Configuración de Wireshark para Análisis de Red

### Ejecutar Wireshark como Administrador
Si Wireshark no está en ejecución, haz clic derecho en el icono de Wireshark y selecciona **Ejecutar como Administrador**.

### Configura tus Interfaces de Red
1. Al iniciar Wireshark, la aplicación muestra una lista de interfaces de red disponibles, incluyendo redes inalámbricas y Ethernet.
2. Selecciona la interfaz que deseas monitorear. Típicamente, esta interfaz será tu conexión de red activa, como tu red inalámbrica y Ethernet.

### Configurar Filtros de Captura (Opcional)
Antes de iniciar una captura, puedes configurar filtros para centrarte en tráfico específico como `tcp`, `udp` o puertos específicos.

Para añadir filtros, localiza el campo **Filtro de Captura** en la pantalla principal, o después de iniciar la captura, puedes introducir filtros en la barra **Filtro de Visualización**.

### Probando la Instalación
1. Inicia una nueva captura seleccionando tu interfaz de red y haciendo clic en el ícono de **aleta de tiburón azul (Iniciar Captura)**.
2. Abre un navegador web y visita cualquier sitio web para generar tráfico.
3. Detén la captura después de unos segundos haciendo clic en el ícono de **cuadrado rojo (Detener Captura)**.
4. Deberías ver los paquetes capturados mostrados en Wireshark, confirmando que la instalación está funcionando correctamente.

### Guardando tu Captura (Opcional)
Después de detener la captura, puedes guardar el archivo de captura para un análisis posterior seleccionando **Archivo > Guardar Como…** y eligiendo una ubicación en tu sistema.

## Tareas

### Captura de Tráfico TCP
1. Haga clic derecho en el ícono de Wireshark y seleccione **Ejecutar como Administrador** para iniciar una nueva sesión de captura.![image](https://github.com/user-attachments/assets/36747f1b-1956-4592-a7ce-a911314dda51)

2. En la barra de filtros, ingrese `tcp` y seleccione **Enter** para filtrar paquetes TCP.![image](https://github.com/user-attachments/assets/8ab64afc-b656-49e2-8b35-90fdd5c764b9)

3. Abra un navegador web y visite un sitio web, como [https://www.ibm.com/in-en](https://www.ibm.com/in-en) para generar tráfico TCP.
4. Detenga la captura después de unos segundos.
**Capturar datos TCP**
   - Examina los paquetes capturados. Identifica los paquetes involucrados en el **apretón de manos de tres vías de TCP**, incluyendo SYN, SYN-ACK y ACK. ![image](https://github.com/user-attachments/assets/95dae1a1-8a8f-4f4e-9946-af77328f951d)

   - Examina el encabezado TCP en busca de números de secuencia, reconocimientos y banderas como SYN y ACK.![image](https://github.com/user-attachments/assets/240d2690-0d3c-4e19-a728-a5fe6c5cda00)


### Captura de Tráfico UDP
1. En Wireshark, borra la captura anterior y comienza una nueva sesión.![image](https://github.com/user-attachments/assets/6b5b927c-1db0-415d-883a-fbb069d3e0ad)

2. En la barra de filtros, ingresa `udp` y selecciona **Enter** para filtrar los paquetes UDP.![image](https://github.com/user-attachments/assets/9f71ec1e-193f-4259-9482-3d43541748a4)

3. Utiliza una aplicación que genere tráfico UDP, como una consulta DNS o un servicio de transmisión de video. Permite que el servicio funcione durante unos segundos.![image](https://github.com/user-attachments/assets/7c0213d1-f2de-4cdc-8747-9bba0471a725)

4. Detén la captura después de unos segundos.

### Analizando los datos
1. Examina los paquetes capturados e identifica los puertos de origen y destino.![image](https://github.com/user-attachments/assets/3c2cc022-d9da-4973-8607-f28732055e54)

2. Observa el encabezado UDP para los campos de **longitud** y **suma de verificación**.![image](https://github.com/user-attachments/assets/3070bed2-0acb-45c7-8585-a451aba64c69)


### Comparar paquetes TCP y UDP
1. Compara un paquete TCP con un paquete UDP capturado en tareas anteriores.
2. **Ver un ENCABEZADO TCP**![image](https://github.com/user-attachments/assets/35acee70-2a3e-4f5b-9e04-01f85b1b9340)

3. **Ver un ENCABEZADO UDP**![image](https://github.com/user-attachments/assets/3760ef00-b71f-47dd-ba03-b8853f8e04e3)

4. Observa las diferencias en los encabezados de los paquetes TCP y UDP.

### Identificar Protocolos Usando TCP
1. Filtrar las capturas de Wireshark para un puerto TCP específico, como **HTTP (puerto 80)** o **HTTPS (puerto 443)**.
2. Analizar los paquetes capturados para entender el comportamiento del protocolo.![image](https://github.com/user-attachments/assets/736429ce-5a4f-44c5-9614-734a534417e3)

3. **Ver la salida del tráfico TCP capturado en el puerto UDP 80:**

### Resumen del análisis
- Al analizar el tráfico HTTP en Wireshark, comienza observando el **apretón de manos TCP**.
- El cliente envía una solicitud HTTP y el servidor responde con un paquete HTTP que incluye código de estado y contenido.
- Observa cómo la comunicación estructurada y confiable de TCP permite este intercambio.

## Ejercicios

### Ejercicio 1: Capturar y Analizar Tráfico HTTPS (TCP)
1. Abre Wireshark usando **Ejecutar como Administrador** y comienza una nueva sesión de captura.
2. En la barra de filtros, ingresa `tcp port 443` para capturar tráfico HTTPS.
3. Abre un navegador web y visita cualquier sitio web seguro, como [https://www.google.com](https://www.google.com).
4. Detén la captura después de unos segundos.
5. Analiza los paquetes capturados para identificar el **apretón de manos de tres vías de TCP (SYN, SYN-ACK, ACK)**.
6. Observa el tráfico HTTPS cifrado.

### Ejercicio 2: Capturar y Analizar Tráfico DNS (UDP)
1. Abre Wireshark usando **Ejecutar como Administrador** y comienza una nueva sesión de captura.
2. En la barra de filtros, ingresa `udp port 53` para capturar tráfico UDP.
3. Para generar tráfico DNS, escribe el comando `nslookup` en el símbolo del sistema.
4. Detén la captura después de unos segundos.
5. Analiza los datos capturados.

### Ejercicio 3: Capturar y Analizar Tráfico ARP (Capa 2)
1. Abre Wireshark usando **Ejecutar como Administrador** y comienza una nueva sesión de captura.
2. En la barra de filtros, ingresa `ARP` para capturar tráfico ARP.
3. Para generar tráfico ARP, escribe el comando `arp -a` en el símbolo del sistema.
4. Detén la captura después de unos segundos.
5. Analiza la captura.

## Conclusión
Este laboratorio proporcionó una exploración práctica de los protocolos TCP y UDP utilizando Wireshark. Aprendiste a capturar y analizar tráfico de red, destacando las diferencias entre protocolos y la estructura de la comunicación en la red.

## Autor(es)
**Dr. Manish Kumar**

## Otros Contribuyentes
**Patsy Kravitz**
**Henrry - BugSlayer**

