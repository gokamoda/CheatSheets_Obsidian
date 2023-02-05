
## WSLを有効化
1. PowerShellを管理者として実行し，次のコマンドを実行
   ```PowerShell
   Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
   ```
2. 再起動
   
## 仮想マシンプラットフォーム有効化
1. PowerShellを管理者として実行し，次のコマンドを実行
   ```PowerShell
   Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform
   ```
2. 再起動

## Hypervsor Platform有効化
必須ではないが入れておく．
1. PowerShellを管理者として実行し，次のコマンドを実行
   ```PowerShell
    Enable-WindowsOptionalFeature -Online -FeatureName HypervisorPlatform
   ```
2. 再起動

## WSL2をデフォルトに設定
1. PowerShellを管理者として実行し，次のコマンドを実行
   ```PowerShell
   wsl --set-default-version 2
   ```

## WSLの更新
1. 引き続き管理者として実行したPowerShellで次のコマンドを実行
   ```PowerShell
   wsl --update
   ```


## Ubuntsuのインストール
1. Microsoft Storeで，Ubuntuを検索
2. `Ubuntu 22.04.1 LTS`をインストール

## Ubuntuの導入
1. インストールしたUbuntuを起動
2. 指示に従って初期設定を行う

## Ubuntuの利用をはじめる
1. Windows Terminalを開く
2. タブの右の`⋁`をクリック
3. `Ubuntu 22.04.1 LTS`をクリック
4. リポジトリ参照先の変更  
   Ubuntuのコンソールで以下を実行
      ```bash
      sudo sed -i -e 's%http://.*.ubuntu.com%http://ftp.jaist.ac.jp/pub/Linux%g' /etc/apt/sources.list
      ```
5. インストールされているソフトの更新  
   Ubuntuのコンソールで以下を実行
	```bash
	sudo apt update
	```

	```bash
	sudo apt upgrade
	```

6. 必要に応じてインストール（Cコンパイラなど）
	- pyenvで必要になった[(参考)](https://github.com/pyenv/pyenv/wiki)
	```bash
	sudo apt install build-essential libssl-dev zlib1g-dev
	```

## ターミナルの設定
1. ファイル/ディレクトリ名の自動補完で，大文字小文字を区別しないようにする  
   `.inputrc`ファイルを作成し，以下を追加
   ```
   set completion-ignore-case on
   ```

## VSCodeを使えるようにする
```bash
code --install-extension ms-vscode-remote.remote-wsl
```