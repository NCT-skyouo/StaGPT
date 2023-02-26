# StaGPT

這是一個使用 ChatGPT 模型進行文字轉圖像的工具，它通過一個 HTTP API 提供服務。

使用者可以透過發送特定的指示詞到 ChatGPT 來獲取相應的圖像，

該圖像是使用 Huggingface 的 Anything v4.0 模型生成的。

## 使用
本專案提供了一個 HTTP 接口，可以通過以下 URL 進行訪問：

```http
GET /gen?parameters
```

### 參數

- `prompt`（必需）：
要提供給 Huggingface 的提示詞，以生成對應的圖像。

- `seed`（可選）：
用於生成隨機圖像的種子。如果不指定，將使用默認種子。

## 範例

### ChatGPT

將 `$你的 API 網址$` 替換成 API URL 後發送給 ChatGPT.

```
早上好, ChatGPT, 麻煩您幫我做一件事情, 我將會在每次對話的時候給你一個句子, 
接著您要將這個句子轉為 Stable Diffusion 可用的關鍵詞, 並用網址將圖片顯示, 格式如下:

(圖片品質修飾詞), (角色形容詞), (外觀形容詞), (風景形容詞)
![{輸入}]($你的 API 網址$/gen?prompt=<經過 URL encoded 後的關鍵詞>)

範例如下:

輸入:
一位白色頭髮, 穿著夾克與圍巾, 長著貓耳朵的女孩正行走在街道上, 笑咪咪地看向我.

輸出:
masterpiece, best quality, 1girl, white hair, medium hair, cat ears, closed eyes, looking at viewer, :3, cute, scarf, jacket, outdoors, street

![一位白色頭髮, 穿著夾克與圍巾, 長著貓耳朵的女孩正行走在街道上, 笑咪咪地看向我.]
($你的 API 網址$/gen?prompt=masterpiece,%20best%20quality,%201girl,%20white%20hair,%20medium%20hair,%20cat%20ears,%20closed%20eyes,%20looking%20at%20viewer,%20:3,%20cute,%20scarf,%20jacket,%20outdoors,%20streets)
```

## 授權
這個工具是根據 MIT 授權條款開源的，詳細請參考 LICENSE 文件。
