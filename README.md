# Reddy 1.3

Configuración PREMIUM para Reddy 1.3 de DeDrones

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/reddy.PNG">

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
Por defecto el numero de **Polos del motor** viene como 14. Estos son el numero de imanes que tiene tu campana de motor Xing-e 2207 2450Kv.   
Recomiendo habilitar el bidirectional con el switch **DShot Bidirectional**.   
Aunque los ESC de la F50 Pro pueden llegar a DSHOT1200 recomiendo poner el **DSHOT 600**.

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/DshotReddy.PNG">

#### Configuración del sistema:  

El **Acelerómetro** es el sensor que nos ayuda a controlar la inclinazión del quad.      
En caso de volar en **Angle Mode** o **Horizon Mode** necesitas tener activado este sensor.    
Revisa la pantalla de Ajustes para ver como calibrar el quad si usas esos modos.    
Normalmente las controladoras de vuelo no trae equipado un Barómetro ni un Magnetómetro.     
Lo mejor para el rendimiento es **Desactivar** los dos sensores (Barómetro y Magnetómetro).   
El mejor valor para el **PID LOOP** es a **8k**.      

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
- DYNAMIC_FILTER:  
Filtro dinamico para el giroscopio

### Pantalla de Energía y Batería

Esta pantalla nos ayuda con la gestión de el voltage y la corriente de nuestro quad.   
Para el Stack Mamba 722 de nuestro reddy 1.3 necesitamos los siguientes valores:  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/EnergiaReddy.PNG">

Puedes consutar los escalados recomendados por el fabricante en el manual de tu controladora de vuelo:  

[MAMBA F722] https://www.diatone.us/collections/mamba-stack/products/mamba-f722s-flight-controller-stack


### Pantalla de Ajustar PID

Antes de empezar a Ajustar los PID, Rates y Filtros, os recomiendo copiar los sigüientes comandos en la pantalla del CLI.  
Os dejo los ajustes mas usados, podeis encontrar todos en https://github.com/AirbenderFPV/Ajustes-rapidos-recomendados-en-Betaflight-4.2.x    
Es muy importante ejecutar el comando **Save** despues de cada Copy/Paste.   

**Race y Freestyle**  
set iterm_relax_cutoff = 20  
set rc_smoothing_auto_smoothness = 7  
set ff_interpolate_sp = AVERAGED_2  
set ff_smooth_factor = 20  
set ff_spike_limit = 70  
set ff_boost = 15  
set feedforward_transition = 0  
set yaw_lowpass_hz = 100  
set throttle_boost = 7  
set throttle_boost_cutoff = 25  
set dyn_lpf_dterm_curve_expo = 7  
set gyro_rpm_notch_q = 700  

**Grabaciones HD (Reddy con Camara de acción, movimientos menos agresivos)**  
set iterm_relax_cutoff = 10  
set rc_smoothing_auto_smoothness = 20  
set ff_interpolate_sp = AVERAGED_3  
set ff_smooth_factor = 40  
set ff_spike_limit = 55  
set ff_boost = 0  
set feedforward_transition = 40  
set yaw_lowpass_hz = 70  
set throttle_boost = 5  
set throttle_boost_cutoff = 10  
set dyn_lpf_dterm_curve_expo = 7  
set gyro_rpm_notch_q = 800  

**Mejora rendimiento 4in1 ESC**  
set dyn_lpf_dterm_curve_expo = 6  
set vbat_sag_compensation = 100  
set vbat_pid_gain = OFF  
set rc_smoothing_type = FILTER  
set rc_smoothing_input_hz = 0  
set rc_smoothing_derivative_hz = 0  
set rc_smoothing_input_type = BIQUAD  
set rc_smoothing_derivative_type = PT1  
set rc_smoothing_auto_smoothness = 10  

Recordad es muy importante ejecutar el comando **Save** despues de cada Copy/Paste para que se guarden los ajustes.  
Personalmente vuelo con los ajustes de **Race y Freestyle** y con la **Mejora rendimiento 4in1 ESC** que me ha dado más estabilidad y más tiempo de vuelo.

Si en algún momento quereis vover a los valores por defecto:  

