```python
from collections.abc import Sequence 
from random import shuffle 
from typing import TypeVar 

T = TypeVar('T') 

def sample(population: Sequence[T], size: int) -> list[T]:
	if size < 1: 
		raise ValueError('size must be >= 1') 
	result = list(population) 
	shuffle(result) 
	return result[:size]
```

![[Pasted image 20240211000120.png]]

```python
from collections.abc import Iterable 
from decimal import Decimal 
from fractions import Fraction 
from typing import TypeVar 

NumberT = TypeVar('NumberT', float, Decimal, Fraction) 

def mode(data: Iterable[NumberT]) -> NumberT:
```

Связанный TypeVar
еще одна возможность TypeVar: необязательный именованный параметр bound. Он задает верхнюю границу допустимых типов. В примере 8.18 мы имеем bound=Hashable, это означает, что параметр-тип может быть Hashable или любым его подтипом

```python
from collections import Counter 
from collections.abc import Iterable, Hashable 
from typing import TypeVar 

HashableT = TypeVar('HashableT', bound=Hashable) 

def mode(data: Iterable[HashableT]) -> HashableT: 
	pairs = Counter(data).most_common(1) 
	if len(pairs) == 0: 
		raise ValueError('no mode for empty data') 
	return pairs[0][0]
```