## WSLのバックアップ

```PowerShell
wsl --export Ubuntu-22.04  $HOME\Work\Ubuntu\wsl_backup.tar
```

## WSLディストロ削除
```PowerShell
wsl --unresister Ubuntu-22.04
```


## バックアップから復元
```PowerShell
wsl --import Ubuntu-22.04 $HOME\Work\Ubuntu Desktop\wsl230203.tar
```

### デフォルトユーザー変更
```PowerShell
ubuntu2204 config --default-user <使用したいユーザー>
```

### WSLユーザー一覧
```bash
cat /etc/passwd
```