**Valores por defecto**    
set iterm_relax_cutoff = 15    
set rc_smoothing_auto_smoothness = 10    
set ff_interpolate_sp = AVERAGED_2    
set ff_smooth_factor = 37    
set ff_spike_limit = 60    
set ff_boost = 15    
set feedforward_transition = 0    
set yaw_lowpass_hz = 0    
set throttle_boost = 5    
set throttle_boost_cutoff = 15    
set dyn_lpf_dterm_curve_expo = 5   
set gyro_rpm_notch_q = 500   
set iterm_windup = 100   

Una vez aplicados estos "pretunes" vamos a profundizar

#### PID  

Esta pestaña nos ayuda a calibrar el PID de nuestro quad, si tienes poca experiencia es mejor provar los ajustes por defecto.  
Una vez hayas volado un tiempo, puedes poner los siguientes valores y provar si mejora tu experiencia de vuelo.   
Los PID que vereis a continuación son para Freestyle, bastante genéricos, pero nos ayudaran a mejorar la experiencia de vuelo con el Reddy 1.3.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/PIDsFreestyleReddy.PNG">

Para la primera vez que pruebes estos valores es muy importante cumplir los sigüientes requisitos:  

- Palas nuevas, sin defectos ni deformaciones       
Personalmente he provado estos ajustes con las palas por defecto que vienen con el Reddy 1.3 y con las Hurricane 5146 de GemFan.    
Me han gustado mas las Hurricane 5146 pero las que vienen por defecto no dan un mal resultado.   

- Temperaduta de los motores    
Volar 30s-1min tranquilo, sin dar mucho "gas" y bajar el drone para comprovar temperatura de los motores.    
No tendrían que calentarse. Un buen indicador es poder mantener el dedo mas de 3s en contacto con el motor, eso nos indica que esta por debajo de 60ºC.    
Volver a volar otros 30s-1min como volaríamos de forma normal y bajar el drone para comprovar temperatura de los motores.  
Si no se nos han calentado podemos volar con seguridad   

- Flip over after Crash  
Si usais este modo, sirve para dal la vuelta al drone cuando chocamos y quedamos boca-abajo, después de todas estas comprovaciones recomiendo provar 3 o 4 veces este modo y volver a revisar la temperatura de los motores. Después de usar este modo normalmente se calentarán mas de lo normal ya que pedimos un sobreesfuerzo al motor. Comprovar que esto no pueda ocasionaros altas temperaturas.   

Siempre podemos volver a los PID por defecto, poniendo todos los sliders (barritas) a 1.  


#### TASAS  
Esta pestaña nos ayuda a calibrar los "rates" o tasas de nuestro quad, en otras palabras la sensibilidad de nuestros sticks.     
Podemos editar el perfil de cada palanca editando los valores para respuestas mas ajustadas a nuestra forma de volar.   
Os dejo los Rates que tengo yo para tener un mejor control del centro del accelerador:  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/RatesReddy.PNG">

Evidentemente, esta pantalla es la que mas se personaliza por la forma de vuelo de cada piloto.  
Si ya teneis unos Rates que os ivan bien, os animo a provar todos estos ajustes con vuestros rates!  

#### FILTROS  
Esta pestaña nos ayuda a filtrar las señales de nuestro quad, si tienes poca experiencia es mejor dejar los ajustes por defecto.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/Filtros.PNG">

Es muy recomendable en esta pestaña editar los valores del **Filtro Notch Dinámico** situado en la parte inferior izquierda.  
Los valores recomdendados y provados por Joshua Bradwell, QuadMX y Airbender_FPV son los que aparecen en la imagen.  
Giro Filtro Notch Dinámico Ancho = 0  
Giro Filtro Notch Dinámico Q =250   
Giro Filtro Notch Dinámico Min =90   
Giro Filtro Notch Dinámico Max =350   

Además, los valores multiplicadores **Filtro Giro** y **Filtro D Term** se pueden mover un poco para filtrar menos la señal que enviamos a nuestro quad y tener una respuesta mas rápida. Hay que mover los dos por igual.  

Personalmente he provado el valor **1.2 en ambos**, y me da muy buen resultado para el freestyle.    
Para algo mas cinematico dejad el valor por defecto 1 en ambos.  
Si provais alguno y no os convence volver a el valor por defecto 1 en ambos.   

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
