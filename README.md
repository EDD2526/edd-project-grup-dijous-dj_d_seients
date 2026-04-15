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

| Descripci&#243; | Ref | Package |Datasheet | Prove&#239;dor | Preu | Unitats |
| --- | --- | --- | --- | ---| --- | --- |

Reference,"Qty","Value","DNP","Exclude from BOM","Exclude from Board","Footprint","Datasheet"
C1,C4,C8,C13,C20,C23,C24,C25,C27,C28,C70,C71,C72,C73,"14","100 nF","","","","Capacitor_SMD:C_0805_2012Metric","~"
C2,C3,"2","220 uF","","","","Capacitor_SMD:C_0805_2012Metric","~"
C5,C6,"2","10uF","","","","Capacitor_SMD:C_0805_2012Metric","~"
C9,C31,C34,"3","0.1uF","","","","Capacitor_SMD:C_0805_2012Metric","~"
C10,C12,C26,C32,"4","100nF","","","","Capacitor_SMD:C_0805_2012Metric","~"
C11,C14,"2","22 pF","","","","Capacitor_SMD:C_0805_2012Metric","~"
C15,C16,"2","100 nF","","","","Capacitor_THT:C_Disc_D5.0mm_W2.5mm_P5.00mm","~"
C17,"1","100 nF","","","","Capacitor_THT:C_Disc_D3.0mm_W1.6mm_P2.50mm","~"
C30,C33,"2","10uF","","","","Capacitor_THT:CP_Radial_D5.0mm_P2.50mm","~"
D1,"1","D_TVS","","","","Diode_SMD:D_SMA","~"
D2,"1","1N5822","","","","Diode_THT:D_DO-201AD_P15.24mm_Horizontal","~"
D3,"1","LED","","","","LED_THT:LED_D3.0mm","~"
D100,"1","1N5819","","","","Diode_THT:D_DO-41_SOD81_P10.16mm_Horizontal","http://www.vishay.com/docs/88525/1n5817.pdf"
F1,"1","Fuse","","","","Fuse:Fuseholder_Cylinder-5x20mm_Schurter_0031_8201_Horizontal_Open","~"
IC1,"1","A3144EUA","","","","A3144:A3144EUA","https://pdf1.alldatasheet.com/datasheet-pdf/download/90853/ALLEGRO/A3144EUA.html"
J1,"1","Conn_01x02_Pin","","","","Connector_PinHeader_2.54mm:PinHeader_1x02_P2.54mm_Vertical","~"
J3,"1","Screw_Terminal_01x05","","","","TerminalBlock_Phoenix:TerminalBlock_Phoenix_MKDS-1,5-5-5.08_1x05_P5.08mm_Horizontal","~"
J4,"1","Screw_Terminal_01x02","","","","TerminalBlock_Phoenix:TerminalBlock_Phoenix_MKDS-1,5-2-5.08_1x02_P5.08mm_Horizontal","~"
J7,"1","DE9_Socket","","","","Connector_Dsub:DSUB-9_Socket_Horizontal_P2.77x2.84mm_EdgePinOffset4.94mm_Housed_MountingHolesOffset4.94mm","~"
J8,"1","DE9_Pins","","","","Connector_Dsub:DSUB-9_Pins_Horizontal_P2.77x2.84mm_EdgePinOffset4.94mm_Housed_MountingHolesOffset4.94mm","~"
J201,"1","Screw_Terminal_01x04","","","","TerminalBlock_Phoenix:TerminalBlock_Phoenix_MKDS-1,5-4-5.08_1x04_P5.08mm_Horizontal","~"
L1,"1","100uH","","","","Inductor_THT:L_Radial_D10.0mm_P5.00mm_Fastron_07M","~"
M4,M5,M6,"3","Motor_DC","","","","Connector_PinHeader_2.54mm:PinHeader_1x02_P2.54mm_Horizontal","~"
Q201,"1","IRLZ44N","","","","Package_TO_SOT_THT:TO-220-3_Vertical","http://www.irf.com/product-info/datasheets/data/irlz44n.pdf"
R1,R4,R16,R17,R18,R19,R20,R21,R22,R23,R24,R209,"12","10k","","","","Resistor_SMD:R_0805_2012Metric","~"
R2,R3,"2","4k7","","","","Resistor_SMD:R_0805_2012Metric","~"
R5,"1","1k","","","","Resistor_SMD:R_0805_2012Metric","~"
R13,R100,"2","10 k","","","","Resistor_SMD:R_0805_2012Metric","~"
R14,R26,"2","4.7k","","","","Resistor_SMD:R_0805_2012Metric","~"
R15,"1","120","","","","Resistor_SMD:R_0805_2012Metric","~"
R210,R211,"2","3.6","","","","Resistor_SMD:R_0805_2012Metric","~"
SW8,SW9,SW10,SW11,SW12,SW13,SW14,SW15,"8","SW_Push","","","","Button_Switch_SMD:SW_Push_SPST_NO_Alps_SKRK","~"
TP1,TP2,TP3,TP4,TP10,"5","TestPoint","","","","TestPoint:TestPoint_Pad_D1.0mm","~"
U1,"1","LM2596S-5","","","","Package_TO_SOT_SMD:TO-263-5_TabPin3","http://www.ti.com/lit/ds/symlink/lm2596.pdf"
U2,"1","LM1117DT-3.3","","","","Package_TO_SOT_SMD:TO-252-3_TabPin2","http://www.ti.com/lit/ds/symlink/lm1117.pdf"
U3,"1","MCP2562-E-SN","","","","Package_SO:SOIC-8_3.9x4.9mm_P1.27mm","http://ww1.microchip.com/downloads/en/DeviceDoc/25167A.pdf"
U4,"1","TMP102xxDRL","","","","Package_TO_SOT_SMD:SOT-563","https://www.ti.com/lit/ds/symlink/tmp102.pdf"
U5,"1","TB6612FNG","","","","Package_SO:SSOP-24_5.3x8.2mm_P0.65mm","https://toshiba.semicon-storage.com/us/product/linear/motordriver/detail.TB6612FNG.html"
U6,"1","24LC256","","","","Package_SO:SOIC-8_3.9x4.9mm_P1.27mm","http://ww1.microchip.com/downloads/en/devicedoc/21203m.pdf"
U7,"1","ATtiny1616-M","","","","Package_DFN_QFN:VQFN-20-1EP_3x3mm_P0.4mm_EP1.7x1.7mm","http://ww1.microchip.com/downloads/en/DeviceDoc/ATtiny3216_ATtiny1616-data-sheet-40001997B.pdf"
U8,"1","DRV8871DDA","","","","Package_SO:Texas_HTSOP-8-1EP_3.9x4.9mm_P1.27mm_EP2.95x4.9mm_Mask2.4x3.1mm_ThermalVias","http://www.ti.com/lit/ds/symlink/drv8871.pdf"
U11,"1","MAX3232","","","","Package_SO:SOIC-16_3.9x9.9mm_P1.27mm","https://datasheets.maximintegrated.com/en/ds/MAX3222-MAX3241.pdf"
U67,"1","PIC24HJ64GP504-I/PT","","","","MICRO:TQFP44_10x10MC_MCH-L","PIC24HJ64GP504-I/PT"
Y1,"1","8 MHz","","","","Crystal:Crystal_HC49-4H_Vertical","~"

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
 
 