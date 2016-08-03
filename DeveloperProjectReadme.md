# Binodata .Net 專案開發 Read Me 手冊範本
* 為了讓每個工程師都能輕鬆與快速上手其他工程師的程式碼，需要每個工程師配合撰寫此文件
* 可以複製此檔案至自己要開發的專案根目錄
* 本文件讓公司內的工程師撰寫建置與部署文件時，皆可以參考複製並更改
* 可以參考如下方式撰寫專案建置與說明文件，與該專案維護與運行時注意事項。


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

#### Enum 程式定義
```C#
 public enum ConfigStatusEnum
 {
        [Display(Name = "Created")]
        Created = 0,

        [Display(Name = "Pending")]
        Pending = 1,

        [Display(Name = "Processing")]
        Processing = 2,

        [Display(Name = "Completed")]
        Completed = 3,

        [Display(Name = "Failed")]
        Failed = 4,
 }
```

### Firmware Status

|値(Short)  |文字顯示|
|-----------|-------|
|-1         |None   |
|0          |Created|
|1          |Pending |
|2          |Processing |
|3          |Completed |
|4          |Failed |

#### Enum 程式定義
```C#
public enum FirmwareStatusEnum
    {
        [Display(Name = "Created")]
        Created = 0,

        [Display(Name = "Pending")]
        Pending = 1,

        [Display(Name = "Processing")]
        Processing = 2,

        [Display(Name = "Completed")]
        Completed = 3,

        [Display(Name = "Failed")]
        Failed = 4,
    }
```

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

#### Enum 程式定義

```C#
public enum DeviceUseStatusEnum
    {
        /// <summary>
        /// 新機器
        /// </summary>
        [Display(Name = "New")]
        New = 0,

        /// <summary>
        /// 已指派
        /// </summary>
        [Display(Name = "In Use")]
        InUse = 1,

        /// <summary>
        /// 維護中
        /// </summary>
        [Display(Name = "RMA")]
        Maintenance = 2,

        /// <summary>
        /// 暫停使用
        /// </summary>
        [Display(Name = "Suspended")]
        Suspended = 3,

        /// <summary>
        /// 報廢
        /// </summary>
        [Display(Name = "Disposed")]
        Disposed = 4,

        /// <summary>
        /// 暫停使用
        /// </summary>
        [Display(Name = "Recalled")]
        Recalled = 5,
    }
```