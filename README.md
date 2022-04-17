# Tips

## git

### .gitignoreを後から反映
```
git rm --cached `git ls-files --full-name -i --exclude-from=.gitignore`
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


