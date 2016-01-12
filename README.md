# DIT de Git勉強会

## 初期設定

名前とメールアドレスを登録しましょう。メールアドレスはGitHubに登録したメールアドレスが好ましいです。

デスクトップでもどこでもいいので、好きなフォルダを作ってそのフォルダを右クリックし、Git Bash Hereをクリックしてください。
そうするとコマンドプロンプトがでてきます。そこに以下のコマンドを打ちましょう。

```
git config --global user.name "Your Name"
git config --global user.email foo@example.com
```
ローム記念館でgitを使う場合、プロキシ設定が必要です。以下のコマンドを打ちましょう。

```
export http_proxy=proxyr.drm.doshisha.ac.jp:8080
export https_proxy=proxyr.drm.doshisha.ac.jp:8080
```

## cloneしてリポジトリを手元にもってきましょう

```
git clone https://github.com/dit-rohm/git-practice
```

`git-practice`というフォルダができたと思います。

## まずブランチを切りましょう

自分の名前でbranchを作りましょう。

```
git branch tanaka
```

ブランチが作られているか確認してみましょう。今いるブランチは以下のコマンドで確認できます。

```
git branch
```

*がついているブランチが今いるブランチです。今作ったブランチに移動してみましょう。

```
git checkout tanaka
```

`git branch`で移動できているか確認してください。


参考：[Github-flowを分かりやすく図解してみた](http://b.pyar.bz/blog/2014/01/22/github-flow/)


## 自己紹介を追加しましょう

メモ帳などエディタを開き、cloneしてきた`git-practice`フォルダの中に自分の名前でテキストファイルを追加しましょう。（例：`tanaka.txt`）
テキストファイルの中に自分の自己紹介を書いてみましょう。

```
私の名前は<NAME>です。
趣味はプログラミングです。
```

# add, commit

まずは変更したファイルをステージングエリアに上げます。

```
git add tanaka.txt
```

addされたことを確認しましょう。

```
git status
```

ファイル名が緑色になっていればaddができています。

それではいよいよ`commit`です

```
git commit -m “add tanaka.txt”
```

# push
ユーザ名とパスワードが聞かれるので、GitHubに登録したユーザ名とパスワードを入力してください。

```
git push origin tanaka
```

# プルリクエストを作成する

このREADMEの上の方に「Compare & pull request」という緑のボタンがあるので、クリックしましょう。必要であればタイトルとコメントを入力して、「Create pull request」をクリックしましょう。

GitHubの「Pull requests」を開き、自分の送ったプルリクエストを開きましょう。下にある「Merge pull request」を押すとリポジトリに反映されます。

# pull
みんなが書いた自己紹介を手元に持ってきましょう。まずはmasterブランチに移動します。

```
git checkout master
```

その後、GitHub上のリポジトリから手元に最新の変更を反映させます。

```
git pull origin master
```

# 他の人の自己紹介にコメントをつけよう

新しいブランチを作ってそこに移動しましょう。

```
git branch tanaka-2
git checkout tanaka-2
```

同じ班の人のファイルにコメントをしましょう（テキストファイルに追記して保存）。右隣の人のファイルを編集してください。

```
git add <編集したテキストファイル>
git commit -m “add comment”
```

前と同様に変更をGitHubにpushします。

```
git push origin tanaka-2
```

githubに移動してプルリクエストを作りましょう。そのあと自分のプルリクエストのページに行って「Merge pull request」をクリックしましょう。

しばらくしたら手元に持ってきましょう。

```
git pull origin master
```

ファイルを確認しましょう。他の人が書いたコメントが入れたらOKです。
# まとめ

1. git clone
2. git branch
3. git add
4. git commit
5. git push
6. プルリクエストを作成
7. プルリクエストをマージ
8. git pull

2から8を繰り返す。 

# アンケートのお願い
[こちら](https://docs.google.com/forms/d/1w5rlfJN2L6XybvRDjSoazWLXRSKfrQsFLb0CMy93RIE/viewform?usp=send_form)より、アンケートにご協力お願いします。
