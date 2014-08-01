# Git

- のどか（以下「の」）：さて、次は実際にGitを使ってみるわよ。
- はじめ（以下「は」）：うぅ、まだ概念すら十分に分かった気がしないのに心配なのです。blobやcommitなどの単語が頭の中をぐるぐる回っているのです。
- の：習うより慣れろ、よ。実際、概念を完全に覚えようとするよりも実際に使ってみた方が身に付くと思うわ。

Gitの導入とgitコマンドの具体的な使い方を解説していきます。

# Getting Started
mac等を利用していると`git`コマンドは標準で使えたりしますが、利用しているOS等によっては改めて導入する必要があるかもしれません。

Gitそのものは、下記のURLよりダウンロードできます。

```
http://git-scm.com/downloads
```

[TODO: Windowsでの導入方法]

なお、本書においては筆者のMacbook Airにインストールされているgitを基準とします。

```
% git --version
git version 1.8.5.2 (Apple Git-48)
```

# Commands

## 使い始める
### git config
まずはGitに対して自己紹介をしましょう。commitオブジェクトができることは前述した通りです。そのとき、「誰が」commitしたのかを設定するのです。

```
% git config --global user.name treby
% git config --global user.email treby@atelier-nodoka.net
```

こうすることで、ホームディレクトリ以下の`.gitconfig`ファイルに次の内容が書き込まれます。

```
% cat ~/.gitconfig
[user]
	name = treby
	email = treby@atelier-nodoka.net
```
ここで設定した情報は、コミットに含まれます。

```
% git log --reverse
commit dacc936975dde6a1c83db7f853e7dc0ef3d6da4e
Author: treby <treby@atelier-nodoka.net>
Date:   Sat Jun 7 16:24:40 2014 +0900

    Initial commit.
```

他にも、`git config`コマンドでは、いろいろな設定が行えます。

### git init
今いるディレクトリ以下のファイルをgit管理下におくコマンドです。
例えば今、CSSファイルとJSファイル、そして単一のページを持つシンプルなWebページがあるとします。

```
% cd public_html
% tree --dirsfirst
.
├── css
│   └── style.css
├── js
│   └── index.js
└── index.html
```
ここで、`git init`コマンドを実行することでこれら全てのファイルをGit管理下におくことができます(リポジトリが作成されます)。

```
% ls -a
.          ..         css        index.html js

% git init
Initialized empty Git repository in /Users/treby/Documents/sample-git/.git/

% ls -a
.          ..         .git       css        index.html js
```

ちなみに`.git`ディレクトリの下は次のようになっています。

```
% tree .git
.git
├── HEAD
├── branches
├── config
├── description
├── hooks
│   ├── applypatch-msg.sample
│   ├── commit-msg.sample
│   ├── post-update.sample
│   ├── pre-applypatch.sample
│   ├── pre-commit.sample
│   ├── pre-push.sample
│   ├── pre-rebase.sample
│   ├── prepare-commit-msg.sample
│   └── update.sample
├── info
│   └── exclude
├── objects
│   ├── info
│   └── pack
└── refs
    ├── heads
    └── tags
```

## 歴史を保存する
まずは、基本的なコマンド類について説明します。

### git add

### git commit


`git status`コマンドを

```
% git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	css/
	index.html
	js/

nothing added to commit but untracked files present (use "git add" to track)
```


## 状態を確認する

- `git add`
  - 変更をステージング・エリアにあげる
- `git commit`
  - ステージングにあげた変更をリポジトリに反映する
- `git reset`
  - 変更を取り消す
- `git log`


- `git branch`
- `git checkout`
- `git merge`

## ネットワークを利用する
- `git remote`
- `git clone`
  - すでにあるリポジトリを手元に持ってくるコマンド。
- `git fetch`
- `git pull`
- `git push`
