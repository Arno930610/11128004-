# Python程式設計-期末報告
  11128004 林峻成
    
# 題目(加密字符串)
密碼對照表的第一行為明碼行，放置大寫字母

第二行為依照下列規則產生的密碼行：

給定一個單詞，將單字中所有字元轉為大寫字母，對於單字中重複出現的字母，保留第一次出現的，刪除之後重複出現的該字元。
用剩餘字母組成秘鑰從密碼行的起始位置放置；再用未在秘鑰中出現的其他大寫字母按字母表順序依序填入密碼行剩餘位置。

兩筆輸入

1.輸入一個字串作為密鑰

2.輸入一個需要加密的字串

# 生成大寫英文字母的序列
```
import string

upperLetter = string.ascii_uppercase
```
# 提醒使用者輸入要加密的金鑰
```
print("請輸入要加密的金鑰:");
```

# 使用者輸入英文字串轉換成大寫
```
s = input().upper()
```
# 創建一個列表 code，其中包含了不在輸入字串 s 中的大寫英文字母，按順序排列
```
code = list(set(upperLetter) - set(s))
code.sort()
```
# 創建一個列表 ls，其中包含了輸入字串中不重複的字母，進行排序，排序是根據字母在原始輸入字串中的順序
```
ls = list(set(s))
ls.sort(key = s.index)
```
# 將列表 ls 和 code 組合成一個新的字串，並賦值給變數 keys ，將新字串用作替換密碼表。
```
keys = ''.join(ls + code)
```
# 提醒使用者輸入想要加密的字串
```
print("請輸入想要加密的字串:")
```

# 使用者輸入須加密的字串轉換成大寫，建立一個轉換表 table，用於將須加密的字串替換為替換密碼表中對應的字母。
```
decode = input().upper()
table = ''.maketrans(upperLetter, keys)
```
# 印出結果
```
print("加密過後結果為:" + decode.translate(table))
```

# 程式碼和結果
[![image](https://github.com/Arno930610/11128004-/blob/main/11128004-%E6%9C%9F%E6%9C%AB.png?raw=true)](https://github.com/Arno930610/11128004-/blob/main/11128004-%E6%9C%9F%E6%9C%AB.png?raw=true))]
