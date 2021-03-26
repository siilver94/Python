
## 예외처리

<br/>


- **예외(exception)** 란 코드를 실행하는 중에 발생한 에러를 뜻합니다. 

- 예외가 발생했을 때도 스크립트 실행을 중단하지 않고 계속 실행하게 해 줘야 합니다.

- **try**에 실행할 코드를 넣고 **except**에 예외가 발생했을 때 처리하는 코드를 넣습니다.

`try ~ except`

<br/>

```python

try:

    print('나누기 전용 계산기')
    num1 = int(input('첫번째 숫자를 입력 : '))
    num2 = int(input('두번째 숫자를 입력 :'))
    print('{0} / {1} = {2}'.format(num1,num2,int(num1/num2)))
except ValueError :

    print('에러 발생!')
    
```

<br/>

## 예외 발생

임의로 예외 처리를 설정 할 수 있다.

`raise` 를 사용하여 설정 가능.

```python
try:

    print('한 자리 숫자 나누기 전용 계산기')
    num1 = int(input('첫번째 숫자를 입력 : '))
    num2 = int(input('두번째 숫자를 입력 : '))
    if num1 >= 0 or num2 >= 10:
        raise ValueError
    print('{0} / {1} = {2}'.format (num1,num2,int(num1/num2)))
except ValueError:
    print('잘못 된 값. 한자리 숫자만 입력하세요')
```

<br/>

## 사용자 정의 예외 처리

`class SoldOutError(Exception):` 을 활용하여 정의 할 수 있다.

```python
class SoldOutError(Exception):
    pass

chicken = 10
waiting = 1
while(True):
    try :
        print('[남은 치킨 : {0}]'.format(chicken))
        order = int(input('치킨 몇 마리 주문하시겠습니까?'))
        if order > chicken :
            print('재료가 부족합니다.')
        elif order <= 0:
            raise ValueError
        else :
            print('[대기번호 {0}] {1} 마리 주문이 완료되었습니다.'.format(waiting, order))
            waiting += 1
            chicken -= order
        if chicken == 0 :
            raise SoldOutError
    except ValueError :
        print('잘못된 값을 입력하였습니다.')
    except SoldOutError :
        print('재고가 소진되어 더 이상 주문을 받지 않습니다')
        break
```

<br/>

## finally

에러가 뜨더라도 무조건 finally 구문은 실행 하게 함.

```python
finally:
	print('')
```
