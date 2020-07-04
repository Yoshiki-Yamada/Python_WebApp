# #01 StartUp!

## 目標
### pycharmでPythonとDjangoを使ってローカルサーバーでページを表示する

## Let's Begin!

### pycharmでpollsを作成する
pollsとは、なんかいろいろ入ってるwebを作成するためのディレクトリです。バーのTools->Run manage.py Task...というように押していく。

すると、したにmanage.py@project_nameが現れる。このproject_nameはpython_djangoなので以下からpython_djangoで書いていきます。そこにstartapp pollsと入力してエンターするとpollsディレクトリができる。その中にはたくさんの希望が入っているはずです。

### codeを書いていく


#### polls/views.py
```python
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

#### polls/urls.py
```python
from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

#### python_django/urls.py
```python
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('polls/', include('polls.urls')),
    path('admin/', admin.site.urls),
]
```


### 実行する

[]()にアクセスしてみると404が出ました。これはurlの参照先を変更したからです。

では、[]()にアクセスしてみましょう。下のような画面が出ればOKです！
