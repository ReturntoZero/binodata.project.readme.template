# Binodata C Sharp Coding Rules
給Binodata工程師參考的C Sharp 開發規範

# 命名

兩種命名種類，Pascal, Camel

* Pascal


* Camel



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




## 環境

* 開發環境 Visual Stdio 2015
* 資料庫環境: SQL Server 2014
* Entity Framework 6.1.3

## 建置作業
1. 在方案上按下滑鼠右鍵，選擇 Restore Nuget Packages
2. 於Binodata.Intra 中檢查 web.config 的 連線字串

``` XML
    <connectionStrings>
        <add name="XXXConnection" connectionString="Data Source=localhost;Initial Catalog=XXX;Persist Security Info=True;User ID=sa;Password=1234567890;Connection Timeout=300;" providerName="System.Data.SqlClient" />
    </connectionStrings>
```
3. 確定資料庫連線字串是否可以連線
4. 確定資料庫連線的使用者權限是否擁有可以Create DB, Table的權限
5. 設定正確的連線字串
6. 建置
7. Run
8. 若沒有對應資料庫，資料庫與資料表格會自行產生(Entity Framework Code First 的作用)

## 建置可能遇到常發生的錯誤

1. Compile 失敗。
   * 處理方式: Nuget Restore
2. System.Data.SqlClient.SqlException: 資料庫中已經有一個名為 'XXX' 的物件
   * 處理方式: 刪除資料庫
3. 沒有足夠的權限建立資料庫
   * 處理方式 : 給予連線的使用者於資料庫中擁有Create db, table 的權限


## 雲端部署

### 雲端環境

* 資料庫: AWS RDS
* 主機: AWS EC2 (Windows Server 2012)

# .Net 套件
* 專案套件皆使用Nuget套件統一管理
* 若需要詳細版本，請參閱個專案的packages.config

# Javascript 套件
1. AutoComplete.js
   * [網站](https://goodies.pixabay.com/javascript/auto-complete/demo.html)
   * [GitHub](https://github.com/Pixabay/JavaScript-autoComplete)
   * [MIT License](http://www.opensource.org/licenses/mit-license.php)

   


# 開發

## 資料定義

### Config Status

|値(Short)  |文字顯示|
|-----------|-------|
|-1         |None   |
|0          |Created|
|1          |Pending |
|2          |Processing |
|3          |Completed |
|4          |Failed |


### Firmware Status

|値(Short)  |文字顯示|
|-----------|-------|
|-1         |None   |
|0          |Created|
|1          |Pending |
|2          |Processing |
|3          |Completed |
|4          |Failed |


### Device Use Status

|値(Short)  |文字顯示|
|-----------|-------|
|-1         |None   |
|0          |New    |
|1          |In Use |
|2          |RMA    |
|3          |Suspended |
|4          |Disposed |
|5          |Recalled |

