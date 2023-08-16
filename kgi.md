#KGI 共銷後台專案

## 資料夾架構
主要說明有更動到的，插件部分根據每頁所需條件不同引入。
```
index.html
login_trust.html
login.html
maubtenance.html
trustRoung.html
css
  ├── style.css
└── 其餘插件.css
js
  ├── bootstrap-table-set.js
  ├── datepicker_set.js
  ├── datepicker_havedate.js
  ├── datepicker_nodate.js
  ├── style.js
  ├── watermark.js
  └── 其餘插件以及json.js
webPage
  ├──Actual_number_of_customers.html
  ├──Cash_Dividend_inquiry.html
  ├──Customer_Details.html
  ├──Customer_Information.html
  ├──Customer_Personal_details.html
  ├──Number_accounts_opened.html
  ├──Opening_progress.html
  ├──P3_announcement.html
  ├──P3_announcement_edit.html
  ├──P3_announcement_management.html
  ├──P3_Parameter_management.html
  ├──P3_Personnel_management.html
  ├──P3_Personnel_search.html
  ├──P3_Release_record.html
  ├──P3_Suspension.html
  ├──Profit_sharing_bonus.html
  ├──System_Management.html
  ├──Total_Transaction.html
  ├──Transaction_Details.html
  └──Transaction_volume_Net_fee.html

```
---
## 共用的CSS
### style.css
所有的樣式修改都在此處。
如果有需要複用的，建議直接參考原本已完成的html檔案直接複製即可。
## 共用的JS
### bootstrap-table-set.js
#### 1. 初始化表格
`$("{table id}").bootstrapTable({ ... });` 
- 用於初始化表格，並設置其配置選項。
#### 2. 選項配置
##### a. 數據源
- `url: "../js/Opening_progress_data.json"`: {設置數據源的URL}
- `totalField: "total"`: {指定總記錄數的字段名}
- `dataField: "datas"`: {指定數據數組的字段名}
##### b. 固定列
- `fixedColumns: true`: {啟用固定列}
- `height: 800`: {設定表格高度}
- `fixedNumber: isSmallScreen ? 1 : 6`: {如果視窗寬度小於 1080px，固定列數設為 1，否則設為 5}
##### c. 查詢參數
- `queryParams: function (params) { ... }`: {添加自定義查詢參數}
##### d. 分頁和格式
- `formatDetailPagination: function (totalRows) { ... }`: {自定義分頁字串顯示為中文}
- `sidePagination: "client"`: {客戶端分頁}
- `pagination: true`: {啟用分頁}
- `pageSize: 25`: {單頁筆數}
##### e. 事件處理(此處列出所有，並不一定都會使用)
- `onLoadSuccess: function (data) { ... }`: {數據加載成功後的回調，例如合併單元格}
- `onClickCell: function (field, value, row, $element) { ... }`: {點擊單元格的事件處理，例如顯示lightbox}
-  `formatDetailPagination: function (totalRows) { return "總共" + totalRows + "筆"; }`: {自定義分頁字串顯示為中文。這個函數會將分頁信息的格式更改為顯示“總共N筆”這樣的字串，其中N是總行數。}

- `onClickCell`: 有使用到的函數

```
彈出燈箱
function lightbox() {
  $(".kgi_lightbox_btn").trigger("click");
}
```

