Этот специальный тип используется только для аннотирования типов возвращаемых значений функций, которые вообще не возвращают управления. Обычно они существуют, чтобы возбуждать исключение.

```python
def exit(__status: object = ...) -> NoReturn: ...
```
