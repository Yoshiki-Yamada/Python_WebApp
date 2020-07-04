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

[http://127.0.0.1:8000/](http://127.0.0.1:8000/) にアクセスしてみると404が出ました。これはurlの参照先を変更したからです。  
![image](https://github.com/Yoshiki-Yamada/Python_WebApp/blob/master/README/image/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202020-07-04%2016.54.26.png)  

では、[http://127.0.0.1:8000/polls/](http://127.0.0.1:8000/polls/) にアクセスしてみましょう。下のような画面が出ればOKです！  
![image](https://github.com/Yoshiki-Yamada/Python_WebApp/blob/master/README/image/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88%202020-07-04%2016.55.16.png)  
