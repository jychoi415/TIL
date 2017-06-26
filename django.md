# Django
* 설치  
```
pip3 install django
```

* 프로젝트 만들기  
```
django-admin startproject <프로젝트이름>
```

* Django 서버 실행  
```
python3 manage.py runserver
```
localhost:8000으로 접속
 
* App 만들기  
```
python3 manage.py startapp <App 이름>
```
=> <App 이름> 디렉토리 생성  
App : 웹사이트를 기능별로 분류 해놓은 단위

 
* App DB에 저장  
<프로젝트이름>/settings.py에 `INSTALLED_APPS`에 <App 이름> 추가  
 
* admin 접속  
```
python3 manage.py createsuperuser
```
localhost:8000/admin에 접속


* 사용자 클래스 사용  
admin.py에 `admin.site.register(<클래스명>)` 추가  
(?).py `from .models import <클래스명>`
```
python3 mange.py makemigrations
```
 
* object 구분  
`__str__` 메소드 오버라이딩  

* 값 나타내기  
view.py에 사용자 클래스 임포트  
`<사용자 클래스명>.objects.all()` : 모든 object 불러와 객체에 저장  
	=> for문으로 출력. HTML 문법 사용  
`HttpResponse()` 리턴 필수!  

* Shell로 DB 저장  
```
python3 manage.py shell
from <앱이름>.modles import <사용자 클래스>
<사용자 클래스>.objects.all()
```
__content 추가__
```
new = <사용자 클래스>(<요소>="")
new.save()
```

* object 하나만 불러오기  
```
no1 = <사용자 클래스>.objects.filter(요소 = "")
```

* 템플릿 사용  
<App 이름> 밑에 __templates__ 폴더 생성 -> <App 이름> 폴더 생성 -> __index.html__ 생성  
views.py의 index 메소드에 `render(request, <index 경로>)`  

* 동적으로 내용 표시 가능  
(views.py)  
```
candidates = Candidate.objects.all()
context = {‘candidates’:candidates}
return render(request, ‘elections/index.html’, context)
```
(index.html)  
for문 사용  
```
{% for _ in _ %} ~~ {% endfor %}
<tr><td>{{__.요소}</td>}</tr>
``` 
 
* MVC 패턴  
	1. Model-데이터(models.py) : 사용자 클래스의 형식대로 데이터를 DB에 저장, 불러옴  
	1. View-화면(templates) : 어떤 화면을 보여줄지 결정  
	1. Controller-조율(views.py) : 모델에서 데이터를 읽어 index.html에 전달  
⇒ MVC패턴 

Django는 특이하게 View가 templates, Controller가 views.py다  
⇒ [링크](https://goo.gl/bQKG1E)
