# Tema 30

_Partes y funciones básicas de un ordenador. Sistema operativo Windows. Definición y funcionamiento básico, iconos y objetos, gestión de las unidades de almacenamiento, organización de los datos en unidades, partes y funcionamiento del escritorio, el explorador de Windows, la papelera de reciclaje, el panel de control, accesorios. Open Office._

## El ordenador

### Definición de ordenador

Un _ordenador_ o _computador_ es una máquina electrónica que funciona ejecutando conjuntos de instrucciones que definen su comportamiento (_programas_). 

> La palabra _ordenador_ (proviene del francés _ordinateur_) hace referencia a la capacidad de manipular grandes cantidades de datos mientras que _computador_ (proviene del inglés _computer_) alude a su capacidad de cálculo.

### Hardware, software

- _Hardware_ hace referencia a los elementos físicos del ordenador (procesador, memoria, disco duro, etc.).
- _Software_ se refiere tanto a los datos como a las instrucciones que los manejan (datos + programas).

> Al principio puede costar entender que el ordenador sea algo más que el hardware. Un símil muy ilustrativo podría ser un señalero que guía un avión. El hardware sería la persona (la parte física que no cambia) y el software lo formarían las diferentes disposiciones que adopta con los brazos para guiar al avión según un código que tanto el señalero como el piloto conocen. En el ordenador el software estaría formado por la disposición de las tensiones en las celdas de memoria y su interpretación o, en el caso de los discos duros, el magnetismo de las diferentes zonas del disco.

### Firmware y BIOS

Un tipo especial de software es el _firmware_, el software que controla directamente el hardware del dispositivo y que suele estar en memoria _no volátil_ (aquella cuya información no se pierde si se desconecta el dispositivo de la alimentación eléctrica). En el caso del ordenador al firmware se le denomina _BIOS_ (Basis Input Output System) o, en los ordenadores modernos, UEFI.

A la parte configurable del BIOS se le denomina _BIOS SETUP_. Permite configurar parámetros como la fecha y hora del sistema o desde qué unidad arrancar el sistema operativo.

### Digital frente a analógico.

Los ordenadores trabajan con solo dos estados. A las magnitudes que se interpretan como un conjunto finito de estados se les denomina _digitales_, en contraposición a aquellas que pueden tomar cualquier valor continuo entre dos dados y que se denominan _analógicas_. Los ordenadores usan solo dos estados (encendido-apagado, 1-0, on-off, etc.). El utilizar solo dos estados hace que las operaciones básicas que realiza el ordenador sean muy sencillas.

> Una ventaja de las señales digitales frente a las analógicas es su inmunidad al ruido electromagnético. Por ejemplo, antes era común que el ordenador se conectara al monitor mediante el interfaz VGA (cable con conectores de color azul con nueve pines). La señal que envía es analógica (una por cada color; rojo, verde y azul) y una pequeña fuente de ruido eléctrico como podría ser un altavoz mal apantallado basta para modificar ligeramente la señal y hacer que la imagen de monitor se distorsione. Sin embargo, los intefaces que se usan modernamente como HDMI o Displayport tratan la señal como digital, más inmune al ruido. Supongamos que la señal que se envía es de +5 V representando el estado "encendido" o "1", y 0 V representando el "apagado" o "0". Si la misma fuente de ruido anterior ahora se aplica al cable HDMI y la señal de +5 V se cambia a +4.8 V, el monitor seguirá entendiendo que es el estado "encendido" o "1" y no se verá la imagen afectada en absoluto. 

### Arquitectura Von Neumann

La mayoría de los ordenadores que conocemos siguen la _arquitectura Von Neumann_. Consiste en una máquina que hace cálculos (unidad de proceso o procesador) y una memoria donde se guardan a la vez tanto los datos como las instrucciones que manejan estos datos. El procesador lee los datos de la memoria secuencialmente (una celda de memoria tras otra, a menos que se encuentre una instrucción de salto a otra celda de memoria, donde continúa de nuevo secuencialmente).

> Las celdas de memoria guardan números. ¿Cómo sabe el ordenador si el número que lee es una instrucción o un dato? Para ello presupone que empieza a leer siempre en una posición de memoria donde hay una instrucción y es esa instrucción la que indica dónde están los datos. Por ejemplo, supongamos que el número 01 representa SUMAR. La sentencia `SUMAR 03 y 01 ` se codifica como `01 03 01` donde el número 01 aparece tanto al principio como al final. El ordenador presupone que el primer 01 es una instrucción, en este caso SUMAR, y los otros dos son los sumandos, por lo que el último 01 lo interpreta como dato y no como instrucción.

Según la arquitectura Von Neumann, un ordenador está formado por los siguientes elemento:

