---
title:  "Python 기초 문법"
excerpt: "python 기초 문법 정리 내용 "

categories:
  - python
tags:
  - python

toc: true
toc_sticky: true
 
date: 2022-06-08
last_modified_at: 2022-06-08
---


# Python

종류: 강의, 헷갈리는 개념정리
학문 분야: Python

# 데이터타입

- **Python 문자열**
    - 중간에 작은 따옴표가 존재하는 문자열을 표현할 때는 큰 따옴표로 문자열을 정의
    
    ```python
    print('작은 따옴"표도 가능')
    print("작은 따옴'표도 가능")
    print("작은 따옴"표도 가능") ## 큰 따옴표로 묶인 상태에서 "는 출력 x
    print('작은 따옴'표도 가능') ## 작은 따옴표로 묶인 상태에서 '는 출력 x
    
    1. 작은 따옴"표도 가능 
    2. 작은 따옴'표도 가능
    ```
    
    ```python
    print ( "총 평가 금액 :" ,77300*3 + 292000*4 + 38350*4,"원")
    -> 문자열 연결은 ,(콤마)를 사용하여 연결 
    총 평가 금액 : 1553300 원
    ```
    

## **인덱싱**

→ 문자열에서 데이터를 하나 가져오는 것.

**→ 각 문자에 인덱스 번호가 부여.**

Ex) C[0] Y[1] S[2]

Ex) a= [ [1,2,3] , [4,5,6] ] → a[0][0] =1

## **슬라이싱**

→ 문자열에서 하나 이상의 데이터를 가져오는 것.

**→ 인덱싱과 달리 문자 사이에 인덱스가 위치**

Ex) [0] C [1] Y [2] S [3]

```python
string = "hello yoonseok"
print( string [0:5])  # 0~5까지의 인덱스값을 슬라이싱 할 수 있다. /구간 지정
print( string [:5])   # 0 생략 가능
print( string [:])    # 전체 인덱스 값 슬라이싱
print( string[:][:][:][:] ) # string [:] = string이므로 결과적으로 string[:] 한번만 실행됌
print( string[:][:][:][0] ) # string[0] = h

hello
hello
hello yoonseok
hello yoonseok
h
```

## **문자열 수정**

- 한번 생성된 문자열은 수정 불가
    
    ```python
    string[0]= 'H’ # 와 같이 재할당시 오류 발생
    ```
    
- 새롭게 하나의 문자열을 정의해야함
    
    ```python
    "H" + string[1:]
    print (string )
    
    Hello yoonseok
    ```
    

## **문자열 Formatting**

- f " {변수명} “ ← 기본 Fomatting 형식
    
    ```python
    용돈 = 3000
    print(용돈,"원")
    print(str(용돈)+"원")
    # formattiong을 사용하면 위와 같은 수고를 덜 수 있으며
    #추가적인 option 기능 사용 가능
    print(f"{용돈}원")
    print(f"{용돈:,}원") # f{a:,} <- :, option
    print(f"{용돈:.1f}원") #실수형 변환가능
    
    3000 원
    3000원
    3000원
    3,000원
    3000.0원
    ```
    

# 리스트

- **순서가 있는 자료구조**
    - 사이사이에 추가 가능

## **Append**

- 리스트에 끝 부분부터 값을 추가하는 메서드
    
    ```python
    Ys = [10,20]
    Ys.append(30) # 리스트 끝 값에 추가
    print(Ys)
    [10, 20, 30]
    
    #################################
    
    Ys = [10,20]
    Ys.append(0,30) # 
    print(Ys)
    
    TypeError: append() takes exactly one argument (2 given)
    append는 한번에 하나의 객체 값만 추가 가능
    
    ##############################
    Ys = [10,20]
    Ys.append([50,40]) # 리스트로 묶어서 하나의 리스트에 여러 값 추가 가능
    print(Ys)
    
    [10, 20, [50, 40]]
    ```
    

## **Insert**

- 특정위치에 값을 추가하는 메서드

```python
Ys = [10,20]
Ys.append(30) # 리스트 끝 값에 추가

Ys.insert(0,40) # 0번째 리스트에 40 추가
Ys
print(Ys)

[40, 10, 20, 30]

```

- **Extend**
    - 추후 추가 예정
    

