# GitHubリポジトリをローカルにコピー（クローン）する方法【初心者向け完全ガイド】

GitHubにあるリポジトリを自分のパソコンにコピーしたいとき、`git clone` コマンドを使います。  
この記事では、**初めてGitを使う方**でもわかるように、Windows・Mac それぞれの手順をひとつずつ丁寧に解説します。

---

## 前提条件

以下のソフトがインストールされている必要があります：

- **Git** — [公式サイト](https://git-scm.com/) からダウンロード・インストール

> 💡 **Mac の場合**：ターミナルで `git --version` を実行すると、Xcode Command Line Tools のインストールを促される場合があります。画面の指示に従ってインストールすればOKです。

### Gitがインストール済みか確認する

ターミナルを開いて、以下のコマンドを実行してください：

```bash
git --version
```

バージョン番号が表示されればOKです（例：`git version 2.45.0`）。  
表示されない場合は、先にGitをインストールしてください。

---

## 手順1：クローンしたいリポジトリのURLを取得する

1. ブラウザで **GitHubのリポジトリページ** を開く
2. 緑色の **「Code」ボタン** をクリック
3. **HTTPS** タブが選択されていることを確認
4. URLの右にある **📋コピーアイコン** をクリックしてURLをコピー

例：`https://github.com/daruma-ad/darumaya_fukubiki.git`

> この手順は Windows / Mac 共通です。

---

## 手順2：ターミナルを開く

### 🪟 Windows の場合

PowerShell を開く方法は3つあります。どれでもOKです。

#### 方法A：スタートメニューから開く

1. キーボードの **Windowsキー** を押す
2. `powershell` と入力する
3. 表示された **「Windows PowerShell」** をクリック

#### 方法B：エクスプローラーのアドレスバーから開く（おすすめ！）

1. エクスプローラーでクローン先にしたいフォルダを開く
2. **アドレスバー**（フォルダのパスが表示されている場所）をクリック
3. `powershell` と入力して **Enter** を押す

→ このフォルダの場所でPowerShellが開くので、`cd` で移動する手間が省けます！

#### 方法C：右クリックメニューから開く

1. エクスプローラーでフォルダ内の空白部分を **Shift + 右クリック**
2. **「PowerShellウィンドウをここで開く」** を選択

---

### 🍎 Mac の場合

ターミナル.app を開く方法は3つあります。どれでもOKです。

#### 方法A：Spotlight から開く（おすすめ！）

1. **⌘ Command + Space** を押して Spotlight を開く
2. `ターミナル` と入力する
3. 表示された **「ターミナル.app」** をクリック

#### 方法B：Launchpad から開く

1. Dock の **「Launchpad」** をクリック
2. 上の検索バーに `ターミナル` と入力
3. 表示された **「ターミナル」** をクリック

#### 方法C：Finder から開く

1. Finder で **「アプリケーション」→「ユーティリティ」** を開く
2. **「ターミナル.app」** をダブルクリック

---

## 手順3：保存先のフォルダに移動する

> 💡 Windows で手順2の**方法B**または**方法C**を使った場合は、すでに目的のフォルダにいるためこのステップはスキップできます。

### 🪟 Windows の場合

```powershell
cd C:\Users\darumaya\antigravity\20260322darumaya_fukubiki
```

> 💡 **ヒント**：パスを手入力するのが面倒なときは、エクスプローラーからフォルダを PowerShell にドラッグ＆ドロップすると、パスが自動入力されます。

### 🍎 Mac の場合

```bash
cd ~/Desktop/my-project
```

> 💡 **ヒント**：Finder からフォルダをターミナルにドラッグ＆ドロップすると、パスが自動入力されます。Mac でもこのテクニックは使えます！

---

## 手順4：リポジトリをクローンする

ターミナルに以下のコマンドを入力して **Enter** を押します（Windows / Mac 共通）：

```bash
git clone https://github.com/daruma-ad/darumaya_fukubiki.git .
```

> ⚠️ **よくある間違い**：URLだけを入力するとエラーになります。必ず先頭に **`git clone`** を付けてください！
>
> ```
> ❌ https://github.com/daruma-ad/darumaya_fukubiki.git
> ✅ git clone https://github.com/daruma-ad/darumaya_fukubiki.git .
> ```

> 💡 **貼り付けのショートカット**
> - **Windows**（PowerShell）：右クリック または `Ctrl + V`
> - **Mac**（ターミナル）：`⌘ Command + V`

### 末尾の `.`（ドット）について

末尾に `.`（ドット）を付けると、**今いるフォルダに直接**ファイルが展開されます。  
付けない場合は、リポジトリ名のフォルダが自動で作成され、その中にファイルが入ります。

| 項目 | `git clone <URL>` | `git clone <URL> .` |
|------|-------------------|---------------------|
| フォルダ作成 | リポジトリ名のフォルダが**自動作成** | 作成されない（今のフォルダに展開） |
| フォルダの事前準備 | 不要 | **空のフォルダが必要** |
| おすすめ場面 | とりあえずコピーしたいとき | 作業フォルダを先に用意したとき |

### 成功時の表示例

```
Cloning into '.'...
remote: Enumerating objects: 12, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (10/10), done.
Receiving objects: 100% (12/12), done.
```

---

## 手順5：クローンの結果を確認する

以下のコマンドで、ファイルが正しくコピーされたか確認します：

### 🪟 Windows の場合

```powershell
dir
```

### 🍎 Mac の場合

```bash
ls
```

### 表示例

```
fukubiki_ki.png
fukubiki_ki2.png
github_pages_deployment_guide.md
index.html
```

このようにリポジトリ内のファイルが表示されれば、クローン成功です 🎉

---

## よくあるエラーと対処法

### ❌ `CommandNotFoundException`（Windows：URLだけ入力した）

```
'https://github.com/...' は、コマンドレット、関数、スクリプト ファイル、
または操作可能なプログラムの名前として認識されません。
```

**原因**：`git clone` を付けずにURLだけを入力しています。

**対処法**：コマンドの先頭に `git clone ` を付けて再実行してください。

### ❌ `command not found: https://...`（Mac：URLだけ入力した）

```
zsh: command not found: https://github.com/...
```

**原因**：Windows と同様、`git clone` を付けずにURLだけを入力しています。

**対処法**：コマンドの先頭に `git clone ` を付けて再実行してください。

### ❌ `fatal: destination path '.' already exists and is not an empty directory.`

**原因**：クローン先のフォルダにすでにファイルがあります。

**対処法**：
- フォルダ内のファイルを削除してから再実行
- または末尾の `.` を外して通常のクローンを使う

### ❌ `fatal: repository 'https://...' not found`

**原因**：URLが間違っているか、リポジトリが非公開（プライベート）です。

**対処法**：
- URLをもう一度確認してコピーし直す
- プライベートリポジトリの場合は、アクセス権を確認する

### ❌ `xcrun: error: invalid active developer path`（Mac のみ）

**原因**：Xcode Command Line Tools がインストールされていません。

**対処法**：以下のコマンドを実行してインストールしてください：

```bash
xcode-select --install
```

---

## まとめ

| ステップ | やること | Windows | Mac |
|----------|----------|---------|-----|
| 事前確認 | Gitの確認 | `git --version` | `git --version` |
| 手順1 | URLをコピー | GitHubの「Code」ボタンから | 同左 |
| 手順2 | ターミナルを開く | アドレスバーに `powershell` | `⌘ + Space` → `ターミナル` |
| 手順3 | フォルダに移動 | `cd <フォルダのパス>` | `cd <フォルダのパス>` |
| 手順4 | クローン実行 | `git clone <URL> .` | `git clone <URL> .` |
| 手順5 | 結果確認 | `dir` | `ls` |

たった1つのコマンド `git clone <URL>` で、GitHubのリポジトリをまるごとコピーできます。  
Windows でも Mac でも、手順はほぼ同じです。ぜひ活用してみてください！
