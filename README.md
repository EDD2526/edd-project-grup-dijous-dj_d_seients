View this project on [CADLAB.io](https://cadlab.io/project/30198). 

# Projecte Grup D (Dijous-tarda): Seients

>**Autors:Joan Martínez, Manel Frías i Joan Heras 
>**Versió: V3.0

----------

## Objectiu

En primer lloc cal explicar que estem davant de l'elaboració d’un mòdul crític per a la seguretat i el funcionament del vehicle. El sistema de SEIENTS DIGITALS és la interfície entre l'energia del cotxe i la seguretat del conductor.
Per tant ens basarem en aquests puts adjuntats al guió:

  a) 3 motors (posició, alçada, reclinació) amb els seus finals de carrera.
  b) Calefacció del seient. 
  c) Sensor digital de cinturons.
  d) Memòria externa no volàtil per guardar posicions pre-programades.

>PCB per ...

L'objectiu principal és dissenyar i fabricar una PCB funcional per a la gestió del subsistema de seients elèctrics d'un vehicle, complint els següents punts:

- Controlar 3 motors del seient:
- Posició longitudinal, alçada, Inclinació del respatller
- Detectar finals de carrera per evitar sobrecàrregues mecàniques.
- Implementar calefacció del seient amb control electrònic.
- Detectar estat del cinturó de seguretat.
- Guardar i recuperar posicions programades del seient mitjançant memòria no volàtil.
- Permetre la interacció de l’usuari amb botonera.
- Comunicar-se amb la xarxa del vehicle via bus CAN.
- Permetre monitorització i debug via USART.

## Diagrama de blocs


### Descripció/funcionalitat de cada bloc

  - ALIMENTACIÓ: El sistema s’alimenta a partir de la bateria del vehicle (12V). Aquesta tensió es condiciona mitjançant dues etapes. Això permet alimentar:

    * Microcontrolador.
    * Sensors.
    * Comunicacions.
 
  - UART: per debug i monitorització.

  - MICROCONTROLADOR: És el nucli del sistema, encarregat de: Processar les entrades (botons i sensors), controlar els motors, gestionar la comunicació amb altres mòduls. També gestiona diferents interfícies:

    * GPIO → botonera i sensors.
    * PWM → control de motors i calefacció.
    * I2C → memòria i sensor de temperatura.
    * CAN → comunicació amb el vehicle.
    * UART → debug.

  - BOTONERA: Permet a l’usuari controlar el seient:

    * Posició.
    * Alçada.
    * Reclinació.
    
  - SENSORS: de temperatura i cinturons.

  - SISTEMA DE MOTORS.

  - SISTEMA DE CALEFACCIÓ.

  - MEMÒRIA.

  - COMUNICACIÓNS.

-----------

## Requisits / Especificacions

  * Alimentació; 12V, regulada 5V
  * Microcontrolador PIC18xxxxxxxxx
  * ...

-----------

## Components

| Descripci&#243; | Ref | Package |Datasheet | Prove&#239;dor | Value | Preu | Unitats |
| Condensadors | C | SMD | [Datasheet](https:https://www.mouser.es/datasheet/3/282/1/70293G.pdf) | Mouser | 0,34&euro; | 14X |
| --- | --- | --- | --- | ---| --- | --- |
| --- | --- | --- | --- | ---| --- | --- |
| --- | --- | --- | --- | ---| --- | --- |

| Exemple | XYZ1234 | SOT-23 | [Enllaç](https://...) | DigiKey | 2 |

 C1, C4, C8, C13, C20, C23, C24, C25, C27, C28, C70, C71, C72, C73, | SMD | |[Datasheet(https:https://www.mouser.es/datasheet/3/282/1/70293G.pdf | [Mouser] | 0,34&euro; | | 14x |
| Microcontrolador | PIC18F26Q83-I/SS | SOIC-28 |[Datasheet](https://www.mouser.es/datasheet/2/268/PIC18F27_47_57Q83_Preliminary_Data_Sheet_40002265B-2887591.pdf) | [Mouser](https://www.mouser.es/c/?q=PIC18F27Q83-I%2FSO)| 2,17&euro;| 1x |
| XTAL-Ressonador | CSTCR7M99G53-R0 | SMD |[Datasheet](https://www.mouser.es/datasheet/2/281/p16e-522700.pdf) | [Mouser](https://www.mouser.es/ProductDetail/Murata-Electronics/CSTCR7M99G53-R0?qs=Zd9RUO93%2Fo7cnwzsujIkpA%3D%3D)  | 0,27&euro; | 1x |

-----------

## Software

### Eines:

  * KiCad 9.0 o superior
  * 

### Configuraci&#243; :

  * 

### Funcionalitats:

  - Controlar 3 motors del seient:
  - Posició longitudinal, alçada, Inclinació del respatller
  - Detectar finals de carrera per evitar sobrecàrregues mecàniques.
  - Implementar calefacció del seient amb control electrònic.
  - Detectar estat del cinturó de seguretat.
  - Guardar i recuperar posicions programades del seient mitjançant memòria no volàtil.
  - Permetre la interacció de l’usuari amb botonera.
  - Comunicar-se amb la xarxa del vehicle via bus CAN.
  - Permetre monitorització i debug via USART

-----------


## Historial de canvis:

23/03/2026 a les 14:07
Al dia d'avui s'ha modificat el diagrama de blocs: hem ajustat petites coses per finalitzar el diagrama de blocs definitiu.

23/03/2026 a les 17:22
Tan bon punt hem modificat el digrama de blocs, al dia d'avui també s'ha modificat la part sensors: hem incorporat l'esquemàtic preliminar una vegada ajustat el diagrama de blocs. Incorporats el TMP102 (sensor de temperatura) i el Hall A3144 (sensor digital dels cinturons).

24/03/2026 a les 14:07
Al dia d'avui s'ha modificat la part d'alimentació: hem incorporat dues coses importants: FUSIBLE i DIODES TVS. Hem modificat els possibles errors mitjançant una escombrada de l'ERC. Alimentació (ACABAT AL 100%).

24/03/2026 a les 18:48
S'ha modificat la part de SENSORS: una vegada incorporats el TMP102 (sensor de temperatura) i el Hall A3144 (sensor digital dels cinturons) hem realitzat la incorporación dels components: resistències pull-up, capacitats de desacoblament, ...

25/03/2026 a les 09:35
Al dia d'avui s'ha modificat la part de sensors: hem incorporat etiquetes i hem modificat algunes connexions degut a problemes amb l'ERC, SENSORS (ACABAT AL 100%).

25/03/2026 a les 1O:07
S'ha modificat la part de SENSORS: hem finalitzat tot l'esquemàtic d'aquesta part i donem per acabada la part de SENSORS.

25/03/2026 a les 09:35
Efectuada la simulació per demostrar el funcionamenten del LM1117-3.3 (part d'ALIMENTACIÓ) a LTSpice.


| Data | Autor     | Branch | Versi&#243; | Descripci&#243; |
| --- | --- | --- | --- | --- |
|  28/03/2023 | mlopez | Master | initial commit | Primera versi&#243; d'esquem&#224;tic i selecci&#243; de components |
E s t a   e s   u n a   l   n e a   d e   p r u e b a   p a r a   e l   r e p o s i t o r i o 
 
 