## **리스트 인덱싱 & 슬라이싱**

```python
interest = ["삼성전자", "LG전자", "카카오"]

interest[ 1 ] 
# 1번째 데이터를 **인덱싱**
LG전자

interest[ 0 ]
#2번째 리스트 값으로 수정 가능
삼성전자

interest[0][0:2]
# 리스트의 0번째 값을 불러온 뒤 / [:2] 문자열을 **슬라이싱** **0 삼 1 성 2** 전 3 ..
삼성 

```

### **Remove, Pop, Del, Clear**

```python
Ys= [10,20,30,40]
Ys.remove(40)
# 리스트에서 40의 값을 삭제

Ys.pop(0)
# 0번째 리스트에 있는 값을 가져온 뒤 삭제

del Ys[0]
# 0번째 리스트에 있는 값을 삭제

Ys.**clear()**
# 리스트의 모든 값을 삭제  / clear() 괄호 필요
```

### **Index**

```python
Ys = [10,20]
Ys.index(20) # index메서드를 통해 20이라는 값의 위치를 찾을 수 있다
-> 1 # 리스트의 1번재 값
```

### **Sort , Reverse**

```python
Ys =[20,10,30]
Ys.**sort()** # 10,20,30
Ys.**reverse()** # 30,20,10 / sort,reverse () 괄호필요
```

### **Count**

```python
Ys =[20,10,30,10]
Ys.count(10) # 리스트에 들어있는 10의 개수를 세준다.
```

### **Join**

```python
Ys =["a","b","c"]
**'_'.**join(Ys)
a_b_c

Ys =["a","b","c"]
**'1'**.join(Ys)
a1b1c1

**# 구분자를 기준으로 리스트안의 문자열 데이터를 연결
'_'. -< 구분자**
```

# 딕셔너리

- `**key`와 `value`값을 쌍으로 저장가능 한 자료구조**

```python
**# 딕셔너리 예시**
wallet = {
    'card':'SK카드',
    'cash':75000,
    'coin':{'500원':1,
            '100원':1,},
    'id':['주민등록증', '여권'],
    'licence':'운전면허증'
}

**# 딕셔너리 in 딕셔너리 접근**
wallet['coin']['500원']
-> 1

**# 딕셔너리 편집( 딕셔너리 in 딕셔너리 값도 변경가능!)
# cash의 내용을 수정한다고 할 때**
wallet['cash'] = 65000

**#딕셔너리 추가**
wallet['id'].append('yoon')

**#딕셔너리 삭제
del** wallet['licence'] # 딕셔너리의 항목 제거
wallet.clear()        # 딕셔너리 원소 전체 제거
del wallet            # 딕셔너리 변수 완전 제거
```

---

# 분기문

## **Boolean**

| 비교 연산자 | 의미 |
| --- | --- |
| == | 같다 |
| ! = | 다르다 |
| > | 크다 |
| < | 작다 |
| ≥ | 크거나 같다 |
| ≤ | 작거나 같다 |

## 조건문

### IF문

```python
If 조건 : 
	print("출력")
#기본적인 틀, 들여쓰기 꼭 필요! , 조건이 참일때 실행된다.
```

### IF-ELSE문

```python
If 조건 :
 ...
else : 
#조건이 참일 경우 if문이 실행되며, 그렇지 않을 경우 else문이 실행된다.
```

### IF-ELIEF-ELSE문

```python
if 조건-1 :   # 첫번째 조건이 참이라면 밑에 조건 발동x

elif 조건-2 : # 첫번째 조건이 거짓이고 해당 조건이 참이면 밑에 조건발동x)  

elif 조건-3 : # 첫째,둘째 조건이 거짓이고, 해당 조건이 참일 때 발동 밑에 조건발동x 
 . . . . . . .  
else :   #위에 조건 모두 해당 안될 경우

#조건이 3개 이상일 때 사용.
```

# 반복문

## For

```python
For 변수(반복자) in 자료구조(반복범위) : #기본 구조
#자료구조의 데이터수 만큼 코드를 반복 실행한다.

Ys=[1,2,3,4]
for i in Ys: # Ys에 있는 값을 i에 바인딩 (가리킴)
	print(i)

# Ys에서 1,2,3,4를 하나씩 가져와서 출력! ( 하나씩 빼서 반복 )
```

