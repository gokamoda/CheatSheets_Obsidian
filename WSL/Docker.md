1. 既存ライブラリアップデート
   ```bash
   sudo apt update
   ```

	```bash
   sudo apt upgrade
   ```
   
2. インストール
[参考](https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script)
   ```bash
   curl -fsSL https://get.docker.com -o get-docker.sh
   ```

   ```bash
   sudo sh get-docker.sh
   ```
   
3. 権限付与
   ```bash
   sudo usermod -aG docker $USER
   ```
   
   Ubuntu再起動
   
4. 起動確認
   ```bash
   sudo service docker start
   ```
   
   ```bash
   docker run hello-world
   ```