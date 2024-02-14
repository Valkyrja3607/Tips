# Tips

## Docker

### Dockerの使用容量を確認
```
docker system df
```
### 全コンテナ一括削除
```
docker container prune
```
### 未使用イメージ一括削除
```
docker image prune
```
### タグ無しイメージ一括削除
```
docker rmi `docker images -f "dangling=true" -q`
```

### Build cacheの削除
```
docker builder prune
```

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

### 行ってる作業の一時退避
```
git stash
```

### 退避した作業を戻す
```
git stash pop
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

## ssh
### 公開鍵周り
#### クライアントPCで鍵を作る
```
ssh-keygen -t rsa -b 4096
```

#### リモートへ公開鍵を転送する
```
ssh-copy-id -i ~/.ssh/id_rsa.pub [リモートユーザー]@[リモートサーバーのホスト名]
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

## その他
### pydensecrfのインストール
```
pip install --force-reinstall cython==0.29.36
pip install --no-build-isolation git+https://github.com/lucasb-eyer/pydensecrf.git
```
