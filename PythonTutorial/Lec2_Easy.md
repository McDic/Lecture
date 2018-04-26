# 파이썬 기초 2강: 데이터 타입과 기본적인 연산들 (EASY)

## 1. 변수란?

    >>> message = "Hello, World!"
    >>> print(message)
    Hello, World!

파이썬(뿐만 아니라 모든 프로그래밍 상황에서)에서 변수는 기초 중의 기초이자 가장 중요한 요소입니다.
변수는 어떠한 값을 저장하거나, 변경하거나, 또는 연산하는 용도로 쓰입니다.

파이썬에서 변수를 만들고 관리하는 방법은 아주 간단합니다. 다음은 1이라는 값을 가진 변수를 만들어내는 방법입니다.

    >>> a = 1
    
간단하죠? 2를 넣고 싶다면 ```a = 2```, 0을 넣고 싶다면 ```a = 0``` 이런 식으로 하면 됩니다.

본 강의자료에서는 자료형들을 아주 간단하게 다뤄볼 예정입니다! 
좀 더 깊게 들어가고 싶으시다면 [Lec2_Hard.md]()를 참고해주세요.

## 2. 수 (Numeric) 자료형

    >>> a = 10
    >>> b = 2.7
    >>> c = 1.0e7 # 지수 표기법
    >>> d = -0.9
    >>> e = a + 1 # e의 값은 11이 됩니다.
    
공학용 계산기에 수식 집어넣듯이 숫자 쓰시면 됩니다

다음과 같이 수에 대한 사칙연산을 진행할 수가 있습니다.
        
    >>> a+b # 덧셈
    12.7
        
    >>> a-b # 뺄셈
    7.3
        
    >>> a*b # 곱셈
    27
    
    >>> a/b # 나눗셈 (완전)
    3.7037037037037033
        
    >> a//b # 나눗셈 (몫)
    3.0
        
    >> a%b # 나눗셈 (나머지)
    1.8999999999999995
        
    >> a**b # 지수 연산
    501.18723362727246
        
## 3. 참/거짓 (Boolean) 자료형

    >>> a = True
    >>> b = False
    
파이썬에서는 참, 거짓을 다룰 수 있습니다. 또, 다음과 같은 코드로 논리연산을 할 수도 있습니다.

    >> a and b # AND 연산
    False
        
    >> a or b # OR 연산
    True
        
    >> not a # NOT 연산
    False
        
이런 식으로 값이 오직 참, 거짓만 존재하는 체계를 *Boolean Logic(Algebra)* 라고 표현합니다. 
다음은 기본 3가지 연산(and, or, not)에 대한 논리 표입니다.

A    | B    | A and B | A or B
---- | ---- | ------- | -------
True | True | True | True
True | False | False | True
False | True | False | True
False | False | False | False

A   | not A
--- | -----
True | False
False | True

## 4. 문자열 (Sring) 자료형

    >>> a = 'Hi, my name is McDic.'
    
파이썬에서는 문자열 자료형을 이용하여 문장을 다룹니다.
파이썬에서 문자열 변수를 다루는 것은 C나 Java 등에 비해 정말 쉽습니다!

다음과 같이 문자열을 이용한 여러 연산을 할 수 있습니다.

    >>> a
    'Hi, my name is McDic.'
        
    >>> print(a) # 그냥 출력하는 것과 print로 출력하는 것은 다르다.
    Hi, my name is McDic.
        
    >>> a + ' What is your name?' # 문자열 합치기
    'Hi, my name is McDic. What is your name?'
        
    >>> a.split(' ') # 특정 문자열로 나누기
    ['Hi,', 'my', 'name', 'is', 'McDic.']
        
    >>> a.endswith('McDic.') # 특정 문자열로 끝나는가?
    True
        
    >>> a.upper() # 소문자로 바뀐 문자열
    'HI, MY NAME IS MCDIC.'
        
    >>> a.lower() # 대문자로 바뀐 문자열
    'hi, my name is mcdic.'
         
    >>> a.count("m") # 부분문자열 개수 세기
    2
        
    >>> a.replace("my", "your") # 문자열 교체하기
    'Hi, your name is McDic.'
    


## 5. 컨테이너 (Container) 자료형

    >>> a = [5, 9, -1, 2.34, False]
    >>> b = (5, 9, -1, 2.34, False)
    >>> c = {5, 9, -1, 2.34, False}
    
