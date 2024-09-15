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