```python
for i in range(0,5) :
	print(i)
0
1
2
3
4
```

## enumerate

```python
**# enumerate 함수는 인자의 값을 추출 할 때 인덱스를 추출하는 기법이다**
test = [ 1,2,3,4,5]
for index, item in enumerate(test):
    print(index, item)
0 1
1 2
2 3
3 4
4 5

**# index 지정이 안 되어 있을 경우
#튜플형태로 반환한다.**
test = [ 1,2,3,4,5]
for item in enumerate(test):
    print(item)
(0, 1)
(1, 2)
(2, 3)
(3, 4)
(4, 5)

```

## While

- **`while` `조건식` `:`** # 조건식이 참이라면
    
    실행코드 # 코드가 무한반복 실행 
    
- break문으로 종료

# 함수

## **함수의 정의 & 호출**

```python
def Ys ():
	print("Yoonseok") # Ys()라는 함수 정의

Ys() # Ys() 함수 호출

```

### **Return 유무에 따른 반환 값**

![질문.PNG](/assets/images/posts/2022-06-08/질문.png)

### 함수 정의 시, 변수 선언

```python
def 함수이름(변수): # 변수는 int,str,list등이 올 수 있다. 


함수이름("YS") # Ys -> parameter or argument

Ex)

def ys(x) :
	return x + "시"

print ( ys("고양") ) 
print ( ys("파주") )

고양시
파주시

---------------------------------------------
def ys(x) :
	print( x + "시" ) 

print ( ys("고양") ) # print 없이 colab에서 실행시에는 None 안 보임
print ( ys("파주") ) #함수에서 return값없이 출력할시 None 출력 됌

고양시
None
파주시
None
```

# 클래스

- **변수와 함수를 묶어서 하나의 객체를 만드는 것**

```python
class EPL : 
	def MNU (입력) :
			return 출력

	def MCI (입력) :
			return 출력

	def LIV (입력) :
			return 출력

# EPL이라는 클래스를 생성하고 구단 이름의 함수를 생성하여 카테고리화 !
----------------------------------------------------------------------------
#Self?
class EPL : 
	def MNU (self,인자,인자,...) :
			return 출력

#self는 객체 자기자신을 참조하는 매개변수
```

## **Self**

- **self는 객체 자기자신을 참조하는 매개변수**
- **객체가 생성되기 전에 미리 이름을 할당 해줄 순 없기에 self라고 표기**

```python
class EPL : 
	def MNU (self) :
			return "맨유"

	def MCI (self) :
			return "맨시티"

	def LIV (self) :
			return "리버풀"

구단 = EPL()     # EPL()클래스를 받는 구단이라는 객체 설정.

x= EPL.MNU(구단) # EPL클래스 안에 있는 MNU함수를 끌어온 값을 x에 지정
# x= 구단.MNU() <-와 같이 사용가능
y= EPL.MCI(구단) # ''
z= EPL.LIV(구단) # ''

print(x)
print(y)
print(z)

맨유
맨시티
리버풀
```

## **인스턴스 변수**

```python
class EPL : # 클래스 선언
	def MNU (self,name,point) : # 객체에서 받을 self,name,point 
			self.name = name
			self.point = point   #객체로 부터 받은 값, 바인딩

	def MCI (self,name,point) :
			self.name = name
			self.point =point

	def LIV (self,name,point) :
			self.name = name
			self.point = point

구단 = EPL()        # 구단이라는 객체 생성 
구단.MNU("맨유",30)  # 객체에서 MNU함수를 불러온 뒤 name,point값 입력

print(구단.name)
print(구단.point)

맨유
30
```

## 초기화자(*init*)

```python
class EPL : # 클래스 선언
	def __init__(self,name,point) : # 초기화 & 생성자 함수, 
			self.name = name						# 함수를 여러 개 만들어서 할당하지 않고, init으로 간단하게 생성
			self.point = point   

a = EPL("맨유",30)    						# EPL클래스를 불러와 name,point값을 넣어주고 a에 바인딩
b = EPL("리버풀",50)

print(a.name)										  # a에서 name 변수만 불러와서 출력
print(b.name)

맨유
리버풀
```

-

