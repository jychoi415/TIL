# Server Error
170701 여개모각코에서 Django 코딩을 하려 `python3 manage.py runserver` 명령어로 서버를 돌리는데 갑자기 대량(?)의 오류를 뿜어냄  

>Performing system checks...
>
>Unhandled exception in thread started by <function check_errors.<locals>.wrapper at 0x7fb406954ae8>  
Traceback (most recent call last):  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/utils/autoreload.py", line 227, in wrapper  
    fn(\*args, \*\*kwargs)  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/core/management/commands/runserver.py", line 125, in inner_run  
    self.check(display_num_errors=True)  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/core/management/base.py", line 359, in check  
    include_deployment_checks=include_deployment_checks,  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/core/management/base.py", line 346, in _run_checks
    return checks.run_checks(**kwargs)  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/core/checks/registry.py", line 81, in run_checks
    new_errors = check(app_configs=app_configs)  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/core/checks/urls.py", line 16, in check_url_config
    return check_resolver(resolver)  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/core/checks/urls.py", line 26, in check_resolver
    return check_method()  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/urls/resolvers.py", line 254, in check  
    for pattern in self.url_patterns:  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/utils/functional.py", line 35, in __get__  
    res = instance.__dict__[self.name] =   self.func(instance)  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/urls/resolvers.py", line 405, in url_patterns  
    patterns = getattr(self.urlconf_module, "urlpatterns", self.urlconf_module)  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/utils/functional.py", line 35, in __get__  
    res = instance.__dict__[self.name] = self.func(instance)  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/urls/resolvers.py", line 398, in urlconf_module  
    return import_module(self.urlconf_name)  
  File "/usr/lib/python3.5/importlib/__init__.py", line 126, in import_module  
    return _bootstrap._gcd_import(name[level:], package, level)  
  File "<frozen importlib._bootstrap>", line 986, in _gcd_import  
  File "<frozen importlib._bootstrap>", line 969, in _find_and_load  
  File "<frozen importlib._bootstrap>", line 958, in _find_and_load_unlocked  
  File "<frozen importlib._bootstrap>", line 673, in _load_unlocked  
  File "<frozen importlib._bootstrap_external>", line 665, in exec_module  
  File "<frozen importlib._bootstrap>", line 222, in _call_with_frames_removed  
  File "/home/runam/django/mysite/mysite/urls.py", line 20, in <module>
    url(r'^', include('elections.urls')),  
  File   "/home/runam/.local/lib/python3.5/site-packages/django/conf/urls/__init__.py", line 50, in include  
    urlconf_module = import_module(urlconf_module)  
  File "/usr/lib/python3.5/importlib/__init__.py", line 126, in import_module  
    return _bootstrap._gcd_import(name[level:], package, level)  
  File "<frozen importlib._bootstrap>", line 986, in _gcd_import  
  File "<frozen importlib._bootstrap>", line 969, in _find_and_load  
  File "<frozen importlib._bootstrap>", line 958, in _find_and_load_unlocked  
  File "<frozen importlib._bootstrap>", line 673, in _load_unlocked  
  File "<frozen importlib._bootstrap_external>", line 661, in exec_module  
  File "<frozen importlib._bootstrap_external>", line 767, in get_code  
  File "<frozen importlib._bootstrap_external>", line 727, in source_to_code  
  File "<frozen importlib._bootstrap>", line 222, in _call_with_frames_removed  
  File "/home/runam/django/mysite/elections/urls.py", line 6
    url(r'^names/(?P<name>.+)/$', views.names')  

### 원인 분석
__url.py__ 에 링크 거는 `url(r'^name/(!P<name>.+)/$', views.name')`를 삽입하면 오류를 발생시킴  


### 오류 해결
`url(r'^name/(!P<name>.+)/$', views.name')` 코드 라인이 잘못된 것을 확인함  
  + `^name`을 `names`로, `views.name`을 `views.names`로 수정해야 __view.py__ 의 __names__ 메소드 사용 가능
  + `!P<name>`은 문법상 오류. 오타임

`url(r'^names/(?P<name>.+)/$', views.names)`로 수정  
