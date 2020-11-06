# Reddy 1.3

Configuración PREMIUM para Reddy 1.3 de DeDrones

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/Reddy.PNG">

¿Te has comprado un Reddy de DeDrones? ¿Quieres sacarle más partido?  

En este repositorio enseñare las cosas basicas que puede hacer mejorar nuestra experiencia con el **Reddy 1.3** de DeDrones.  
He usado la versión **Betaflight 4.2.4** recordad que para usar esta versión de Betaflight es necesario el **Betaflight Configurator version 10.7.0**.    
Antes de usar estas recomendaciones os aconsejo seguir los video tutoriales que el equipo de DeDrones nos da junto al Reddy.  
También recomiendo que si este es tu primer drone, vueles primero con los valores por defecto de Betaflight para hacerte un poco al drone.  
El uso de esta información queda bajo la responsabilidad de cada usuario.  

Si tienes dudas de como descargarte el configurador o como alcualizar el firmware visita los repositorios:  

[Actualizar firmware 4.2.x]   
https://github.com/AirbenderFPV/Actualizar-Firmware

[Actualizar/Instalar el Configurador de Betaflight v10.7]  
https://github.com/betaflight/betaflight-configurator/releases/download/10.7.0/betaflight-configurator-installer_10.7.0_win32.exe

## Menú Betaflight 4.2.x  

### Pantalla de Puertos

En esta pantalla podremos configurar los puertos de nuestro quad.    
Estos puertos normalmente vienen definidos en la placa controladora con la etiqueta TX y acompañada de un numero.    
Por ejemplo, el TX3 en la placa controladora sera el puerto Uart3 en Betaflight.   
En este caso tendremos cableado el cable del Smart Audio del VTX a este pin.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/PuertosReddy.PNG">

En esta imagen muestro la configuración recomendada para los puertos del Reddy:   
El puerto **USB VCP** para la comunicación por el puerto usb.  
El puerto **UART1** para  la comunicación Rx. Comunicación con nuestra emisora.    
El puerto **UART3** para la comunicación con el VTX a través de SmartAudio.    
El puerto **UART4** para la comunicación por Bluetooth.   
En algunos casos el **UART6** se utiliza para la telemetria con los ESC, tendriamos que declararlo en **Entrada de Sensores**  

Con aplicación **SpeedyBee** nos podemos conectar por Bluetooth y cambiar valores de Betaflight sin necesidad del ordenador.    

Puedes consutar los puertos y configuraciones recomendadas por el fabricante en el manual de tu controladora de vuelo, que en el caso del Reddy 1.3 es el Stack MAMBA 722S con la F50 Pro:  

[MAMBA F722] https://www.diatone.us/collections/mamba-stack/products/mamba-f722s-flight-controller-stack

### Pantalla de Ajustes  

En esta versión de Betaflight es **obligatorio calibrar** nuestro quad si vamos a usar los modos **Angle** o **Horizon**.

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/Ajuste.PNG">

Para **Calibrar el Acelerómetro** situar nuestro quad en una superficie plana y dar al botón.    

Es aconsejable hacer una copia de seguridad antes de hacer los cambios importantes de este repositorio, por si tenemos que deshacer estos cambios de forma rapida.

### Pantalla de Configuración  

Esta pantalla es una de las mas importantes en cuanto a el rendimiento de nuestro Reddy:

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/configuracion.PNG">

#### Funcionalidades ESC/Motor:
La opción **MOTOR_STOP** controla si los motores girarán o no al armar el quad.  
Si los motores giran al armar el quad y tenemos esta opción deshabilitada seguramente tendremos habilitado el **AIR MODE**.  
Por defecto el **Motor Idle Throttle value [percent]** tiene un valor de 4.5, esto es el porcentaje al que giraran los motores al armar.  
Por defecto el numero de **Polos del motor** viene como 14. Estos son el numero de imanes que tiene tu campana de motor.  
En tinnys a veces este numero se reduce ya que los motores son mas pequeños. Rondan sobre 12.  
Lo mejor es asegurarse mirando una campana de nuestros motores. 
Se puede habilitar el bidirectional con el switch **DShot Bidirectional**. 
Aunque los ESC de la F50 Pro pueden llegar a DSHOT1200 recomiendo poner el **DSHOT 600**.

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/DshotReddy.PNG">

#### Configuración del sistema:  

El **Acelerómetro** es el sensor que nos ayuda a controlar la inclinazión del quad.      
En caso de volar en **Angle Mode** o **Horizon Mode** necesitas tener activado este sensor.    
Revisa la pantalla de Ajustes para ver como calibrar el quad si usas esos modos.    
Normalmente las controladoras de vuelo no trae equipado un Barómetro ni un Magnetómetro.     
Lo mejor en estos casos es **Desactivar** estos dos sensores.   
El mejor valor para el **PID LOOP** es a **8k**    

Los ESC del Stack MAMBA que nos vienen con el Reddy 1.3 ya estan actualizados, pero si en un futuro los cambiamos recordad de tener los ESC actualizados a la útltima versión.

#### Armado y Aliniación de Placa y Sensores:

