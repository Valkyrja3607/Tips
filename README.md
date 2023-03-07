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
### 直前のaddをなかったことにする
```
git reset HEAD <file_name>
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
### requirements.txtの作成
```
pip freeze > requirements.txt
```
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

### ディレクトリのファイル数をカウント
```
ls -U1 | wc -l
```

## vscode
### 設定
`Enable Preview`をoffにする

`FilesAutoSave`をafterDelayにする

## PyTorch
### 少数3桁までe+02とかにしない
```
torch.set_printoptions(precision=3, sci_mode=False)
```

## Lightgbm
### log出力しない
```
lgb.train(lgbm_params, lgb_train, valid_sets=lgb_eval, verbose_eval=False)
```

