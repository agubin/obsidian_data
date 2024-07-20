```python
from functools import singledispatch
from collections import abc
import fractions
import decimal
import html
import numbers

@singledispatch
def htmlize(obj: object) -> str:
	content = html.escape(repr(obj))
	return f'<pre>{content}</pre>'

@htmlize.register
def _(text: str) -> str:
	content = html.escape(text).replace('\n', '<br/>\n')
	return f'<p>{content}</p>'

@htmlize.register
def _(seq: abc.Sequence) -> str:
	inner = '</li>\n<li>'.join(htmlize(item) for item in seq)
	return '<ul>\n<li>' + inner + '</li>\n</ul>'

@htmlize.register
def _(n: numbers.Integral) -> str:
	return f'<pre>{n} (0x{n:x})</pre>'

@htmlize.register
def _(n: bool) -> str:
	return f'<pre>{n}</pre>'

#Тип можно передать в аннотацию, а не указывать у параметра
@htmlize.register(fractions.Fraction)
def _(x) -> str:
	frac = fractions.Fraction(x)
	return f'<pre>{frac.numerator}/{frac.denominator}</pre>'

#Эти декораторы-регистраторы возвращают не декрированную функцию
#поэтому можно использовать несколько для одной реализации и нескольких типов
@htmlize.register(decimal.Decimal)
@htmlize.register(float)
def _(x) -> str:
	frac = fractions.Fraction(x).limit_denominator()
	return f'<pre>{x} ({frac.numerator}/{frac.denominator})</pre>'
```

Замечательное свойство механизма singledispatch состоит в том, что специализированные функции можно зарегистрировать в  любом месте системы, в любом модуле. Если впоследствии вы добавите модуль, содержащий новый пользовательский тип, то сможете без труда написать новую специализированную функцию для обработки этого типа. А также реализовать функции обработки для классов, которые вы не писали и не можете изменить