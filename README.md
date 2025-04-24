# 📄 ブログアプリ構成概要

##コンセプトと目的　

病気や障がいを抱えた方の辛い気持ちや挫折を乗り越えた経験を当事者同士で共有できること、同じ境遇の方同士でSNSのグループを通して繋がることができることを目的としてミニマムで開発しました。

## ✅ 各ファイルの主な機能

### `forms.py`
- Djangoのフォーム定義ファイル。
- 使用目的：
  - ユーザー登録・プロフィール編集用フォーム（`CustomUserCreationForm`, `CustomUserChangeForm`）
  - 投稿・グループ作成フォーム（`PostForm`, `GroupForm`）

### `models.py`
- データベースと接続するモデル定義。
- 含まれるモデル：
  - `CustomUser`：ユーザープロフィール付き拡張ユーザーモデル
  - `Post`：投稿情報（タイトル、本文、画像）
  - `Category`：グループのカテゴリー
  - `Group`：ユーザーが作成できるグループ情報

### `views.py`
- 各ページの処理ロジック（View）を定義。
- 使用されているビュータイプ：
  - `ListView`, `DetailView`, `CreateView`, `DeleteView`, `TemplateView`
- 主な機能：
  - 投稿一覧、詳細、作成、編集、削除
  - グループ一覧、作成、削除
  - ユーザー登録・ログイン後マイページ表示など

---

## 🧰 使用されている主なライブラリ

### Django標準ライブラリ
- `django.shortcuts`：ビュー内でのテンプレート描画やリダイレクトなど
- `django.views.generic`：汎用ビュー（`ListView`, `DetailView`, `CreateView`, etc.）
- `django.contrib.auth`：ユーザー認証（`UserCreationForm`, `login_required`, `AbstractUser`）
- `django.db.models`：モデル定義用
- `django.urls`：URL逆引き（`reverse_lazy`）
- `django.core.paginator`：ページネーション（`Paginator`, `EmptyPage`, etc.）

### その他
- `Q`オブジェクト：検索機能でAND/OR条件を組み立てるために使用（`from django.db.models import Q`）

---