- _Unidad central de proceso_ (CPU de sus siglas en inglés). Al principio estaba formada por muchos componentes electrónicos hasta que se consiguió integrar en un único chip denominado _microprocesador_ o simplemente _procesador_. La CPU está formada por los siguientes elementos:
	- _Unidad Aritmético lógica_ (ALU por sus siglas en inglés). Se encarga de realizar operaciones muy sencillas tanto de tipo aritmético (sumas, multiplicaciones) como de tipo lógico (AND, OR, NOT, etc.).
	- _Unidad de Control_. Interpreta las instrucciones leídas de la memoria principal y gestio a todas las señales que se envían o reciben de los demás elementos (ALU, registros, memoria y sistema de entrada y salida).
	- _Registros_. Son pequeñas memorias de alta velocidad incluidas en el procesador. De entre ellas podemos destacar:
		- _Acumulador_ (AX). Es donde se almacena uno de los operandos de la ALU. También suele servir de salida, almacenando el resultado de la operación. 
		- _Registro de Estados_. Indica el resultado de las operaciones de la ALU (resultado cero, signo negativo, paridad, debordamiento, etc.). Cada bit, denominado _bandera_ o _flag_ representa un único estado, por lo que cada flag solo puede tomar dos valores (Por ejemplo, si el flag Signo está a 1 significa que el resultado de la operación a sido negativo y 0 en caso contrario).
		- _Puntero de Instrucciones_ (IP) o _Contador de Programa_ (PC). Almacena la posición de la memoria principal a la que tiene que acceder la CPU.
  - _Registro de Instrucciones_ (IR). Almacena la instrucción en curso leída de la memoria principal.
El Acumulador y el Registro de Estados están asociados a la ALU mientras que el Puntero de Instrucciones y el Registro de Instrucciones a la Unidad de Control.
- _Memoria principal_. Es la encargada de guardar los datos e instrucciones y es leída secuencialmente (celda tras celda) por la CPU. Se suele decir que es la memoria donde "se ejecutan los programas", a diferencia de la _memoria secundaria_ que se usa como almacén de datos.
- _Sistema de entrada y salida_. Transfiere datos desde y hacia dispositivos externos (llamados _periféricos_) que pueden ser de entrada hacia la CPU (ratón, teclado, escáner, webcam, micrófono, etc.), de salida (monitor, impresora, altavoz, etc.) o de entrada y salida (por ejemplo, la tarjeta de red o una pantalla táctil). Algunos periféricos combinan dispositivos tanto de entrada como de salida (auriculares con micrófono, una impresora multifunción que incluye escáner, etc.).
- _Buses del sistema_. Las señales eléctricas que maneja el procesador suelen dividirse en tres grandes grupos:
	- _Bus de direcciones_. Son líneas de salida de la CPU a la memoria principal Transportan la dirección de la celda de memoria donde la CPU tiene que acceder para leer o para escribir.
	- _Bus de datos_. Son líneas de entrada y salida que conectan la CPU con la memoria principal. Transportan la información de la celda de memoria a la que accede la CPU para leer o escribir. Puede ser un dato o una instrucción.
	- _Bus de control_. El resto de líneas (algunas de entrada, otras de salida) que se usan para coordinar el sistema. Por ejemplo, la línea de lectura-escritura (R/W) que indica a la memoria principal si la CPU quiere leer una celda de memoria o escribir en esa misma celda, o la _señal de reloj_ (CLK) que sirve para sincronizar el funcionamiento del sistema.

### Generaciones de ordenadores

La historia del ordenador suele organizarse en diferentes etapas o generaciones que supusieron un cambio importante respecto a la etapa anterior.

- **Primera**. Los ordenadores se construyen con _válvulas_ (también llamadas _tubos de vacío_). Estos componentes electrónicos están formados por una ampolla de vídrio con varios filamentos. Con respecto a los transistores de la generación posterior, son elementos voluminosos y frágiles, que consumen mucha energía (se calientan) y con una vida útil relativamente corta.
- **Segunda**. Los _transistores_, elementos de estado sólido realizados con semiconductores, sustituyen a las válvulas permitiendo circuitos mucho más pequeños y eficientes.
- **Tercera**. Con la invención del _circuito integrado_ o _chip_ se consigue reunir en un solo elemento miles de transistores.
- **Cuarta**. Se integran todos los chips que forman la CPU en un solo componente denominado _microproceador_.
- **Quinta**. Aparición del ordenador portátil y de la inteligencia artificial.

### Lenguages de programación

