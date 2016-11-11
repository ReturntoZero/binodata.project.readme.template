# Binodata Project Readme Template
給公司工程師參考撰寫專案說明文件Readme範本，工程師撰寫專案Readme 文件，可以參考此文件或直接複製此文件，並修改符合專案的說明。

# Binodata .Net 專案開發 Read Me 手冊範本說明與使用方式
* 為了讓每個工程師都能輕鬆與快速上手其他工程師的程式碼，需要每個工程師配合撰寫此文件
* 可以複製此檔案至自己要開發的專案根目錄
* 本文件讓公司內的工程師撰寫建置與部署文件時，皆可以參考複製並更改
* 可以參考如下方式撰寫專案建置與說明文件，與該專案維護與運行時注意事項。


## 專案需求說明
* [請參考資料夾-XXX/ooo/02.需求與架構分析](url)

## 開發詳細規格
* [請參考資料夾-XXX/ooo/02.需求與架構分析](url)

## 專案相關工具與Web API/Services使用方式
* [請參考資料夾-XXX/ooo/03.開發](url)

## 開發規範
* [請參考資料夾-XXX/ooo/開發規範](url)

## 方案檔資料夾說明範例

### Core
* Core 資料夾專門放主要商業行為邏輯，共用的專案。

### DataAccess

* DataAccess 資料夾專門放與資料庫相關的處理專案

### Solution Items

* Solution Items 資料夾專門放方案檔的說明，README.md

### Test

* Test 資料夾專門放測試專案，README.md


### Web

* Web 資料夾專門放Web，Web Api專案，README.md

## 專案檔說明

|專案名稱                 |說明                       |備註|
|-----------------------|--------------------------|--|
|Binodata.QQOO.Member.Web|娃娃機會員雲端管理系統專案    | |
|Binodata.QQOO.Admin.Web|娃娃機裝置管理系統專案| |
|Binodata.IoT.Library|IoT 系統所需要使用的專案            |於另一個Git儲存庫，[連結](https://bitbucket.org/binodataiot/binodata.iot.library)|



## 系統環境

* 資料庫環境: SQL Server 2014

## 開發環境

* 開發環境 Visual Stdio 2015

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

## 套件說明

### .Net 套件
* 專案套件皆使用Nuget套件統一管理
* 若需要詳細版本，請參閱個專案的packages.config

### Javascript 套件
1. AutoComplete.js
   * [網站](https://goodies.pixabay.com/javascript/auto-complete/demo.html)
   * [GitHub](https://github.com/Pixabay/JavaScript-autoComplete)
   * [MIT License](http://www.opensource.org/licenses/mit-license.php)


## Web API服務使用範例

### 取得Binodata 服務資料

* 取得Binodata 服務資料的Web API 的URL

```javascript
http://localhost/service/api/binodata/binoserver
```

* 回傳Json資料範例

```javascript
[
  {
    "ServiceCode": 1,
    "ServicName": "BinodataMath"
  },
  {
    "ServiceCode": 2,
    "ServicName": "BinodataDB"
  },
  {
    "ServiceCode": 3,
    "ServicName": "BinodataCloud"
  }
  
]
```

## Library API 使用範例

### 方法名稱

#### 用途描述

* 加法計算
* 回傳計算結果

#### Sample Code

```cs
int c = Calculator.Add(a, b);
```
