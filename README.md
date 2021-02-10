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



    
