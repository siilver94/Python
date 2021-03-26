## **클래스**

<br/>

**클래스 정의 예제.**

`class '  ' :`

```python
class AttackUnit :
    def __init__(self,name, hp, damage):
        self.name = name
        self.hp = hp
        self.damage = damage

    def attack(self, location):
            print('{0} : {1} 방향으로 적군을 공격 합니다. [공격력 {2}]'\
                .format(self.name,location, self.damage ))

    def damaged(self, damage):
        print("{0} : {1} 데미지를 입었습니다.".format(self.name, damage))

        self.hp -= damage
        print("{0} : 현재 체력은 {1} 입니다.".format(self.name, self.hp))
        if self.hp <= 0 :
             print('뒤졌어')

firebat1 = AttackUnit('파이어뱃',50,16)
firebat1.attack('5시')
```

<br/>

### **메소드**

<br/>

**메서드 & 함수**

메서드는 [클래스 및 객체(object)](https://bskyvision.com/735)와 연관되어 있는 함수라는 것입니다. 
**클래스 내에 선언되어 있는 함수가 바로 메서드입니다**. 즉, 클래스 및 객체와 연관되어 있는 것이라면 메서드고, 그것들과 상관없이 독립적으로 존재하는 것은 함수입니다. 

**함수가 메서드보다 더 큰 개념**이라고 생각할 수 있습니다.

<br/>

### **상속**

상속 받을 클래스를 괄호() 안에 넣어주고

상속받을클래스.`__init__ ` 을 해주면 됨.

```python
class Unit:
    def __init__(self,name, hp):
        self.name = name
        self.hp = hp

class AttackUnit (Unit) :
    def __init__(self,name, hp, damage):
        Unit.__init__(self, name, hp)
        self.damage = damage
```

<br/>

### **다중상속**

```python
    def __init__(self, name, hp, damage):
        Unit.__init__(self, name, hp)
        self.damage = damage

    def attack(self, location):
            print('{0} : {1} 방향으로 적군을 공격 합니다. [공격력 {2}]'\

                .format(self.name,location, self.damage ))

    def damaged(self, damage):

        print("{0} : {1} 데미지를 입었습니다.".format(self.name, damage))
        self.hp -= damage
        print("{0} : 현재 체력은 {1} 입니다.".format(self.name, self.hp))
        if self.hp <= 0 :
             print('뒤졌어')

class Flyable :
    def __init__(self, flying_speed):
        self.flying_speed = flying_speed

    def fly(self, name, location):
        print('{0} : {1} 뱡향으로 날아갑니다. [속도 {2}]'\
            .format(name, location, self.flying_speed))

```
<br/>

다중상속은, 클래스 괄호안에 한개 이상을 만들고, 상속받을 부모를 __init__ 생성자로 정의합니다.

```python
class FlaybleAttackUnit(AttackUnit, Flyable):
    def __init__(self, name ,hp, damage, flying_speed):
        AttackUnit.__init__(self, name, hp, damage)
        Flyable.__init__(self, flying_speed)

valkyrie = FlaybleAttackUnit('발키리',200,6,5)
valkyrie.fly(valkyrie.name, '3시')
```

<br/>


### **오버로딩**

클래서의 상속 시 **부모 Class 에서 정의한 메소드를 자식 Class 에서 변경**하는 것 입니다.

부모 Class의 메소드 이름과 **기본적인 기능은 그대로** 사용하지만, 특정 기능을 바꿀 때 사용.

사용은 자식 Class에서 같은 이름의 메소드로 **재정의** 하면 됨.
