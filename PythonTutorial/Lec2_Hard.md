# 파이썬 기초 2강: 데이터 타입과 기본적인 연산들 (HARD)

## 1. 개요

본 강의자료는 [Lec2_Easy.md]()에 만족하지 못하신 분들을 위해서 제작한 자료입니다. 
자료형들에 대해서 좀 더 깊게 파고드는 시간을 가질 것입니다.

## 2. 변수 자료형

파이썬에서는 다음과 같은 변수 자료형들을 지원합니다.
- 숫자 자료형: **int**, **float**
- 참/거짓 자료형: **bool**
- 아무것도 없는(아닌) 것을 표현하는 자료형: **None**
- 문자열 자료형: **str**
- 컨테이너 자료형: **list**, **tuple**, **set**, **dict**, ...
- ... 이 이외에도 아주 많습니다!

이 단원에선 그 중 가장 많이 쓰이는 일부 자료형들을 배워보게 될 것입니다.

### int: 정수 (Integer)

    >>> a = 1
    >>> b = -10
    >>> c = 1+2+3+4+5
    >>> d = 9*7
    >>> e = 2**4
        
int는 정수를 나타내기 위해 고안한 자료형으로, 소수점 단위는 표현할 수 없는 자료형입니다.

파이썬은 정수의 기본적인 사칙연산 기능을 제공합니다. 밑은 예시입니다.

    >>> a = 7
    >>> b = 2
        
    >>> print(a+b) # 덧셈
    9
    
    >>> print(a-b) # 뺄셈
    5
        
    >>> print(a*b) # 곱셈
    14
        
    >>> print(a/b) # 나눗셈(완전)
    3.5
    
    >>> print(a//b) # 나눗셈(몫)
    3
    
    >>> print(a%b) # 나눗셈(나머지)
    1
    
    >>> print(a**b) # 지수 연산
    49
        
다음과 같이 정수를 0으로 나누려고 하면 오류가 일어납니다. 완전 나눗셈, 몫 나눗셈, 나머지 연산 모두 다 해당됩니다.

    >>> print(b%0) # b를 0으로 나눈 나머지를 구하는 것을 시도
    Traceback (most recent call last):
        File "<pyshell#12>", line 1, in <module>
            print(b%0)
    ZeroDivisionError: integer division or modulo by zero
        
        
### float: 실수 (Floating Point)

    >>> a = 1.0
    >>> b = -0.0097
    >>> c = 123456.7890123
    >>> d = 2.7 / 10.0
    >>> e = -1.29E20
        
float는 실수를 나타내기 위해 고안한 자료형으로, int하고는 다르게 소수점 부분도 표현이 가능한 자료형입니다.

단, 1/3과 같은 수들은 실제 컴퓨터 상에서 소수점으로 표현이 불가능하기 때문에, 
float 자료형에서 표현되는 실수는 실제 실수하고 비교했을 때 "오차"가 발생합니다.

실수를 표현하는 방법은 숫자 그대로를 쓰는 방식 말고 다른 방식이 있는데, 바로 지수 표현 방식을 사용하는 것입니다.

    >>> a = 1.2E20
    >>> print(a)
    1.2e+20
    
1.2E20(1.2e+20)의 값은 1.2 * 10^20 과 같습니다.

다음은 실수의 사칙연산에 대한 예시 코드입니다.
        
    >>> a = 7.0
    >>> b = 1.5
    
    >>> print(a+b) # 덧셈
    8.5
    
    >>> print(a-b) # 뺄셈
    5.5
    
    >>> print(a*b) # 곱셈
    10.5
    
    >>> print(a/b) # 나눗셈(완전)
    4.666666666666667
    
    >>> print(a//b) # 나눗셈(몫) -> 실수 나눗셈의 몫은 실수로 나옵니다.
    4.0
    
    >>> print(a%b) # 나눗셈(나머지)
    1.0
    
    >>> # 실수의 지수 연산을 지원하는 것은 아주 큰 메리트입니다.
    >>> print(a**b)
    18.520259177452132
        
정수와 마찬가지로, 실수 또한 0으로 나누려고 시도했을 때 오류가 일어납니다.

    >>> print(a/0.0) # a를 0.0으로 나누려고 시도
    Traceback (most recent call last):
        File "<pyshell#13>", line 1, in <module>
            print(a/0.0)
    ZeroDivisionError: float division by zero

정수와 실수 간의 사칙연산도 가능합니다. 이 경우, 정수의 값이 자동으로 실수로 변환되어 연산이 진행됩니다.
이를 Implicit Type Conversion(자동 형 변환)이라고 합니다.

    >>> a = 7
    >>> b = 1.5
    
    >>> print(a+b)
    8.5
    
    >>> print(a-b)
    5.5

### bool: 참/거짓 (Boolean)

    >>> a = True
    >>> b = False
    >>> c = not True
    >>> d = True or False
        
bool은 참/거짓을 나타내기 위해 고안한 자료형으로, 오직 ```True```와 ```False``` 2가지 값만 존재합니다.
bool에는 논리 연산이라는 것이 제공됩니다. 다음은 그 예시입니다.

    >>> a = True
    >>> b = False
    
    >>> print(a and b) # True and False = False
    False
    
    >>> print(a or b) # True or False = True
    True
    
    >>> print(not a) # not True = False
    False
    
    >>> print((not a) or b) # (not True) or False = False or False = False
    False

사칙연산에 bool 값을 사용할 경우, True는 1로, False는 0으로 자동 변환됩니다.

    >>> print(a*b) # a = True -> 1, b = False -> 0
    0
    
    >>> print(a+7) # a = True -> 1
    8
    
    >>> print(1.0 * b) # b = False -> 0
    0.0

### None: 아무것도 없음 (None)

    >>> a = None
    
None은 "아무것도 없음" 혹은 "아무것도 아님"을 표현하기 위해 고안한 자료형입니다.

숫자 0이랑은 다른 개념입니다. C++, Java의 null과 같은 개념입니다.

None으로 할 수 있는 연산은 거의 없습니다. print로 출력해도 이렇게 나옵니다.

    >>> print(a)
    None

### str: 문자열 (String)

    >>> a = "Hello, World!"
    >>> b = '안녕하세요, 탈잉입니다.'
    >>> c = "큰 따옴표 안에는 작은 따옴표('')를 넣을 수 있다!"
    >>> d = '그 반대로도("") 된다!'
    
str은 문자열을 나타내기 위해 고안한 자료형입니다.
큰 따옴표 또는 작은 따옴표를 이용하여 문자열 변수를 표현할 수 있습니다.

    >>> print(a)
    Hello, World!
    
    >>> print(b)
    안녕하세요, 탈잉입니다.
    
    >>> print(c)
    큰 따옴표 안에는 작은 따옴표('')를 넣을 수 있다!
    
    >>> print(d)
    그 반대로도("") 된다!
        
다음과 같이 한번에 따옴표를 3개씩 사용하면 여러 줄에 걸쳐서 문자열 변수를 생성할 수 있습니다.
이러한 특징 때문에 여러 줄에 걸쳐서 주석을 사용하는 것에 3개짜리 따옴표가 쓰이기도 합니다.
    
    >>> e = """1번째 줄
    2번째 줄
    3번째 줄
    4번째 줄"""
        
    >>> e
    '1번째 줄\n2번째 줄\n3번째 줄\n4번째 줄'
        
    >>> print(e)
    1번째 줄
    2번째 줄
    3번째 줄
    4번째 줄
        
여기서 print 함수로 출력하는 거랑 그냥 출력하는 것의 명확한 차이를 알 수 있습니다!
- print 함수로 출력하는 건 대화형 인터프리터 뿐만 아니라 일반 파이썬 에디터에서도 작동하지만, 
그냥 출력하는 건 대화형 인터프리터에 대해서만 작동합니다.
- print 함수에서는 newline(엔터키 치면 다음줄로 넘어가는 그거) 같은 특수문자열이 자연스럽게 표시가 되지만,
그냥 출력할 때는 ```\n``` 같은 식으로 출력이 됩니다. 
- print 함수로 문자열을 출력하면 맨 앞뒤에 ```'``` 가 붙지 않지만, 그냥 출력하면 ```'```가 붙습니다.

### list: 여러 변수들의 순차적 목록 (List)

    >>> a = [1, 2, 3]
    >>> b = [1.0, True, "Hello"]
    >>> c = [-0.9, [1, 2, False],  None]
    
list는 변수들의 목록을 나타내기 위해 고안한 자료형들 중 하나입니다. 
list는 여러 개의 변수들을 한번에 묶어서 표현할 수 있습니다.

    >>> print(a)
    [1, 2, 3]
    
    >>> print(b)
    [1.0, True, 'Hello']
        
다음과 같이 리스트의 특정 위치의 원소만을 뽑아올 수 있습니다. 이걸 *indexing*이라고 합니다.
대괄호를 이용해서 뽑아올 수 있으며, 맨 앞자리부터 0번째 원소입니다. 
    
    >>> print(b[0])
    1.0
    
    >>> print(b[1])
    True
    
    >>> print(b[2])
    Hello
    
대괄호 안에 음수를 넣음으로써 뒤에서부터 원소를 뽑아낼 수 있습니다.

    >>> print(a[-1])
    3

다음과 같은 식으로 몇번째 원소부터 몇번째 원소까지의 리스트도 뽑아내는 것이 가능합니다.
```a[x:y]```는 ```[a[x], a[x+1], a[x+2], ..., a[y-1]]```과 동일합니다.

    >>> print(a[0:2])
    [1, 2]

심지어 간격도 설정 가능합니다! 
```a[x:y:z]```는 ```[a[x], a[x+z], a[x+2*z], ..., (y번째 원소 전까지)]```와 동일합니다.
    
    >>> d = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j"]
    
    >>> print(d[0:5:1])
    ['a', 'b', 'c', 'd', 'e']
    
    >>> print(d[1:7:2])
    ['b', 'd', 'f']
    
    >>> print(d[4:6:0]) # 간격이 0이면 오류가 일어납니다.
    Traceback (most recent call last):
        File "<pyshell#10>", line 1, in <module>
            d[1:7:0]
    ValueError: slice step cannot be zero
        

c의 경우처럼 리스트 안에 리스트도 얼마든지 넣을 수 있습니다. 

    >>> print(c)
    [-0.9, [1, 2, False], None]

    >>> print(c[0])
    [1, 2, False]

리스트의 서브리스트의 원소를 액세스하고 싶다면 다음과 같이 대괄호를 2번 쓰시면 됩니다.
    
    >>> print(c[1][2])
    False
        
다음과 같이 리스트의 끝에 원하는 것을 추가시킬 수도 있습니다.

    >>> a.append(-1)
    >>> print(a)
    [1, 2, 3, -1]
    
    >>> a.append([9, 8, 7])
    >>> print(a)
    [1, 2, 3, -1, [9, 8, 7]]
        
리스트의 끝에 있는 원소를 제거할 수도 있습니다.

    >>> a.pop()
    [9, 8, 7]
    
    >>> print(a)
    [1, 2, 3, -1]
    
    >>> a.pop()
    -1
    
    >>> print(a)
    [1, 2, 3]
        
리스트끼리 더해서 합칠 수도 있습니다.

    >>> a + [3, 4, 5]
    [1, 2, 3, 3, 4, 5]

### tuple: 여러 변수들의 "변경 불가능한" 순차적 목록 (Tuple)

    >>> a = (1, 2, 3)
    >>> b = (1.0, True, "Hello")
    >>> c = (-0.9, (1, 2, False), None)

### 이번 강좌에서 생략하는 기본 제공 자료형들

- **complex**: 복소수를 나타내기 위해 필요한 자료형입니다. 복소수를 쓸 일이 별로 많지 않기에, 본 강의에선 생략합니다.
    
        >>> a = 1 + 2j
        >>> b = 3 - 1j
        
        >>> print(a+b)
        (4+1j)
        
        >>> print(a-b)
        (-2+3j)
        
        >>> print(a*b)
        (5+5j)
        
        >>> print(a/b)
        (0.1+0.7000000000000001j)
        
        >>> print(a**b)
        (-27.43638199160605+19.789310365010714j)

- **frozenset**: set과 유사하지만, 원소를 추가하거나 제거할 수 없다는 특징이 있습니다.
frozenset과 set의 관계는 tuple과 list의 관계와 유사합니다. 본 강의에선 생략합니다.

        >>> a = frozenset([1, 2, 3])
        >>> print(a)
        frozenset({1, 2, 3})
        
        >>> print(a.union({4, 5}))
        frozenset({1, 2, 3, 4, 5})

- **range**: 특정 영역의 정수들을 표현하는 데에 사용됩니다. 강의 초반부(Lec3.md)에서 배우게 됩니다.

        >>> print(list(range(4))
        [0, 1, 2, 3]
        
        >>> for i in range(5, 10, 2):
        ...     print(i)
        5
        7
        9

- **function**: 함수를 나타냅니다. 강의 중반부(Lec4.md)에서 자세히 배우게 됩니다.

        >>> def f(x):
        ...    if x>0:
        ...        return x*x
        ...    else:
        ...        return -x*x
        
        >>> print(f(2))
        4
        
        >>> print(f(-2))
        -4

- **object**: 파이썬의 모든 변수 자료형의 기본이 되는 자료형입니다. 
강의 중반부(Lec5.md)에서 클래스 상속과 함께 배우게 됩니다.

        >>> a = object()
        >>> print(a)
        <object object at 0x0000021BFFAEC340>

- **generator**: Iterator의 일종입니다. 파이썬이 아주 매력적인 이유 중 하나가 바로 이겁니다.
지금 이해하기엔 어렵습니다. 강의 후반부(Lec7.md)에서 자세히 배우게 됩니다.

        >>> a = (i*i for i in range(1, 6))
        >>> for num in a:
        ...     print(num)
        1
        4
        9
        16
        25

- **file**: 파일(*.txt*, *.csv* 등)을 나타내는 자료형입니다. 강의 후반부(Lec8.md)에서 배우게 됩니다.

        >>> # 실제 test.txt 파일 내부를 확인해보세요.
        >>> with open("test.txt", "w") as testfile:
        ...    testfile.write("Test writing")

- **Exception**, **StopIteration**, **ArithmeticError** 등등: 에러를 커버하는데 쓰이는 자료형입니다. 
강의 후반부(Lec9.md)에서 자세히 배우게 됩니다.

        >>> a = Exception("Test Exception")
        >>> raise a
        Traceback (most recent call last):
            File "<pyshell#15>", line 1, in <module>
                raise a
        Exception: Test Exception

- **bytes**, **bytearray**, **memoryview**: Binary Data(바이너리 데이터) 관련 자료형입니다. 본 강의에선 생략합니다.
    
        >>> a = bytes("Hello, World", "utf-8")
        >>> print(a)
        b'Hello World'

        >>> b = bytearray([1, 2, 3])
        >>> print(b)
        bytearray(b'\x01\x02\x03')

        >>> c = memoryview(a)
        >>> print(c)
        <memory at 0x000002301EFD2F48>

- 이 외에도 **builtins**, **filter**, **property**, **slice**, **super**, **zip** 등이 있지만, 넘어가겠습니다!