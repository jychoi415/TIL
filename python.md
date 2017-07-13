# Python
**_Life is too short, You need Python._**  

1990년 귀도 반 로썸(Guido Van Rossum)이 개발한 인터프리터 언어  
현재 _Google_, _Dropbox_ 등 에서 많이 사용 중인 언어로 다양한 분야에서 쓰이고 있음  
시스템 프로그래밍, 하드웨어 제어 등 매우 복잡하고 반복 연산이 많은 프로그램은 파이썬에 적합하지 않음  
⇒ 다른 언어로 만든 프로그램은 파이썬 프로그램에 포함시켜 실행 가능함으로 약점 극복

### 특징
+ __디자인 철학__  
  > Beautiful is better than ugly.  
  > Explicit is better than implicit.  
  > Simple is better than complex.  
  > Complex is better than complicated.  

  위 철학들을 만족시키는 __단 하나의 스타일__ 로 수렴 진화
+ __인터프리터 언어__  
  Python은 한 줄씩 소스 코드를 해석하여 그 때마다 실행해 결과를 바로 확인할 수 있는 언어임
+ __언어 구현__  
  + __CPython__  
    보통 말하는 C언어로 구현되어 있음.
  + __IronPython__  
    C#으로 구현된 닷넷프레임워크 위에서 동작
  + __Stackless Python__  
    CPython에서 C 스택 없앰
  + __Jython__  
    Java로 구현되어 JVM 위에 돌아감
  + __PyPy (=RPython)__  
    Python 자체로만 구현  

  오리지널은 _CPython_ 임

### 활용
+ __파이썬으로 할 수 있는 일__  
  + __시스템 유틸리티 제작__  
    운영체제의 시스템 명령어를 이용할 수 있는 도구들을 갖추어 여러 시스템 유틸리티를 만드는데 유리
  + __GUI 프로그래밍__  
    Python 설치 시 함께 설치되는 기본 모듈인 Tkinter를 사용해 간단하게 창을 띄울 수 있음  
    Tkinter 외에 wxPython, PyQT, PyGTK 등이 있음  
  + __C/C++와의 결합__  
    C나 C++로 만든 프로그램을 Python에서 사용할 수 있으며 그 반대도 가능  
  + __웹 프로그래밍__  
    Python 웹 프레임워크인 _Django_ 나 _Flask_ 로 웹 프로그램을 간단히 제작 가능  
  + __수치 연산 프로그래밍__  
    Python은 복잡하고 반복적인 연산에 적합하지 않은 언어지만 _Numeric Python_ 이라는 수치 연산 모듈을 제공  
    이 모듈은 C로 구현되어 Python에서도 수치 연산을 빠르게 할 수 있음
  + __데이터베이스 프로그래밍__  
    Sybase, Infomix, Orcle, MySQL, PostgreSQL 등의 데이터베이스에 접근 가능한 도구 제공  
    _Pickle_ 이라는 모듈은 Python에서 사용되는 자료들을 변형없이 그대로 파일에 저장하고 불어옴  
  + __데이터 분석__  
    _Pandas_ 모듈을 사용하면 데이터 분석을 더 쉽고 효과적으로 가능  
    아직 데이터 분석에 특화된 _R_ 언어를 많이 사용하지만 Pandas 등장 이후 Python 이용 경우가 점차 증가  
  + __사물인터넷__  
    _Raspberry Pi3_ 는 홈시어터나 작은 게임기 등으로 만들 수 있는데 Python은 Raspberry Pi3를 제어하는 여러 언어 중 하나임
  + __인공지능__  
    _Tensorflow_ 는 머신러닝과 딥러닝을 위해 구글에서 만든 오픈소스 라이브러리임  

### 문법
파이썬에는 두 가지 다른 시퀀스 구조가 있음. __튜플__ 과 __리스트__ 임.  
각 요소는 어떤 객체도 가능함.  
단 하나의 스타일로 수렴 진화하는 파이썬이 리스트와 튜플 모두 포함하는 이유  
⇒ 튜플은 불변 _(immtable)_ 하고 리스트는 변경 가능 _(mutable)_ 함.
+ __리스트__  
  리스트는 데이터를 순차적으로 파악하는데 유용.  
  ⇒ 특히 내용의 순서가 바뀔 수 있다는 점에서 유용.  
  리스트의 현재 위치에 새로운 요소 추가, 삭제 혹은 기존 요소를 덮어 쓸 수 있음.  
  리스트에는 동일한 값이 여러 번 나타날 수 있음.
  ```
  a = []
  b = [1,2,3]
  c = ['life','is','life']
  d = [1,2,['life','is']]
  ```
  비어있는 리스트는 `a = list()`로 생성  
  + __슬라이싱__  
    슬라이스로 리스트의 서브시퀀스 추출 가능.  
    ```
    list = ['apple','banana','lemon']
    list[0:2]
    # ['apple','banana']
    ```
    슬라이스에 __스탭__ 사용 가능.
    ```
    list[::2]
    # ['apple','lemon']

    list[::-1]
    # ['lemon','banana','apple']
    ```
  + __항목 추가__  
    리스트는 변경 가능하기 때문에 `append()`로 새 항목을 추가할 수 있다.
    ```
    list.append('grape')
    list
    # ['apple','banana','lemon', 'grape']
    ```
+ __셋__  
  요소들이 순서 상관없이 유일한 값으로 유지되어야 한다면 리스트보다 셋을 사용하는 게 유용.
+ __튜플__  

+ __딕셔너리__  

### QnA
+ __Python 2.x VS Python 3.x__  
Python 3.x에서 모든 변수가 __객체__ 로 처리됨  

|| Python 2.x | Python 3.x |
|----|----|----|
| __print문__ | print 'hello' / print( 'hello' ) | print( 'hello' ) |
| __int 나누기__ | print( 1/2 )  _# 0_ | print( 1/2 ) _# 0.5_ |
| __long 자료형__ | print( type(2**100) )  _#<type 'long'>_ | print( type(2**100) ) _#<class 'int'>_ |

+ __Python은 쉬운 언어일가?__  

___
#### 참조
[점프 투 파이썬 Wikidocs](https://wikidocs.net/book/1)
[Python 언어 구현](http://python-guide-kr.readthedocs.io/ko/latest/starting/which-python.html)  
[도서]처음 시작하는 파이썬(빌 루바노닉 저_한빛미디어 출판)
