# #01 StartUp!

## 目標
### pycharmでPythonとDjangoを使ってローカルサーバーでページを表示する

## Let's Begin!

### pycharmでpollsを作成する
`polls`とは、なんかいろいろ入ってるwebappを作成するためのディレクトリです。バーの`Tools`->`Run manage.py Task...`というように押していく。

すると、したに`manage.py@project_name`が現れる。この`project_name`は`python_django`なので以下から`python_django`で書いていきます。そこに`startapp polls`と入力してエンターすると`polls`ディレクトリができる。その中にはたくさんの`希望`が入っているはずです。

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
