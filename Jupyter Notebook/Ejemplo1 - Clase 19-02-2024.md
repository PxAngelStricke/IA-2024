# Ejemplo de cargar imagen

Para instalar opencv se requiere el siguiente comando

pip3 install python-contrib-opencv
conda install python-contrib-opencv


```python
import cv2 as cv
```


```python
pwd
```




    'C:\\Users\\Px Angel'




```python
img = cv.imread('C:\\Users\\Px Angel\\Documents\\IA\\Material\\tr.jpg',0)
print(img.shape)
w, h = img.shape
cv.imshow('Ejemplo1', img)
for i in range(w):
    for j in range(h):
        #img[i, j] = 255 - img[i, j]
        if(img[i, j] > 150):
            img[i, j] = 255
        else:
            img[i, j] = 0
cv.imshow('Ejemplo2', img)
cv.waitKey(0)
cv.destroyAllWindows()
```

    (488, 489)
    


```python

```
