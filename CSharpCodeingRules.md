# Binodata C Sharp Coding Rules
給Binodata工程師參考的C Sharp 開發規範

# 命名

兩種命名種類，Pascal, Camel

* Pascal

```C Sharp
    
    HelloWorld;

```

* Camel
```C Sharp

    helloWorld;

```


* [參考](http://www.dotblogs.com.tw/ouch1978/archive/2010/10/30/c-sharp-naming-convention.aspx)

|種類      						|命名規則  |範例 |注意事項|
|-----------------------------|---------|----|------|
|Project File  					|Pascal   |Math.Algorithm.csproj | |
|Source File     				|Pascal	| RuleSetup.cs | 保持檔案名稱與Class名稱一致|
|Resource or Embedded File    |Pascal	| TestPicture.jpg | |
|Namespace     					|Pascal	| MyCompany.Wpf.Controls|儘量使用"公司名稱.專案名稱/技術名稱.功能分類/子類別"做為命名準則|
|Class or Struct     			|Pascal	| CustomAttribute| 使用名詞命名，並使用基底類別名稱做為後置詞|
|Interface     					|Pascal	|ICustomer | 使用前置詞"I"|
|Generic Class & Generic Parameter Type     |Pascal| TKey,TValue| 使用前置詞"T"或"K" |
|Method     						|Pascal	| ValidateUser| 使用動詞作為開頭|
|Property     					|Pascal	| Name| 避免使用"Get"或"Set"當前置詞|
|Field (Public, Protected, or Internal)     |Pascal| Name| |
|Field (Private)     			|Camel		| _name| 字首加上底線做為區隔 |
|Constant or Static Field     |Pascal	|Name | 與Field處理方式相同|
|Enum     						|Pascal	|EncodeType | 裡面包含選項也是使用Pascal命名法|
|Delegate or Event|Pascal|public event EventHandler LoadPlugin|全都使用 PascalCase|


## 版本發佈管理


* 版本控管號碼– 1.0.0
* 版本控管號碼說明 - (1)major.(0)minor.(0)patch
* 修正錯誤,沒有加功能 ( patch release ) • 1.0.1
* 加新功能,但不影響原本 API 運作 ( minor release ) • 1.1.0
* 大功能更新,會有破壞的變更 ( major release ) • 2.0.0	

