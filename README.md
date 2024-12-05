# **javascript AES Encrypt Decrypt utf8**
使用javascript建立一個AES加解密的驗證工具，使開發員在開發串接銀行API的時候，可以先了解要上傳的電文內容，以及收到的回應電文內容

使用情境：
1. 要開發與銀行串接API前，哪些欄位或是電文內容是要做加密或是解密，可以先用驗證工具了解加解密的方式跟流程
2. 每間銀行的資料加密流程與步驟可能是不儘相同，透過驗證工具可以調整成需要轉換的順序


## download & click & start
下載後即可啟動執行驗證

![AES-start](https://github.com/astinchen/javascript-AES-Encript-Decript-utf8/blob/main/AES-start.png)

## start to valid you Encription & Decription

![AES-validation](https://github.com/astinchen/javascript-AES-Encript-Decript-utf8/blob/main/AES-validation.png)


## stringToUTF8Bytes

將字串用UTF8轉成bytes

```
    function stringToUTF8Bytes(str) {
        const encoder = new TextEncoder("utf-8");
        return encoder.encode(str);
    }
```

## stringToBig5Bytes

<mark style="color:red;">串用big5轉成bytes，雖然TextEncoder目前有支援編碼格式，但實際上從頁面上直接用big5編碼轉成bytes無法成功，必須從檔案中讀取big5編碼格式才能正確轉成bytes</mark>

```
    function stringToBig5Bytes(str) {
        const encoder = new TextEncoder("big5");
        return encoder.encode(str);
    }
```

## bytesToBase64
```
    function bytesToBase64(bytes) {
        const decryptedHexString = new TextDecoder("utf-8").decode(new Uint8Array(bytes));
        return decryptedHexString;
    }
```
