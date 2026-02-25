#programming

TCP-сокеты
является надежным доставщиком информации между сервером и клиентом, что является его основной фишкой
Особенности:
- Он надежен, отброшенные в сети пакеты обнаруживаются и повторно передаются отправителем
- Данные доставляются с сохранением порядка очередности. В приложении данные считываются в порядке их записи отправителем

UDP-сокеты
- не надежны, данные могут считываться получателем с изменением порядка очередности записей отправителя


Ниже можно наблюдать порядок работы TCP сервера и клиента


![[Pasted image 20240418082154.png]]

Начиная с верхнего левого угла, показаны серверные вызовы API на сервере, которые настраивают «прослушиваемый» сокет:  
  

- `socket()`
- `.bind()`
- `.listen()`
- `.accept()`

что бы установить подключение к серверу и инициировать трехэтапное рукопожатие, на клиенте вызывается 
`.connect()`

Простой эхо сервер:
```python
import socketHOST = "127.0.0.1"  
PORT = 65432
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:    
	s.bind((HOST, PORT))
	s.listen()
	conn, addr = s.accept()
	with conn:
		print(f"Connected by {addr}")
		while True:
			data = conn.recv(1024)
			if not data:
				break
			conn.sendall(data)
```

Эхо клиент:

```python
import socketHOST = "127.0.0.1"  
PORT = 65432 
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:  
	s.connect((HOST, PORT))
	s.sendall(b"Hello, world")
	data = s.recv(1024)
	print(f"Received {data!r}")
```



