# Discord Gemini聊天機器人

## 安裝教學
1. 安裝[Python](https://www.python.org/downloads/release/python-3121/)
2. [安裝PIP](https://bootstrap.pypa.io/get-pip.py)(如果確認有安裝可以跳過)
3. 開啟控制台 輸入
```
pip install -r requirements.txt
```
4. 設置[config.json](#configjson設置教學)
5. 啟動~~原神~~bot.py

## config.json設置教學

* `token`: 你機器人的token，可以前往[Discord Developer Portal](https://discord.com/developers/applications)創建
* `gemini_key`: Gemini的API Key，可以前往[這裡](https://makersuite.google.com/u/0/app/apikey)創建
  * 如果有需要更多使用額度(1個API Key一分鐘只能用60次)可以使用更多API Key，詳細請看[使用多個API Key](#使用多個api-key)
* `developer`: 這應該不用解釋吧，寫上你的名稱就對了
  * 如果[修改提示詞](#修改提示詞)，這基本可以當成裝飾
* `prefix`: 你機器人的前綴，設定成!，幫助指令就是!help
* `bot_name`: 這應該不用解釋吧，寫上你機器人的名稱就對了
   * 如果[修改提示詞](#修改提示詞)，這還是有一點用
 

## 使用多個API Key
1. 先前往[Google Cloud Console](https://console.cloud.google.com)創建一個專案
2. 進入專案，打開`其他產品`，`API 與服務`
3. 按下`啟用 API 和服務`
4. 輸入`generative language api`，第一個就是
5. 點進去，然後點`啟用`
6. 你會跑到`API/服務詳細資料`，選到`API 和服務`裡的`憑證`
7. 按下`建立憑證`然後選取`API 金鑰`
8. 他會跳出一個`建立的 API 金鑰`，複製起來
9. 回到`config.json`，設置`gemini_key`成`["API_Key_1","API_Key_2"]` 你要放多少個都可以
10. 恭喜你完成了

## 修改提示詞
1. 先去[這裡](https://makersuite.google.com/u/0/app/prompts/new_chat)，創建一個模板
  * 修改的地方在`Write your prompt example`
2. 按下`Get Code`，選擇`Python`(如果要選的話)
3. 找到`convo = model.start_chat(history=[...])`，複製裡面的`history=[...]`，注意最後不要複製到`)`
4. 打開`bot.py` 找到`async def history(cid):`然後刪掉後面的`history =[...]`，刪到`]`
5. 貼上你剛剛複製的那一大段，完成

## 還沒寫
可能等我哪天有空才會寫
