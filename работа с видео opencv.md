#programming 
работа с видео с этой библиотекой, осуществляется по тому же принципу что и с фото, так как видео это много фото которые идут под ряд, по этому наша цель сейчас раздолбить видео на отдельные фото и показывать их по одному

```python
import cv2  
cap = cv2.VideoCapture(0)  
while(True):  
    ret, frame = cap.read()  
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)  
    cv2.imshow('Video', frame)  
    # cv2.imshow('frame',gray)  
    if cv2.waitKey(1) & 0xFF == ord('q'):  
        break  
cap.release()  
cv2.destroyAllWindows()

```
зная python вы скорее всего сможете разобраться что тут происходит

  [[основы opencv|основы opencv]] - тут можно посмотреть о работе с фото, так как видео это много фото
  