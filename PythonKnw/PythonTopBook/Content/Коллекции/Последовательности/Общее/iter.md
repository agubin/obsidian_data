Встроенная функция iter выполняет следующие действия. 
1. Смотрит, реализует ли объект метод __iter__, и, если да, вызывает его, чтобы получить итератор. 
2. Если метод __iter__ не  реализован, но реализован метод __getitem__, то Python создает итератор, который пытается извлекать элементы по порядку, начиная с индекса 0. 
3. Если и это не получается, то возбуждается исключение – обычно с  сообщением 'C' object is not iterable, где C – класс объекта.


![[Pasted image 20240304230459.png]]


![[Pasted image 20240304231419.png]]

Чтобы «поддержать несколько активных обходов», необходимо иметь возможность получить несколько независимых итераторов от одного итерируемого объекта, причем каждый итератор должен хранить собственное внутреннее состояние, поэтому для правильной реализации паттерна нужно всякий раз обращаться к  функции iter(my_iterable) за новым независимым итератором
