```python
def make_averager(): 
	count = 0 
	total = 0 
	
	def averager(new_value): 
		count += 1 
		total += new_value 
		return total / count 
		
	return averager
```

Этот код вызовет ошибку из-за присваивания свободным переменным count, total значений, внутри averager. Это делает их локальными.

Что бы работать со свободными переменными локально нужно использовать nonlocal
```python
def make_averager(): 
	count = 0 
	total = 0 
	
	def averager(new_value): 
		nonlocal count, total
		count += 1 
		total += new_value 
		return total / count 
		
	return averager
```