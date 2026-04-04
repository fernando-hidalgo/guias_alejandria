# Mac Media Center -  Guía

## **1️⃣ Crear la carpeta compartida en Windows**

1.  En tu PC Windows, crea una carpeta donde pondrás tus películas, por ejemplo:  
    `D:\Peliculas`
2.  Haz clic derecho sobre la carpeta → **Propiedades** → pestaña **Compartir** → **Compartir…**
3.  Selecciona el usuario o “Todos” y da permisos de lectura (y escritura si quieres añadir archivos desde el Mac).
4.  Pulsa **Compartir** y apunta la **dirección de IP** mediante **ipconfig en terminal**, algo como: `192.168.x.x`

## **2️⃣ Conectar el Mac a la carpeta de Windows**

1.  En tu Mac, abre **Finder** → menú **Ir** → **Conectarse al servidor…** (⌘K).
2.  Introduce la dirección de la carpeta compartida usando el formato SMB:
`smb://192.168.x.x/Peliculas`
3. Introduce el usuario y contraseña de Windows y pulsa **Conectar**.
4. Marca **Recordar esta contraseña en mi llavero** para que no te pida cada vez.

#### ⚠️El usuario de Windows debe tener contraseña para evitar mareos ⚠️

## **3️⃣ Montar automáticamente al iniciar**
1.  En el Finder, ve a **Preferencias del Sistema → Usuarios y grupos → Ítems de inicio**.
2.  Pulsa el “+” y añade el disco de red que acabas de montar.
3.  Ahora, cada vez que enciendas el Mac, la carpeta compartida se montará automáticamente.

## **4️⃣ Configurar Kodi para usar la carpeta de red**
1.  Abre **Kodi → Videos → Archivos → Añadir vídeos…**
2. Selecciona **Buscar** → **Añadir fuente de red** → **SMB**. Esta opción en ocasiones me ha fallado, pero si vas a **Volumenes** verás la carpeta compartida sin problema, podrás elegirla como fuente.
3. Cuando te pregunte por el tipo de contenido, selecciona **Películas** y activa **Escanear contenido y obtener metadatos**.
4. Instala un **skin** bonito para que las portadas se vean más grandes. **fTV** es probablemente las más sencilla de usar y viene incluida con Kodi.
5. Añade **Kodi** también a **Ítems de inicio**, para que se abra directamente al enceder el Mac

## **5️⃣ Configurar el mando TV**
Lo más probable es que la mayoría de botones del mando no respondan. Para configurar el mando, se utiliza **Karabiner-Elements**

Supongamos que el **botón Atrás** no funciona, y se quiere mapear para que funcione como **Escape** (que la tecla que Kodi entiende como atrás)

1. Abre **Karabiner EventViewer** (El del simbolo de lupa) y pulsa la tecla, se mostrará su clave en el log de eventos, algo como: `{consumer_key_code:ac_back}`
2. Abre **Karabiner Settings → Simple Modifications → For all devices** Lo suyo sería elegir en concreto el mando, pero me ha dado problemas.
3. Añade una regla, a la izquierda el código del botón, a la derecha su mapeo. Por ejemplo, para este caso `ac_back → escape`

Este programa funciona por defecto al arrancar el Mac, así que mas allá de esta configuración no hay que tocar nada.

---
Listo!

Ahora el Mac arrancará, montará la carpeta de red y entrará en Kodi, donde se muestran las películas añadidas.

Si una película se añade al vuelo, con el Mac encendido, con pulsar Actualizar Biblioteca ya aparecerá en el listado. Una vez vista y eliminada de la carpeta, al abrirla de nuevo Kodi te dará la opción de borrarla.

---

## **6️⃣ Extra: Copiar las películas al local**
Se puede crear un script que copie en una carpeta del disco local del Mac las pelis que se añaden a la carpeta compartida, para que Kodi no las corra por red.

Después de hacer varias pruebas *(Interestelar 4k 20GB)*, no creo que merezca la pena el mareo y los posibles errores de copiado, frente a simplemente conectar el Mac por cable, funciona de lujo. Incluso por WiFi no ha dado problema alguno.

En todo caso, la opción está ahí, es pedirle a chatGPT que te eche un cable generando el código y luego pedirle a Kodi que mire en dicha carpeta, como se explica arriba.