Si tenemos el Acelerómetro activado, habilitaremos la selección del Ángulo de armado máximo.  
Personalmente recomiendo el valor **180º** para poder armar el quad bajo cualquier inclinación.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/configuracion2.PNG">

#### Otras funcionalidades:

Normalmente se dejan tal como vienen de serie a excepción de estas tres, que **tienen que estar activadas**:

- Air Mode:  
Activa permanentemente el Air Mode. Se puede deshabilitar aqui i condicionarlo en la pantalla de Modos.  
- OSD:  
Permite sobreponer información sobre la imagen de la camara. Se configura en la pantalla de OSD.  
- DYNAMIC_FILTER
Filtro dinamico para el giroscopio

### Pantalla de Energía y Batería

Esta pantalla nos ayuda con la gestión de el voltage y la corriente de nuestro quad.   
Para el Stack Mamba 722 de nuestro reddy 1.3 necesitamos los siguientes valores:  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/EnergiaReddy.PNG">

Puedes consutar los escalados recomendados por el fabricante en el manual de tu controladora de vuelo:  

[MAMBA F722] https://www.diatone.us/collections/mamba-stack/products/mamba-f722s-flight-controller-stack


### Pantalla de Ajustar PID

#### PID  

Esta pestaña nos ayuda a calibrar el PID de nuestro quad, si tienes poca experiencia es mejor provar los ajustes por defecto.  
Una vez hayas volado un tiempo, puedes poner los siguientes valores y provar si mejora tu experiencia de vuelo.    

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/PIDsFreestyleReddy.PNG">

Para la primera vez que pruebes estos valores es muy importante cumplir los sigüientes requisitos:

- Palas nuevas, sin defectos ni deformaciones     
Personalmente he provado estos ajustes con las palas por defecto que vienen con el Reddy 1.3 y con las Hurricane 5146 de GemFan.  
Me han gustado mas las Hurricane 5146 pero las que vienen por defecto no dan un mal resultado.  

-Temperaduta de los motores  
Volar 30s-1min tranquilo, sin dar mucho "gas" y bajar el drone para comprovar temperatura de los motores.  
No tendrían que calentarse. Un buen indicador es poder mantener el dedo mas de 3s en contacto con el motor, eso nos indica que esta por debajo de 60ºC.  
Volver a volar otros 30s-1min como volaríamos de forma normal y bajar el drone para comprovar temperatura de los motores.
Si no se nos han calentado podemos volar con seguridad 


#### TASAS  
Esta pestaña nos ayuda a calibrar los "rates" o tasas de nuestro quad, en otras palabras la sensibilidad de nuestros sticks.   
Podemos editar el perfil de cada palanca editando los valores para respuestas mas ajustadas a nuestra forma de volar.  
Si tienes poca experiencia es mejor dejar los ajustes por defecto.  

#### FILTROS  
Esta pestaña nos ayuda a filtrar las señales de nuestro quad, si tienes poca experiencia es mejor dejar los ajustes por defecto.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/Filtros.PNG">

Es muy recomendable en esta pestaña editar los valores del **Filtro Notch Dinámico** situado en la parte inferior izquierda.  
Los valores recomdendados y provados por Joshua Bradwell son los que aparecen en la imagen.  
Giro Filtro Notch Dinámico Ancho = 0  
Giro Filtro Notch Dinámico Q =250   
Giro Filtro Notch Dinámico Min =90   
Giro Filtro Notch Dinámico Max =350   

Además, los valores multiplicadores **Filtro Giro** y **Filtro D Term** se pueden mover un poco para filtrar menos la señal que enviamos a nuestro quad y tener una respuesta mas rapida. Hay que mover los dos por igual.  

Personalmente he provado el valor **1.2 en ambos**, si provais alguno y no os convence volver a el valor por defecto 1 en ambos.  

Para mas información de ajustes rapidos recomendados visita:

[Ajustes rapidos recomendados en Betaflight 4.2.x] https://github.com/AirbenderFPV/Ajustes-rapidos-recomendados-en-Betaflight-4.2.x



### Pantalla de Caja Negra

La caja negra nos ayuda a guardar datos de los sensores en tiempo real para su posterior analisis.  
Para un mejor rendimiento de la controladora de vuelo, si no vamos a usar la caja negra, es mejor **desactivarla**.

[Notas de la versión] https://github.com/betaflight/blackbox-log-viewer/releases

Descarga el software para ver los log de la caja negra:  
https://github.com/betaflight/blackbox-log-viewer


### Pantalla de CLI

Esta pantalla nos permite introducir comandos para programar o extraer valores de la controladora de vuelo de nuestro drone  
Para guardarlos tenemos que ejecutar el comando **Save**.

Podemos listar nuestros ajustes cambiados respecto a los valores por defecto con el comando **diff_all**


#### Fuentes de información

[Notas oficiales de la versión] https://github.com/betaflight/betaflight/wiki/4.2-Tuning-Notes    

[Joshua Bardwell] https://www.youtube.com/watch?v=rhfOVJMxY7E    

[QuadMx Drones] https://www.youtube.com/watch?v=tCgN-EwdSQ8     

[Airbender_FPV] https://www.instagram.com/airbender_fpv/  
