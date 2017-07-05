# Python
**_Life is too short, You need Python._**  

1990년 귀도 반 로썸(Guido Van Rossum)이 개발한 인터프리터 언어[^1]
현재 _Google_, _Dropbox_ 등 에서 많이 사용 중인 언어로 다양한 분야에서 쓰이고 있음  
시스템 프로그래밍, 하드웨어 제어 등 매우 복잡하고 반복 연산이 많은 프로그램은 파이썬에 적합하지 않음  
⇒ 다른 언어로 만든 프로그램은 파이썬 프로그램에 포함시켜 실행 가능함으로 약점 극복

### 특징
* __언어 구현__  
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

  오리지널은 _CPython_ 임 [참고](http://python-guide-kr.readthedocs.io/ko/latest/starting/which-python.html)
* __디자인 철학__  
  > Beautiful is better than ugly.  
  > Explicit is better than implicit.  
  > Simple is better than complex.  
  > Complex is better than complicated.  

  위 철학들을 만족시키는 단 하나의 스타일로 수렴 진화

### 활용
* __파이썬으로 할 수 있는 일__  
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

### QnA
* __Python 2.x VS Python 3.x__  
Python 3.x에서 모든 변수가 __객체__ 로 처리됨  

|| Python 2.x | Python 3.x |
|----|----|----|
| __print문__ | print 'hello' / print( 'hello' ) | print( 'hello' ) |
| __int 나누기__ | print( 1/2 )  _# 0_ | print( 1/2 ) _# 0.5_ |
| __long 자료형__ | print( type(2**100) )  _#<type 'long'>_ | print( type(2**100) ) _#<class 'int'>_ |

___
[^1]: 한 줄씩 소스 코드를 해석해서 그 때마다 실행해 결과를 바로 확인할 수 있는 언어
