# Binodata C Sharp Coding Rules

說明：給Binodata工程師參考的C Sharp 開發規範

## 前言
為了讓後進工程師能夠輕鬆了解Binodata專案的寫作框架與邏輯，進而能夠維護與擴充過去專案與產品之程式碼，而規範此命名規則。此外，也能增進工程師之間的合作，讓彼此能夠交流程式碼，並快速理解其他工程師的程式邏輯，以增進合作默契與效率。

命名是軟體開發重要的基礎，好的命名可以讓人快速了解程式的目的，不用讓人還需要去看程式碼底層的實作，才知道程式要解決什麼問題。

## 命名種類介紹

兩種命名種類，Pascal, Camel

* Pascal

```<CSharp>
    HelloWorld;
```


* Camel



```<CSharp>
    helloWorld;
```



* [參考](http://www.dotblogs.com.tw/ouch1978/archive/2010/10/30/c-sharp-naming-convention.aspx)

|種類      						|命名規則  |範例 |注意事項|
|-------------------------------|---------|-----|-------|
|Project File  					|Pascal   |Math.Algorithm.csproj |  |
|Source File     				|Pascal	| RuleSetup.cs | 保持檔案名稱與Class名稱一致|
|Resource or Embedded File    	|Pascal	| TestPicture.jpg | |
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


## 各項命名規範


### 方案檔命名規範

* 方案檔命名：以公司開頭，服務或專案名稱結尾

```<CSharp>
    //Sample
    //公司.服務或專案名稱
    Binodata.EComm
```

### 專案命名規範

* Web 類型的專案：以公司開頭，中間名以服務或專案名稱，最後用Web 結尾

```<CSharp>
    //Sample
    //公司.服務名稱.Web類型
    Binodata.EComm.Web
```

* Web API 類型的專案：以公司開頭，中間名以服務或專案名稱，最後用WebAPI 結尾

```<CSharp>
    //Sample
    //公司.服務名稱.Web類型
    Binodata.EComm.WebAPI
```

* 商業邏輯層的專案：以公司開頭，中間名以服務或專案名稱，最後用Business結尾

```<CSharp>
    //Sample
    //公司.服務名稱.商業邏輯層
    Binodata.EComm.Business
```

* 服務共用模組或的專案：以公司開頭，中間名以服務或專案名稱，最後用Library結尾

```<CSharp>
    //Sample
    //公司.服務名稱.共用服務與模組
    Binodata.EComm.Library
```

* 資料庫類型的專案：以公司開頭，中間名以服務或專案名稱，最後用Entities 或 DataAccess 結尾

```<CSharp>
    //Sample
    //公司.服務名稱.資料庫類型
    Binodata.EComm.Entities
    Binodata.EComm.DataAccess
```

### 常用檔案與類別命名規範

* MVC Controller :  以Controller 結尾

```<CSharp>
    //Sample
    HomeController
```

* MVC View :  以View 結尾

```<CSharp>
    //Sample
    HomeView
```

* MVC Partial View :  底線開頭，以Partial 結尾

```<CSharp>
    //Sample
    _HomePartial
```

* 資料儲存類別 :  以Dao 結尾

```<CSharp>
    //Sample
    ProductDao
```



## 版本發佈管理


* 版本控管號碼– 1.0.0
* 版本控管號碼說明 - (1)major.(0)minor.(0)patch
* 修正錯誤,沒有加功能 ( patch release ) • 1.0.1
* 加新功能,但不影響原本 API 運作 ( minor release ) • 1.1.0
* 大功能更新,會有破壞的變更 ( major release ) • 2.0.0	

