## 目標
- JIS配列の内臓キーボードで刻印通りに入力できること．
- US配列の外付けキーボードで刻印通りに入力できること．

## 注意
- Windows Updateなどで設定が戻ってしまう可能性がある．
- レジストリをいじるのは自己責任で．

## 設定方法
### 1. デフォルトを英語配列にする
1. 設定>時刻と言語>言語と地域 を開く．
1. 「日本語」と書かれ，その下に「言語パック，音声認識．．．」などが書いてある行の右側にある「...」をクリックし，「言語のオプション」をクリックする．
1. 後半部分の「キーボードレイアウト」で，「英語キーボード (101/102キー) 」を設定する．
1. 再起動を求められるので再起動する．

### 2. 内臓キーボードをJIS配列として認識させる．
1. レジストリエディタを起動する．
1. `Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\i8042prt\Parameters`まで移動する．
1. この中の`OverrideKeyboardType`を`OverrideKeyboardType.bak`に，`OverrideKeyboardSubtype`を`OverrideKeyboardSubtype.bak`などに変更することにより無効化する．
1. 簡単のために外付けキーボードをすべて外す．
1. デバイスマネージャーを開く．
1. 「キーボード」から内臓キーボードと思われるものをダブルクリックする．
    - 外付けキーボードを外しているので内臓キーボードだけが表示されるはず．
1. 詳細タブで，プロパティから「デバイスインスタンスパス」を選択する．
1. `Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\デバイスインスタンスパス\Device Parameters`まで移動する．
1. 次のパラメータを設定する．
    - OverrideKeyboardType : 7
    - OverrideKeyboardSubType : 2
1. 再起動する．
