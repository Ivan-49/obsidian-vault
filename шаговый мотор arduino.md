---
tags:
  - arduino
language: C++
type of work: крутить мотор
полезность: 10
создал заметку: 2024-04-23T22:01:00
---


### на этот раз я не стал пользоваться библиотеками, а написал все с нуля

```cpp
void stepper(long degree_angle) {
  if (degree_angle>0){
  for (long i = 0; i<(degree_angle * 256); i++){
    digitalWrite(in1, LOW);
    digitalWrite(in2, LOW);
    digitalWrite(in3, HIGH);
    digitalWrite(in4, HIGH);
    delay(dl);
    digitalWrite(in1, LOW);
    digitalWrite(in2, HIGH);
    digitalWrite(in3, HIGH);
    digitalWrite(in4, LOW);
    delay(dl);
    digitalWrite(in1, HIGH);
    digitalWrite(in2, HIGH);
    digitalWrite(in3, LOW);
    digitalWrite(in4, LOW);
    delay(dl);
    digitalWrite(in1, HIGH);
    digitalWrite(in2, LOW);
    digitalWrite(in3, LOW);
    digitalWrite(in4, HIGH);
    delay(dl);
  }
  }
  else if(degree_angle<0){
  degree_angle = -1*degree_angle;
  for (long i = 0; i<(degree_angle * 256); i++){
    digitalWrite(in1, HIGH);
    digitalWrite(in2, LOW);
    digitalWrite(in3, LOW);
    digitalWrite(in4, HIGH);
    delay(dl);
    digitalWrite(in1, HIGH);
    digitalWrite(in2, HIGH);
    digitalWrite(in3, LOW);
    digitalWrite(in4, LOW);
    delay(dl);
    digitalWrite(in1, LOW);
    digitalWrite(in2, HIGH);
    digitalWrite(in3, HIGH);
    digitalWrite(in4, LOW);
    delay(dl);
    digitalWrite(in1, LOW);
    digitalWrite(in2, LOW);
    digitalWrite(in3, HIGH);
    digitalWrite(in4, HIGH);
    delay(dl);
  }
  }
}
```

Функция `stepper()` принимает количество π(половина оборота) на которое должен прокрутиться мотор, 
то есть если надо повернуть мотор на 180 градусов то надо надо вызвать `stepper()` c аргументом 1
```cpp 
stepper(1);
```
то есть на 1π









