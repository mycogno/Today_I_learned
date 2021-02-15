# if \_\_name\_\_ == "\_\_main\_\_" 의 비밀

---

### 종종 if \_\_name\_\_ == "\_\_main\_\_": 뒤에 코드를 작성하는 경우를 많이 보았는데 왜 쓰는걸까?

```python
python fibo.py
```

이런 식으로 직접 모듈을 실행하면 \_\_name\_\_ == "\_\_main\_\_" 이다.

하지만,

```python
import fibo
```

이런 식으로 다른 코드에 imported 되어 실행 될 때에는 그렇지 않다.

즉, 직접 코드를 main으로 실행할 때에만 명령을 수행하게 만들 때 이를 사용한다.

```python
# fibo.py

def fib(n):    # write Fibonacci series up to n
    a, b = 0, 1
    while a < n:
        print(a, end=' ')
        a, b = b, a+b
    print()

if __name__ == "__main__":
    fib(10)
```

```python
#test.py

import fibo
fibo.fib(20)
# if __name__ == "__main__": 부분에 해당하는
# 부분 fib(10)은 실행되지 않음
```

스크립트에서 직접 모듈의 소스코드를 실행함으로써 모듈을 테스트 하는 용도로 사용할 수 있다.
