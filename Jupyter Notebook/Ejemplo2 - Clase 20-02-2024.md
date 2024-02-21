# Ejemplo 2
## Seccion 1
Transformando imagenes en tamaños y jugando con su pixelaje y posicionamiento


```python
import cv2 as cv
import numpy as np
```

## Seccion
funcion escala para escalar imagenes a diferentes tamaños


```python
def escala(imx, escala):
    width = int(imx.shape[1] * escala/100)
    height = int(imx.shape[0] * escala/100)
    size = (width, height)
    im = cv.resize(imx, size, interpolation = cv.INTER_AREA)
    return im
```

## Seccion
Utiliando la funcion de escala para escalar la imagen a un 200%


```python
img = cv.imread('C:\\Users\\Px Angel\\Documents\\IA\\Material\\tr.jpg', 1)
img2 = escala(img, 200)
cv.imshow('img', img)
cv.imshow('img2', img2)
cv.waitKey(0)
cv.destroyAllWindows()
```

## Seccion
Jugando con los canales de colores para conseguir combinaciones y extraer colores y su representacion


```python
img = cv.imread('C:\\Users\\Px Angel\\Documents\\IA\\Material\\tr.jpg', 1)
w, h = img.shape[:2]
img2 = np.zeros((w, h), dtype='uint8')

r,g,b = cv.split(img)
#r = cv.merge([r, img2, img2])
#g = cv.merge([img2, g, img2])
#b = cv.merge([img2, img2, b])

r1 = cv.merge([g, r, b])
g1 = cv.merge([r, b, g])
b1 = cv.merge([b, r, g])

cv.imshow('r', r1)
cv.imshow('g', g1)
cv.imshow('b', b1)
cv.waitKey(0)
cv.destroyAllWindows()
```

## Seccion
Transformando la imagen


```python
img = cv.imread('C:\\Users\\Px Angel\\Documents\\IA\\Material\\tr.jpg', 0)
w, h = img.shape[:2]
img2 = np.ones((w, h), dtype='uint8')*150
for i in range(w):
    for j in range(h):
        img2[int(i*0.5)+100, int(j*0.5)+100] = img[i, j]
cv.imshow('img', img)
cv.imshow('img2', img2)
cv.waitKey(0)
cv.destroyAllWindows()
```


```python

```
