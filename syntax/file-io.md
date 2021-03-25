## **파일 입출력**


<br/>

### **파일 생성 후 입력**

<br/>

#### score_file 이란 txt파일을 만들어서 넣기



```python
score_file = open("score.txt","w",encoding="utf8")
print('수학 : 0', file = score_file)
print('영어 : 50', file = score_file)

score_file.close()
```

- 한글 문자를 입력 할 때는 `encoding-"utf8"` 넣어주기.
- 파일을 열었으면 항상 `close()` 해주기.
- **'w'** 는 쓰기(write) 용도란 뜻.

<br/>

### **있던 파일에 추가 입력**



```python
score_file = open("score.txt", "a", encoding = "utf8")
score_file.write("과학 : 80")
score_file.write("\n코딩 : 100")
score_file.close()
```

`a` 는 **append** 의 약자로, 원래 있던 것에 추가.

<br/>

### **파일 읽기 read()**

```python
score_file = open("score.txt", "r", encoding = "utf8")
print(score_file.read())
score_file.close()
```

<br/>

### **파일 줄 별로 읽기 realine()**

```python
score_file = open("score.txt", "r", encoding = "utf8")
print(score_file.readline())
print(score_file.readline())
print(score_file.readline())
print(score_file.readline())
score_file.close()
```

<br/>

### **파일 전체 내용 읽기 while**

```python
score_file = open("score.txt", "r", encoding = "utf8")

while True :
    line = score_file.readline()
    if not line:
        break
    print(line)

score_file.close()
```

#### 파일 전체 내용 읽기2

```python
score_file = open("score.txt", "r", encoding = "utf8")

lines = score_file.readlines()

for line in lines:
    print(line, en\d="")
```

<br/>

### **pickle**

텍스트 상태의 데이터가 아닌 파이썬 **객체 자체를 파일로 저장**하는 것.

pickle 모듈을 활용해 그 객체 자체를 바이너리로 저장하는 것.

`pickle.dump(객체, 파일)` 로 저장하고.

`pickle.load(파일)` 로 로딩.


```python
import pickle
my_list = ['a','b','c']

## Save pickle
with open("data.pickle","wb") as fw:
    pickle.dump(my_list, fw)

## Load pickle
with open("data.pickle","rb") as fr:
    data = pickle.load(fr)
print(data)
#['a', 'b', 'c']
```

#### 1~ 50주차까지 보소서 파일 만드는 프로그램.

```python
for i in range(1,51) :
    with open('{0} 주차.txt'.format(i),'w',encoding='utf8') as profile_file:
        profile_file.write('''
        - {0} 주차 주간 보고 -
        부서 :
        이름 :
        업무 요약 :'''.format(i))

```
