---
tags:
  - python
---

`enumerate(list)` - принимает массив, возвращает индекс и значение каждого элемента.  Таки образом можно при переборе списка, можно сразу получать и значение и индекс элемента

```python
list = ['new', 'old', 'age']

for index, val im enumerate(list):
	print(index, val)
