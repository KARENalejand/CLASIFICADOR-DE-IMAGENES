# CLASIFICADOR-DE-IMAGENES

###PRIMER PASO

- Creamos una carpeta con el nombre lcd y otra con el nombre perro.
[![N|Solid](https://github.com/KARENalejand/imagenes/blob/main/f.png)](https://nodesource.com/products/nsolid)

- Dentro de dichas carpetas estarán las imágenes que se utilizarán para el
entrenamiento.
[![N|Solid](https://github.com/KARENalejand/imagenes/blob/main/CARPETAS.png)](https://nodesource.com/products/nsolid)

### Código 
- Teniendo  completo el primer paso pasamos a  realizamos el siguiente codigo

- primero importamos las  librerias 

```sh
$ import cv2
$ import numpy as np
$ import os
$ import matplotlib.pyplot as plt
```

- Luego cargamos las fotos  de las carpetas especificas
```sh
$ lcd_folder_path="C:/Users/kv460/Documents/lcd/lcd"
$ lcd=[]
$ img_size=150
$ for img in os.listdir(lcd_folder_path):
    $ img = cv2.imread(os.path.join(lcd_folder_path,img))
    $ #img_gray= cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    $img_resize= cv2.resize(img,(img_size,img_size))
    $lcd.append(img_resize)
```
En esta imagen se explica cada parte de  ese texto
[![N|Solid](https://github.com/KARENalejand/imagenes/blob/main/parte2.png)](https://nodesource.com/products/nsolid)

- vizualizamos tamaño de la imagen

```sh
$ lcd = np.array(lcd)
$ print(lcd.shape)
```
- Se realiza exactamente lo mismo, pero ahora para la carpeta de perro

```sh
$ ####cargamos las fotos  de las carpetas especificas### 
$ perro_folder_path="C:/Users/kv460/Documents/lcd/perro"
$ perro=[]
$ img_size=150
$ for img in os.listdir(perro_folder_path):
    $ img = cv2.imread(os.path.join(perro_folder_path,img))
    $ #img_gray= cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    $ img_resize= cv2.resize(img,(img_size,img_size))
    $ perro.append(img_resize)
    
$ perro = np.array(perro)
$ print(perro.shape)
```
- Graficamos las imagenes
```sh
$ print(lcd[4].shape)
$ plt.figure()
$ plt.imshow(np.squeeze(lcd[2]))
$ plt.colorbar()
$ plt.grid(False)
$ plt.show()
######
$ print(perro[2].shape)
$ plt.figure()
$ plt.imshow(np.squeeze(perro[2]))
$ plt.colorbar()
$ plt.grid(False)
$ plt.show()
```

[![N|Solid](https://github.com/KARENalejand/imagenes/blob/main/parte%203.png)](https://nodesource.com/products/nsolid)

- Se juntarán las imágenes con una concatenación
```sh
$ images=np.concatenate([lcd,perro])
$ #convertir a un arreglo 
$ Images=np.array(images)
$ print(len(images)) #imprimecuantas imagenes hay en total
```
- En este momento etiquetas todas nuestras imágenes teniendo en cuenta, cuantas imágenes hay en cada carpeta en este caso en lcd hay 41 y en la carpeta perro hay81

```sh
$ etiquetas_lcd=np.repeat(0,41)#lcd se reconoce con elnumero 0
$ print(len(etiquetas_lcd))
$ print(etiquetas_lcd)
#################etiquetamos##############
$ etiquetas_perro=np.repeat(1,81)#perro se reconoce con elnumero 1
$ print(len(etiquetas_perro))
$ print(etiquetas_perro)
```
- Ahora damos el nombre a nuestras clases teniendo en cuenta que lcd fue nuestra primera etiqueta y perro la segunda, por lo cual deben ser colocadas en ese orden.
Posterior a esto concatenamos las etiquetas
```sh
$ class_names=['lcd','perro']
$ #concatenamos clases
$ labels=np.concatenate([etiquetas_lcd,etiquetas_perro])
$ print(len(labels))
$ print(labels)
```



