- `onLoadSuccess`:有使用到的函數
```
欄位合併設定
欄位合併設定的目的是為了使表格的特定欄位具有相同的值進行合併，以便更好地呈現數據。
它可以合併單元格，無論是水平合併（左右合併）還是垂直合併（上下合併），都是基於數據的特定屬性。
合併的欄位包括 "CustName"、"emp_id"、"name"、"org_name"、"dept_level_name"、"Id"、"Mobile"、"AccountType" 等。

function mergeCells(data, colspan, target) {
    var last_WorkspaceId = "";
    for (var i = 0; i < data.length; i++) {
      if (data[i].rowspan > 1 && last_WorkspaceId != data[i].WorkspaceId) {
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "CustName",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "emp_id",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "name",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "org_name",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "dept_level_name",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "Id",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "Mobile",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
        // Cash_Dividend_inquiry欄位合併
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "AccountType",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
      }
      last_WorkspaceId = data[i].WorkspaceId;
    }
    // 其他單獨上下合併
    for (var i = 0; i < data.length; i++) {
      if (data[i].rowspan_kind > 1) {
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "kind_desc",
          colspan: 1,
          rowspan: data[i].rowspan_kind,
        });
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "kind_desc",
          colspan: 1,
          rowspan: data[i].rowspan_kind,
        });
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "Kind",
          colspan: 1,
          rowspan: data[i].rowspan,
        });
      }
    }
    // 其他單獨左右合併
    for (var i = 0; i < data.length; i++) {
      if (data[i].colspan > 1) {
        target.bootstrapTable("mergeCells", {
          index: i,
          field: "kind_desc",
          colspan: data[i].colspan,
          rowspan: 1,
        });
      }
    }
  }
```
```
含有特定字就執行特定動作
檢查移除: 函數會檢查`fix_record`字段是否包含"移除"這個字串。
格式化移除條目: 如果包含"移除"，則對`value`添加紅色字體和刪除線效果，以視覺方式表示該條目已被移除。
返回原始值: 如果不包含"移除"，則返回字段的原始值，不進行任何格式化。

function formatIfRemoved(value, row) {
        if (row.fix_record.includes("移除")) {
          return '<span style="color:red;text-decoration:line-through;">' + value + "</span>";
        } else {
          return value;
        }
      }
```
#### 2. 參考資料
[bootstrap table](https://getbootstrap.com/docs/4.1/content/tables/)

### datepicker_set.js
#### 日期選擇器設定與功能
中文語系設定，透過jQuery UI的datepicker進行設定，提供以下特性：
- 語系設定: 將日期選擇器設定為中文顯示。
- 日期選擇器套用: 將日期選擇器套用到指定元素上。
- 刪除按鈕功能: 在日期選擇器中加入一個清除按鈕，用於清除選擇的日期。

```
//設定中文語系
$.datepicker.regional['zh-TW'] = {
    dayNames: ["星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"],
    dayNamesMin: ["日", "一", "二", "三", "四", "五", "六"],
    monthNames: ["一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月"],
    monthNamesShort: ["一月", "二月", "三月", "四月", "五月", "六月", "七月", "八月", "九月", "十月", "十一月", "十二月"],
    prevText: "上月",
    nextText: "次月",
    weekHeader: "週"
};

//將預設語系設定為中文
$.datepicker.setDefaults($.datepicker.regional["zh-TW"]);
```
日期選擇器套用
```
//套用到表單
$(function () {
    $("#datepicker_Start").datepicker({ dateFormat: 'yy/mm/dd' });
});

```
刪除按鈕功能
```
// 刪除按鈕
function datepickerAddClearBtn() {
    var old_fn = $.datepicker._updateDatepicker;
    $.datepicker._updateDatepicker = function (inst) {
        old_fn.call(this, inst);
        var buttonPane = $(this).datepicker("widget").find(".ui-datepicker-buttonpane");

        $("<button type='button' class='ui-datepicker-clean ui-state-default ui-priority-primary ui-corner-all'>清除</button>").appendTo(buttonPane).click(function (ev) {
            $.datepicker._clearDate(inst.input);//清除選擇的日期
            $.datepicker._hideDatepicker();//關閉Datepicker
        });
    };
}
datepickerAddClearBtn();

```
### datepicker_havedate.js
日期選擇器設定如果有需要含有月份日期，就引用這個
### datepicker_nodate.js
日期選擇器設定如果只含有月份，就引用這個

---

## 其餘插件功能標示

### JavaScript Libraries

#### **jQuery**
- `jquery-3.6.1.js`

#### **jQuery UI**
- `jquery-ui.js`

#### **jQuery datepicker**
- `datepicker_havedate.js`
- `datepicker_nodate.js`
- `datepicker_set.js`

#### **Bootstrap**
- `bootstrap.bundle.min.js`

#### **彈出視窗 (Modal)**
- `fancybox.umd.js`

#### **Bootstrap Table**
- `bootstrap-table.js`
- `bootstrap-table-fixed-columns.js`
- `bootstrap-table-set.js`

#### **浮水印 (Watermark)**
- `moment.js`
- `watermark.js`

#### **頁面相關**
- `style.js`

### CSS Stylesheets

#### **jQuery UI**
- `jquery-ui.css`

#### **Bootstrap**
- `bootstrap-grid.min.css`

#### **Bootstrap Table**
- `bootstrap-table-fixed-columns.css`
- `bootstrap-table.css`

#### **彈出視窗 (Modal)**
- `fancybox.css`

#### **通用樣式**
- `reset.css`
- `style.css`

