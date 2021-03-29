## **함수**

<br/>

```python
def open_account():

  print("새로운 계좌가 생성되었습니다.")

open_account()
```

<br/>

### **함수 기본값 설정 예제**


<br/>

```python
def profile(name,age=17,main_lang='파이썬') :
    print('이름은 {0}\t나이 : {1}\t주사용 언어:{2}'.format(name,age,main_lang))

profile("유재성")
profile("김태호")
```

<br/>

### **가변인자**

인자값이 일정하지 않을때 *language 처럼 해두면 된다

```python
def profile(name, age, *language):
    print('이름 : {0}   나이 : {1}'.format(name,age),end=" ")
    for lang in language:
        print(lang, end=" ")
    print()

profile('유재석',20,'python','java','c','c++','c#')

```

<br/>

---


## 파이썬 내장함수

파이썬 사이트 참조

[Built-in Functions - Python 3.9.2 documentation](https://docs.python.org/3/library/functions.html)


<br/>


## 파이썬 외장함수

파이썬 사이트 참조

[Python Module Index](https://docs.python.org/3/py-modindex.html)