Se denomina _algoritmo_ al conjunto de pasos que permiten solucionar un problema. Para que el ordenador pueda ejecutar un algoritmo, éste debe estar codificado en algún _lenguaje de programación_ (hay muchos; BASIC, C, C#, Java, PHP, etc.) que luego será traducido al lenguaje máquina que entiende el ordenador.

Los lenguajes de programación se dividen en lenguajes de _bajo nivel_ o de _alto nivel_ en función de su cercanía a la máquina o al lenguaje natural. 

- _Lenguajes de bajo nivel_. Son los que representan el conjunto de instrucciones específicos del procesador, lo que hace que no sean portables y, por lo tanto, un programa diseñado para un procesador en concreto no se puede usar en otro ordenador con un procesador diferente.
    - _Lenguaje máquina_. Es el único lenguage que entiende el ordenador está formado por ceros y unos. 
    > El lenguaje máquina se representa con el sistema de numeración binario (base dos) o con un sistema de base múltiplo de dos como el hexadecimal (base 16 = 2x2x2x2). Por ejemplo, la instrucción que incrementa en una unidad el valor del registro AX del procesador es 00100000 en binario o 40 en hexadecimal (nótese que cuatro dígitos binarios se corresponden con uno solo en hexadecimal; más adelante se explica en el apartado correspondiente). 
    - _Ensamblador_. La representación de las instrucciones del ordenador mediante números (ya sea en binario o en hexadecimal) resulta difícil de recordar. Por ello se creó el _lenguaje ensamblador_ en el que cada instrucción se representa mediante abreviaturas en inglés llamadas _nemotécnicos_. 
    > A las instrucciones parecidas se les asigna nemotécnicos parecidos. Por ejemplo, en el caso particular del procesador Intel 8086, para incrementar en una unidad el valor del registro AX se utiliza el número en binario 00100000. Como nemotécnico se representa como INC AX. Incrementar el registro BX (en binario 001000111) se representa como INC BX.
- _Lenguajes de alto nivel_. Son lenguajes independientes de la arquitectura del ordenador (son _portables_, se pueden usar en máquinas con procesadores diferentes) y son más cercanos al lenguaje natural. Necesitan de un traductor que convierta las instrucciones del lenguaje de alto nivel al lenguaje máquina que es el que entiende el ordenador. Existen dos tipos de traductores. Los _compiladores_ traducen todo el programa de una vez dejándolo listo para su ejecución. Los _intérpretes_, sin embargo, traducen una instrucción y la ejecutan cada vez. Hasta que un compilador no ha terminado de generar el código máquina de todo el programa, éste no está listo para su ejecución pero, una vez generado, las instrucciones se ejecutan a gran velocidad. Los intérpretes no necesitan del tiempo de compilación pero su ejecución es más lenta al tener que traducir cada instrucción antes de ejecutarla.

### Binario

#### Bit y byte
Los ordenandores solo entienden de dos estados, 0 y 1. A la unidad mínima de información que puede valer 0 o 1 se le denomina _bit_ (binary digit). El procesador trabaja con grupos de bits o _palabras_, por ejemplo para representar caracteres. Un grupo de ocho bits se denomina _byte_ (1 byte = 8 bits).

> La unidad bit suele representarse con la letra _b_ en minúscula y byte con _B_ mayúscula. Así, cuando el proveedor de servicios de Internet dice que la conexión es de 100 Mbps se refiere a 100 millones de _bits_ por segundo. Cuando se dice que un archivo ocupa 10 MB se refiere a 10 millones de _bytes_.

#### Conversión binario-decimal
Para pasar un número en binario a decimal basta con sumar los "pesos" correspondientes a las posiciones que tienene un 1, teniendo en cuenta que son las potencias de dos (1, 2, 4, 8, ...) empezando por la derecha, por el dígito menos significativo. Por ejemplo, el número en binario 1011 sería en decimal: 8 + 0 + 2 + 1 = 11.

Para pasar un número de decimal a binario hay que hacer la operación opuesta; calcular las potencias de dos que sumadas dan ese número. Así, 11 en decimal se puede obtener con la potencia 8, 2 y 1 porque 11 = 8 + 2 + 1 (para la conversión a binario conviene comenzar siempre por la potencia más alta posible, en este caso 8. Luego se resta 11-8=3 y se vuelve a calcular para 3).

#### Prefijos de unidades

Cuando la cantidad de bits o de bytes es alta se suelen usar los siguientes prefijos:

- k (kilo) = 2 elevado a 10 = 1024 (casi mil)
- M (mega) = 2 elevado a 20 = k x k = 1024 x 1024 (casi un millón)
- G (giga) = 2 elevado a 30 = k x M = k x k x k =1024 x 1024 x 1024 (casi mil millones)
- T (tera) = 2 elevado a 40 = M x M = k x k x k x k (casi un billón)

> Esos prefijos o multipcadores se pueden aplicar tanto a bits como a bytes.

### Partes del ordenador

En la práctica un ordenador suele estar formado por una placa de circuito impreso, llamada _motherboard_ donde se sitúan el procesador, la memoria y el sistema de entrada y salida que consiste en multitud de circuitos que controlan diferentes periféricos como el ratón y teclado, los puertos usb, el monitor, la red, etc. Esta placa junto con la fuente de alimentación y otros botones y conectores se agrupan en una caja.

> Informalmente suelen referirse a la caja como "la CPU" (sinécdoque en el que se nombra al todo con una parte).

#### Placa base o placa madre

La mayor parte de los componentes de un ordenador se integran en una placa de circuito impreso que se denomina _placa base_, _placa madre_ o _motherboard_. El  _factor de forma_  identifica el tamaño y la disposición de los elementos y conexiones en la placa base, siendo el más común el ATX.

> Otros formato derivados del ATX es el micro-ATX o, más pequeño aún, el mini-ATX.

La placa base contiene el zócalo o _socket_ para insertar el _microprocesador_.

> Un _socket_ o _zócalo electrónico_ es un soporte que sirve también de conexionado eléctrico.


Junto con el microprocesador, en la placa base se montan otros circuitos electrónicos que gestionan la memoria principal y muchos otros periféricos.

Al conjunto de circuitos integrados (_chipset_) que están más cerca del procesador y gestionan el bus de alta velocidad al que se conectan la memoria principal y la _tarjeta gráfica_ (esta última mediante la conexión _PCIe_, pci express), se denomina _puente norte_. Estos circuitos pueden estar integrados en un único chip o incluso incluidos en el procesador. A los circuitos que gestionan el bus donde se conectan los demás periféricos (discos duros, sonido, puertos usb, red, etc.) se le denomina _puente sur_.

La conexión de la memoria al puente norte se realiza mediante conectores llamados _slots de memoria_. El resto de conectores a los buses se denominan _ranuras o slots de expansión_ y permiten conectar diferentes tarjetas, tanto al puente norte (tarjeta gráfica) como al puente sur (interfaz de audio, de red, etc.). Actualmente los slots de expansión más usados son de tipo PCIe (_PCI-Express).

> PCIe es un estándar que se refiere no solo al conector sino al tipo de bus que transporta la información.

#### Procesador

Los procesadores actuales contienen varios _núcleos_ que se comportan como varias CPU separadas que permiten trabajar en paralelo.

#### Memoria

Las memorias se pueden clasificar de diferentes formas. Una de ellas es atendiendo a su función:

- _Memoria principal_. Es la memoria que lee el procesador para ejecutar las instrucciones del programa. Para su implementación se usan módulos RAM.
- _Memoria secundaria_. Es la que sirve de almacenamiento. Ejemplos de memoria secundaria son los discos duros o las unidades flash.

Atendiendo a su volatilidad:

- _RAM_ (Random Access Memory). Son memorias de lectura/escritura rápidas cuyo contenido se pierde cuando se retira la alimentación eléctrica (son volátiles).
- _ROM_ (Read Only Memory). Son memorias que mantienen su contenido aunque se le retire la alimentación eléctrica. Atendiendo a su capacidad de borrado se dividen en:
    - _PROM_ (Programable ROM). Se escriben una sola vez.
    - _EPROM_ (Erasable PROM). Permite borrarlas retirando una pegatina y exponiéndola a rayos ultravioletas.
    - _EEPROM_ (Electrically Erasable PROM). Se puede borrar eléctricamente. Las _memorias flash_ que conocemos actualmente son una evolución de las eeprom.


La _memoria caché_, en el contexto de la memoria principal, es una memoria temporal, de menor capacidad pero más rápida, donde se guardan los datos leídos de la memoria principal que pueden ser requeridos de nuevo. De esa forma, esos datos se leen de la caché aumentando el rendimiento. Las memoria caché se clasifican en niveles según su proximidad al procesador, desde la L1 (la más cercana y rápida) a la L3.

> En los procesadores modernos las cachés L1, L2 y L3 se encuentran integradas en el chip del procesador. Además, cada núcleo del procesador tiene su propia caché L1 y L2.


#### Disco duro

El disco duro o HDD  (Hard Disk Device) es un dispositivo de almacenamiento secundario formado por uno o varios discos (llamados _platos_) que giran a gran velocidad sobre el mismo eje. Sobre estos discos se sitúan unos cabezales que se encargan escribir o leer sobre la superficie magnetizada.

Los discos duros _ATA_ (también llamados _IDE_) se conectaban mediante un bus en paralelo (transmitían 16 bits a la misma vez). En la actualidad han sido reemplazados por los SATA (Serial ATA). Los discos SATA permiten mayores velocidades de transmisión y cables más largos y finos que los PATA (retrónimo que significa Parallel ATA). También permiten la conexión/desconexión en caliente (no hace falta retirar la alimentación eléctrica).

> En el entorno empresarial (servidores y estaciones de trabajo) los discos duros SCSI, de comunicación paralela, también se sustituyeron por los SAS, de comunicación serie.

|            |   Antes   | Ahora |
|------------|:---------:|:-----:|
| Doméstico  | ATA o IDE |  SATA |
| Servidores |    SCSI   |  SAS  |

Los discos duros están formados por uno o más platos con caras divididas en anillos concéntricos (_pistas_) llamadas _cilindros_ (un cilindro incluye la misma pista de todos los platos). Las pistas se dividen en _sectores_.

Cuando se da formato al disco, se establece el tamaño del _cluster_ o _unidad de asignación_, el número mínimo de sectores que el sistema operativo trata como una unidad.

> En la mayoría de los discos un sector ocupa 512 bytes (medio kB). Si al formatear una partición de un disco se establece un clúster como 4 sectores, el sistema operativo escribirá o leerá en grupos de 2 kB (4 sectores x 0.5 kB/sector). Así, si un archivo ocupa 2.5 kB, se grabará como 2 clústeres o 4 kB (un clúster se queda demasiado corto con solo 2 kB) y los 1.5 kB restantes no se usan y cuentan como espacio que ocupa en disco. De ahí que al ver las propiedades de un archivo en Windows, éste nos presenta dos valores: _Tamaño_ y _Tamaño en disco_.

#### SSD

En los últimos años los discos duros están empezando a ser sustituidos por unidades _SSD_ (Solid State Device) que al estar hechas con tecnología flash son más rápidas, consumen menos, son más ligeras y más inmunes a los golpes y vibraciones al no tener partes móviles.

#### Partición

Para que el sistema operativo reconozca una unidad de disco duro o de SSD lo primero que hay que hacer es particionarlo. Al particionar se crean unidades lógicas que para el sistema operativo son independientes. También se graba la tabla de particiones al principio del disco.

> Aunque solo se quiera una única unidad lógica que ocupe todo el espacio del disco, éste hay que particionarlo.

Hasta hace unos años las unidades se particionaban escribiendo en el primer sector del disco lo que se denomina _Master Boot Record_ (MBR). El MBR contiene la tabla con las particiones del disco y un pequeño programita que indica al ordenador en qué partición está el sistema operativo (_partición activa_). El sistema MBR está limitado a cuatro particiones primarias con un tamaño máximo de 2 TB. En la actualidad está generalizada la partición mediante el sistema GPT que permite hasta 128 particiones de más de 2 TB.

|              | Antes | Ahora |
|--------------|:-----:|:-----:|
| Firmware     |  BIOS |  UEFI |
| Particionado |  MBR  |  GPT  |


#### Formato
Tras particionar la unidad física (disco duro, SSD, etc.), hay que formatear las unidades lógicas creadas. Al formatear se crea el _sistema de archivo_ que permitirá al sistema operativo almacenar y leer los archivos. Cada sistema de archivos ofrece diferentes características. Los más usados en Windows son FAT32, NTFS y el más moderno exFAT. En Linux y MacOS se suelen usar otros.

Una diferencia fundamental entre el sistema de archivos NTFS y FAT es que NTFS proporciona seguridad permitiendo establecer permisos de acceso.

> Si en las propiedades de un archivo o carpeta (se accede pulsando con el botón derecho del ratón en el icono correspondiente y eligiendo _Propiedades_) aparece la pestaña _Seguridad_, el sistema de archivos es NTFS. En esa pestaña se pueden asignar permisos de acceso al archivo o carpeta a grupos o a usuarios específicos.


## El sistema operativo Windows

### Definición de sistema operativo

Un sistema operativo está formado por el software que permite al usuario y a otros programas acceder a los recursos del ordenador.

> Muchos usuarios suelen asociar el sistema operativo Windows solo con la _interfaz gráfica_, constituida principalmente por el escritorio de Windows. En realidad el sistema operativo consta de mucho más como, por ejemplo, los controladores de dispositivos que hace que los periféricos puedan funcionar o las funciones que necesitan los programadores para que sus programas funcionen.

### Versiones de Windows

Una clasificación de los sistemas Windows se basa en el propósito (escritorio, servidor, sistemas embebidos).

Las versiones de escritorio están destinadas a ofrecer a los usuarios un _interfaz gráfico de usuario_ o _GUI_ (básicamente el _escritorio_ de Windows) con accesos sencillos a aplicaciones de escritorio (navegador web, editor de textos, editor gráfico, reproductor multimedia, etc.). Las versiones de servidor no tienen por qué incluir un escritorio y están destinadas a ejecutar servicios de red.

> Microsoft creó _Windows CE_ destinado a dispositivos móviles (teléfonos y tablets), pantallas multimedias y consolas. Posteriormente creó versiones simplificadas de sistemas Windows de escritorio (_Windows XP Embedded_, _Windows 7 Embedded_) para ser usadas en sistemas embebidos como máquinas recreativas, cajas registradoras o cajeros automáticos.

#### Versiones de escritorio

Microsoft lanzó Windows 1.0 en 1985 pero la primera versión que tuvo éxito fue Windows 3.0 cinco años más tarde (y sus actualizaciones Windows 3.1 y _Windows 3.11 Trabajo en Grupo_). A partir de ahí se dividen las versiones en dos líneas: la doméstica basada en MS-DOS (_Windows 95/98/Me) y la profesional basada en NT (Windows NT/2000/XP/Vista/7/8/10).

Los sistemas operativos basados en NT soportan el sistema de archivos NTFS con seguridad a nivel de archivo.


- 1985 - Windows 1.0
- 1987 - Windows 2.0
- 1990 - Windows 3.0
- 1992 - Windows 3.1
- 1993 - Windows NT (NT 3.1)
- 1993 - Windows 3.11 _Trabajo en Grupo_
- 1995 - Windows 95 (4.0)
- 1995 - Windows 95 OSR (admite FAT32)
- 1996 - Windows NT (NT 4.0)
- 1998 - Windows 98 
- 1999 - Windows 98 SE (_Second Edition_)
- 2000 - Windows 2000 (NT 5.0)
- 2000 - Windows Me (_Millenium Edition_, basado en 98 SE)
- 2001 - Windows XP (basado en NT)
- 2007 - Windows Vista (NT 6.0)
- 2009 - Windows 7 (NT 6.1)
- 2012 - Windows 8 (NT 6.2)
- 2013 - Windows 8..1 (NT 6.3)
- 2015 - Windows 10 (NT 10)

#### Versiones de servidor

Las versiones de servidor están optimizadas para ofrecer servicios en red por lo que se puede instalar sin interfaz gráfico (administración a través de líneas de comandos) y carece de opciones que puede interesar a un usuario de escritorio como la reproducción multimedia o Cortana, por ejemplo. 

- Server 2003 (NT 5.2)
- Server 2008 (NT 6.0)
- Server 2012 (NT 6.2)
- Server 2019 (NT 10)

#### Apagar, reiniciar, suspender e hibernar.

- _Apagar_. Cierra todos los programas. Tras apagar no se necesita la alimentación eléctrica salvo para cargar la batería.
- _Reiniciar_. Apaga y enciende de nuevo el ordenador.
- _Suspender_. Establece el equipo en un estado de poco consumo eléctrico apagando temporalmente elementos como la pantalla o el disco duro. Tras suspender hace falta que se mantenga la alimentación eléctrica aunque el consumo es pequeño.
- _Hibernar_. Graba en el disco una copia del estado actual de la memoria y luego se apaga, por lo que en el siguiente encendido recupera el estado en el que se encontraba el ordenador justo antes de hibernar. No necesita alimentación eléctrica.

|   Acción  | Cierra programas | Necesita electricidad |
|:---------:|:----------------:|:---------------------:|
|   Apagar  |        Sí        |           No          |
| Reiniciar |        Sí        |           Sí          |
| Suspender |        No        |           Sí          |
|  Hibernar |        No        |           No          |


### El Escritorio

El _interfaz gráfico de usuario_ (GUI) de Windows se concreta fundamentalmente en el escritorio. Cuando un usuario inicia sesión en Windows aparece un área con varios elementos denominada escritorio. Consta de las siguientes partes:

- El _Área de trabajo_. Es donde se efectúa el trabajo del usuario. En él podemos encontrar:
    - _Iconos_. Son pequeñas imágenes que representan archivos, carpetas o _accesos directos_ (enlaces a archivos o carpetas). Los archivos pueden ser programas o documentos que necesitan ser abiertos con el programa correspondiente.
    - _Ventanas_. Son el área que muestra la ejecución de las aplicaciones. Suelen tener los siguientes elementos:
        - _Botón de control_. Está situado en la esquina superior izquierda. Contiene las acciones comunes que se pueden ejecutar sobre la ventana (mover, maximizar, restaurar, minimizar, cambiar el tamaño y cerrar).
        - _Barra de título_. Con el nombre del documento y del programa.
        - _Barra de menú_. Contiene las acciones que el programa ofrece, en forma de menú desplegable.
        - _Barras de herramientas_. Incluye pequeños botones con iconos como alternativa más visual al menú desplegable.
        - _Botones de minimizar/maximizar/cerrar_. En la esquina superior derecha.
        - _Barra de estado_. Se sitúa en la parte inferior de la ventana. Muestra información relativa al contexto. Por ejemplo, en el caso de un documento de texto abierto con el bloc de notas, el número de línea y columna por donde se sitúa el cursor o el zoom aplicado.
- La _Barra de tareas_. Barra horizontal que por defecto viene situada en la parte inferior del escritorio. Contiene los siguientes elementos:
    - El _botón de inicio_. Tradicionalmente es el punto de acceso a todos los programas, a la configuración de Windows, a los archivos recientes o al apagado del ordenador, entre otros.
    - El _área de la barra de tareas_. Está destinada a contener botones que representan los programas abiertos. Aunque técnicamente la barra de tareas incluye el botón de inicio y el área de notificación, en muchos contextos se le denomina barra de tareas solo al área entre éstos.
    - El _área de notificación_. Está situada en la parte derecha de la barra de tareas y consta de:
        - La _bandeja de sistema_ (tray icons). Muestra notificaciones de Windows y programas. En ella se sitúan pequeños iconos con características que pueden no estar presentes en el escritorio.
        - El reloj-calendario.

> Generalmente no se muestran todos los iconos de la bandeja de sistema a menos que se pulse en una pequeña flecha junto a ellos. Se puede configurar Windows para que los muestre todos o solo los que nos interese. Uno de los iconos más usados es el de _quitar hardware de forma segura_ que permite extraer un medio extraíble teniendo la seguridad de no quedan más datos por grabar en él (_expulsar de forma segura_).

Existen iconos por defecto que pueden mostrarse en el escritorio:

- Equipo (anteriormente _PC_)
- Papelera de reciclaje
- Archivos del usuario (anteriormente _Mis documentos_)
- Panel de control
- Red (anteriormente _Mis sitios de red_)

Haciendo doble clic sobre un icono se ejecuta el programa o se abre el documento al que hace referencia. Si se pulsa con el botón derecho aparece un menú contextual que permite realizar diferentes acciones como copiar, pegar, cambiar de nombre o ver las propiedades.

### El explorador de Windows

El _explorador de Windows_ es el programa que gestiona los archivos y carpetas en Windows. El explorador muestra la información de la memoria secundaria en tres niveles: unidades (C:, D:, etc.), carpetas y archivos.

> El explorador de archivos se encuentra en la carpeta Windows y se llama `explorer.exe` (no confundir con `iexplore.exe` que se corresponde con el navegador _Internet Explorer_). Siempre hay un explorer.exe ejecutándose (en caso contrario no se verían los iconos del escritorio). Posteriores llamadas a explorer.exe abren una ventana. Se puede abrir el explorador de archivos mediante la combinación de teclas **Windows+E**.

> A partir de Windows 7 se ocultó por defecto la barra de menús del explorador de archivos (al igual que la del navegador Internet Explorer). Para mostrarla basta con pulsar la tecla `Alt`. Si se quiere siempre visible se puede configurar en _Opciones de carpeta_.

Cuando se arrastra con el ratón un archivo o carpeta a otra carpeta dentro de la misma unidad, el archivo o carpeta se mueve (desaparece de la ubicación de origen y aparece en la nueva) pero si se arrastra entre ubicaciones de unidades diferentes, el archivo o carpeta se copia en lugar de moverse (no deseparece de la ubicación de origen sino que se duplica en la nueva).

Este comportamiento de copiar o mover se puede "forzar" si se pulsa una de estas teclas cuando se arrastra el icono:

- **Ctrl + arrastrar**, siempre se copia.
- **May + arrastrar**, siempre se mueve.
- **Alt + arrastrar**, crea un acceso directo.

#### Portapapeles

Una de las acciones más básicas que permite el explorador de archivos es el uso del _portapapeles_ de Windows. Cuando se pulsa con el botón derecho del ratón sobre un icono, aparece un menú contextual con las opciones copiar, cortar o pegar. También existen los métodos abreviados:

- **Ctrl + C**, copiar los iconos seleccionados al portapapeles.
- **Ctrl + X**, cortar los iconos seleccionados al portapapeles.
- **Ctrl + V**, pegar desde el portapapeles a la ventana activa.

En Windows 10 el portapapeles contiene un historial de los elementos copiados. Se puede acceder a él mediante la combinación de tecla **Windows + V** . La primera vez que se pulsen estas teclas se activará el historial del portapapeles; a partir de ahí, cada vez que se pulsen aparecerá el listado con los elementos previamente copiados.

> Otra función que puede activarse en Windows 10 es el _portapapeles compartido_, que permite enviar lo copiado a los servidores de Microsoft para que esté disponible cuando inicie sesión con una cuenta de Microsoft en otro dispositivo.

#### Métodos abreviados del explorador de Windows

Algunas combinaciones de teclas son:

- **Ctrl + N**, abre una nueva ventana del explorador.
- **Ctrl + W**, cerrar.
- **Ctrl + May + N**, crar carpeta.
- **Inicio**, ir al principio.
- **Fin**, ir al final.
- **F11**, maximizar/minimizar.
- **Ctrl + E**, seleccionar todos los elementos.
- **Ctrl + F**, buscar.


### La papelera de reciclaje

La _papelera de reciclaje_ es una función introducida por Microsoft en sus sistemas operativos. Evita que se borren de forma definitiva archivos y carpetas accidentalmente permitiéndolos recuperar después de que se hayan borrado. Para ello, cuando se borra un archivo, no se borra definifivamente sino que se mueve a una zona intermedia (la papelera) en la que deja de estar visible para el usuario.

Cuando un archivo se elimina de la papelera, Windows avisa de que se va a borrar de forma permanente. En realidad lo que ocurre es que el espacio que ocupa el archivo se marca como libre para poder ser usado por otros archivos. Mientras no haya sido sobrescrito, existe la posibilidad de recuperarlo mediante aplicaciones de terceros.

#### Capacidad de la papelera de reciclaje

Antes de Windows Vista la papelera tenía capacidad para almacenar hasta un 10% del espacio de la unidad, sobrescribiendo los más antiguos cuando se llena.

#### Directorio de almacenamiento de la papelera

La ubicación de la carpeta de la papelera de reciclaje depende del sistema de archivos y el sistema operativo. En el caso de la unidad C (existe un directorio para cada unidad), la papelera se encuentra en:

- C:\RECYCLED - Sistemas FAT (Windows 3/95/98/Me)
- C:\RECYCLER - Sistemas NTFS (Windows NT/2000/XP)
- C:\$Recycle.Bin- A partir de Windows Vista/7

> En un sistema NTFS existe una subcarpeta por cada usuario en la carpeta de la papelera de reciclaje (C:\RECYCLER o C:Recycle.Bin). El sistema operativo evita que usuarios no administradores puedan acceder a los archivos personales de otros usuarios y esto incluye a la papelera de cada usuario.
> 
> La carpeta de la papelera de reciclaje tiene los atributos oculto y de sistema.

Cuando se eliminan archivos desde un medio extraíble como una unidad flash usb o mediante la red, el borrado es permanente y no pasa por la papelera de reciclaje.

### El panel de control

El _panel de control_ ha sido tradicionalmente la aplicación que permite configurar Windows de manera visual.

En la actualidad la mayoría de las funciones del panel de control, aunque no todas, están también disponibles en _Configuración_, que presenta una interfaz más moderna acorde con Windows 10.

El panel de control está disponible desde el botón Inicio (en Windows 10 se puede encontrar tecleándolo en la barra de búsqueda). Cuando se abre muestra los ajustes de configuración ordenados por categorías, aunque también se pueden mostrar todos los iconos mediante el desplegable "Ver por:".

> El panel de control es el programa `control.exe` que se encuentra en la carpeta `Windows\System32`. Se puede abrir tecleando `control` (no hace falta escribir la extensión ".exe") en una consola de comandos.

Las diferentes categorías en Windows 7 son:

- _Sistema y seguridad_ (cortafuegos, Windows Update, Sistema, Opciones de energía, Restauración del equipo)
- _Redes e Internet_ (conexiones de red y opciones que usan Internet Explorer y otros navegadores)
- _Hardware y Sonido_ (impresoras y otros dispositivos, sonido, opciones de energía, pantalla)
- _Programas_ (_Programas y característas_ para mostrar/desinstalar los programas, configuración de los programas predeterminados)
- _Usuarios y protección infantil_ (cuentas de usuario y control parental, correo)
- _Apariencia y personalización_ (configuración de la pantalla/barra de tareas, opciones de carpeta)
- _Reloj, Idioma y Región_ (configuración de la fecha y hora, configuración regional y de idioma)
- _Accesibilidad_ (centro de accesibilidad y reconocimiento de voz)

> En Windows 10 se tienen las mismas categorías con la excepción de _Usuarios y protección infantil_ que se llama ahora _Cuentas de usuario_ ya que se ha retirado la configuración de protección infantil al menú `Configuración > Familia y otros usuarios > Tu familia`, obligando a crear una cuenta de Microsoft para el menor.

### Accesorios

Se llaman _accesorios_ de Windows a las utilidades preinstaladas en Windows.

### Aplicaciones preinstaladas en Windows 10

Las aplicaciones preinstaladas son muy numerosas. Muchas de ellas son mejoras de las que se tenía en versiones anteriores de Windows (calculadora, bloc de notas, etc.). Un listado no exhaustivo es el siguiente:

- _Cortana_. Asistente de productividad de Microsoft. Permite, entre otros, abrir aplicaciones, realizar búsquedas, gestionar el calendario y las alarmas.
- _Microsoft Edge_. Navegador moderno basado en el proyecto de software libre Chromium.
- _Bloc de notas_. El clásico _notepad_, editor de textos sin formato.
- _Wordpad_. Procesador de textos con formato.
- _Paint_. Editor de imágenes de _mapa de bits_ (_bitmap_) y _Paint 3D_ que permite insertar elementos tridimensionales.
- _Herramienta Recortes_
- _Lupa_. Permite ver con mayor tamaño una zona del escritorio.
- _Reconocimiento de voz_. Tanto para ejecutar órdenes como para redactar texto.
- _Narrador_. Lee todo lo que ha en la ventana activa; no solo el texto sino también los elementos que conforman la ventana como los botones.
- _Teclado en pantalla_. Es un teclado virtual, útil en dispositivos móviles como tablets.
- _Panel de entradas matemáticas_. Permite escribir expresionees matemáticas a mano.
- _Notas rápidas_. Simulan post-it. Pueden ser de diferentes colores.
- _Mapa de caracteres_. Útil para insertar símbolos especiales. Relacionado con éste se encuentra el _editor de caracteres privados_ que permite crear caracteres propios.
- _Windows Journal_. Editor y organizador de notas manuscritas.
- _Microsoft Print to PDF_. Impresora virtual que permite crear un documento PDF de todo aquello que se pueda imprimir.
- _Skype_ ...

## Apache OpenOffice

Suite ofimática de _software libre_ que emula el estilo de las versiones de MS Office basadas en menús (anteriores a 2007).

### Historia de Apache OpenOffice

Apache OpenOffice desciende del proyecto OpenOffice.org basado en StarOffice (suite de pago). Este proyecto fue liderado por Sun Microsystems desde el año 2000 hasta la compra de Sun por parte de Oracle en 2009. En 2010 un grupo de desarrolladores desencantados con Oracle forman su propio proyecto denominado LibreOffice. En 2011 Oracle cede OpenOffice a la fundación Apache de la que toma su nombre actual.

> En LibreOffice se volvió a programar desde cero partes importantes del código para hacerlo más limpio y eficiente y eliminar la dependencia con Java. El éxito de LibreOffice frente a OpenOffice se debe a su inclusión por defecto en las distribuciones de Linux y a una licencia más permisiva que permite que LibreOffice pueda incluir las mejoras de OpenOffice pero no al contrario.

La suite OpenOffice está formada por las siguientes aplicaciones:

- _Writer_. Procesador de textos.
- _Calc_. Hojas de cálculo.
- _Impress_. Presentaciones.
- _Base_. Bases de datos.
- _Draw_. Editor de gráficos vectoriales.
- _Math_. Editor de fórmulas matemáticas.
