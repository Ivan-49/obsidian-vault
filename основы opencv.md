---
tags:
  - python
  - baselibrary
---

Часто opencv используют в купе с numpy, для быстрой обработки больших массивов

```python
pip install opencv-python
```

```python
import cv2

img = cv2.imread('img.jpeg')

```

imread, функция предназначена для открытия фото

```python

img = cv2.cvtCoolor(img, cv2.COLOR_...)

```

cvt.Color, для изменения цветового профиля изображения.

Для отображения фото на экране:
```python
import cv2
image_file = "path_file"
img = cv2.imread(image_file)

cv2.imshow('НАЗВАНИЕ ОКНА, img)

cv2.waitkey(0)
```

ноль который в данном случае принимает функция waitkey обозначает то сколько времени будет показываться фото на экране, в тысячных секунды, если там как аргумент 0 то она будет показываться вечно до остановки программы

по той же логике можно работать с видео   [[работа с видео opencv]]

#programming