# Tips

## git

### .gitignoreを後から反映
```
git rm --cached `git ls-files --full-name -i --exclude-from=.gitignore`
```
### 直前のcommitをなかったことにする
```
git reset --soft HEAD^
```
### git rebase (a)->(b)
```
git rebase master <branch_name>
```
```
(a)
      A---B---C <branch_name>
     /
D---E---F---G master

(b)
              A'---B'---C' <branch_name>
             /
D---E---F---G master
```

### git remoteの変更
```
git remote set-url origin {new url}
```

## pip

### pip install -r requirements.txtでエラーが出ても続行
```
cat requirements.txt | xargs -n 1 pip3 install
```

## コマンド

### 容量
#### ディレクトリの全体容量
```
du -s -h ディレクトリ名
```
#### ディレクトリ内の各要素の容量
```
du -a -h ディレクトリ名
```

## vscode
### 設定
`Enable Preview`をoffにする

`FilesAutoSave`をafterDelayにする


