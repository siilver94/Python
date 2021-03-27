# 유용한 함수들.


<br/>

---

### csv처럼 만들기

`sep` 함수를 통해 인자 사이를 **콤마','** 로 구분하여 **csv** 형태로 만들 수 있다.

```python
print('python','java',sep = ',')
```
`python,java`

<br/>

---

### **왼쪽, 오른쪽 정렬**

- `.ljust()` 는 왼쪽으로 정렬.

- `.rjust()` 는 오른쪽 정렬.

```python
scores = {'수학':0,'영어':50,'코딩':100}

for subject, socore in scores.items():
    print(subject.ljust(8), str(socore).rjust(4), sep = ":")
```

`수학      :   0영어      :  50코딩      : 100`

<br/>

---

### **zfille() 빈공간 0으로 채우기**

**zero fill** 말그대로 함수 안 매개변수의 숫자만큼 공간을 확보하고 값이 없으면 0으로 채움.

```python
for num in range(1,21):
    print('대기번호 : '+str(num).zfill(3))
```

`대기번호 : 001대기번호 : 002대기번호 : 003대기번호 : 004대기번호 : 005대기번호 : 006대기번호 : 007대기번호 : 008대기번호 : 009대기번호 : 010대기번호 : 011대기번호 : 012`
