# djangorestframework
[official](https://www.django-rest-framework.org/tutorial/quickstart/#project-setup)

公式通りにやってもエラーが出る🧐

AIに質問した

このエラーは、プロジェクト名 "tutorial" が既存の Python モジュールと競合しているために発生しています。Django は既存の Python モジュール名と同じ名前のプロジェクトを作成することを許可していません。
この問題を解決するには、以下のいずれかの方法を試してみてください：

1. プロジェクト名を変更する:
別の名前を使用してプロジェクトを作成します。例えば：

```shell
mkdir django_tutorial
cd django_tutorial
```

2. コマンドかGUIでdjango, djangorestframeworkを追加する。
```shell
pip install django
pip install djangorestframework
```

3. djangoプロジェクトを作成
```shell
django-admin startproject django_tutorial .
# 開発サーバーを起動
python manage.py runserver
```

## admin ui

```shell
python manage.py startapp quickstart
```

プロジェクト構造
```
django_tutorial/
    manage.py
    django_tutorial/
        __init__.py
        settings.py
        urls.py
        asgi.py
        wsgi.py
    quickstart/
        __init__.py
        admin.py
        apps.py
        models.py
        tests.py
        views.py
```

次に、django_tutorial/settings.py 
ファイルを編集して、新しく作成した quickstart 
アプリケーションを INSTALLED_APPS に追加します：

```pycon
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'quickstart',  # 新しく追加したアプリケーション
]
```

これで、ログイン機能を含む新しいアプリケーションの開発を始める準備が整いました。
ログイン機能の実装に関しては、Django の組み込み認証システムを利用することをお勧めします。以下の手順で基本的なログイン機能を設定できます：

django_tutorial/urls.py に認証用URLを追加：

```pycon
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('accounts/', include('django.contrib.auth.urls')),
    # 他のURLパターン
]
```

テンプレートディレクトリを作成し、ログインテンプレートを追加：
```shell
mkdir -p templates/registration
touch templates/registration/login.html
```

