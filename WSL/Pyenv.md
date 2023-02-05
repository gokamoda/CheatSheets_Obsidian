1. 必要なパッケージインストール[(参考)](https://github.com/pyenv/pyenv/wiki)
	```bash
	sudo apt update; sudo apt install build-essential libssl-dev zlib1g-dev \
	libbz2-dev libreadline-dev libsqlite3-dev curl \
	libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
	```
	
2. pyenvのインストール
   ```bash
   curl https://pyenv.run | bash
   ```
   
3. .bashrcに以下を追記
   ```.bashrc
   export PYENV_ROOT="$HOME/.pyenv"
   command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
   eval "$(pyenv init -)"
   ```
   
4. インストールの確認
   ```bash
   pyenv --version
   ```

5. アップデート確認
	```bash
	pyenv update
	```

6. pyenvにインストールできるバージョンの確認
	```bash
	pyenv install --list
	```