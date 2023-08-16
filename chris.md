# 0815新增/改動的所有資料夾架構
```
layouts
├── dashboard
│   ├── CustomComponents
│   │   ├── Custom-album.js
│   │   ├── Custom-CardHeader.js
│   │   ├── Custom-Chip.js
│   │   ├── Custom-ColorPicker.js
│   │   ├── Custom-datePicker.js
│   │   ├── Custom-imageUpload.js
│   │   ├── Custom-Model.js
│   │   ├── Custom-Select.js
│   │   ├── Custom-subTitle.js
│   │   ├── Custom-switch.js
│   │   ├── Custom-Tabs-valueCard.js
│   │   ├── Custom-tabs.js
│   │   ├── Custom-TextEditer.js
│   │   ├── Custom-TextField.js
│   │   ├── Custom-timePicker.js
│   │   └── Custom-upLoad.js
│   ├── titleBreadcrumbs.js
│   └── config.js
│
├── page
│   ├── addActivity
│   │   ├── tab_0
│   │   │   ├── AttributesTable.js
│   │   │   ├── CardImages.js
│   │   │   ├── Category.js
│   │   │   ├── Feature.js
│   │   │   ├── Information.js
│   │   │   ├── Notify.js
│   │   │   ├── Plan.js
│   │   │   └── TopImages.js
│   │   ├── tab_1
│   │   │   ├── moneySetting.js
│   │   │   ├── PlanSetting.js
│   │   │   ├── saleDate.js
│   │   │   ├── SignupSetting.js
│   │   │   ├── specialDate.js
│   │   │   ├── specialTable.js
│   │   │   └── table-Collapsible.js
│   │   ├── tab_2
│   │   │   └── AboutEvent.js
│   │   ├── tab_0.js
│   │   ├── tab_1.js
│   │   └── tab_2.js
│   └── IndexActivity
│       └── table-Collapsible.js
│
pages
├── activity
│   ├── addActivity
│   │   └── addPlan.js
│   ├── addActivity.js
│   └── index.js
styles
├── globo.js
└── globo.css

```
後續將會根據此架構依序介紹各個資料夾以及檔案的用途

---
# layouts 資料夾
## dashboard 資料夾
此資料夾包含所有與儀表板相關的組件和配置。
###  config.js
此檔案為路由設定。

### titleBreadcrumbs.js
此文件包含麵包屑導航組件，用於顯示當前頁面的層次結構。

### CustomComponents 子資料夾
此子資料夾包含所有自定義組件。每個組件都放在其自己的文件中。

####通用元件

- [`Custom-album.js`](#custom-albumjs): 相簿選取功能組件，通常放在"Custom-imageUpload.js"配合使用。
- [`Custom-CardHeader.js`](#custom-cardheaderjs): 頁面頭部的命名組件。
- [`Custom-Chip.js`](#custom-chipjs): 標籤創建的組件。
- [`Custom-ColorPicker.js`](#custom-colorpickerjs): 顏色選取器。
- [`Custom-datePicker.js`](#custom-datepickerjs): 日期選取器。
- [`Custom-imageUpload.js`](#custom-imageuploadjs): 上傳圖片相關組件。
- [`Custom-Model.js`](#custom-modeljs): 彈出視窗相關組件。
- [`Custom-Select.js`](#custom-selectjs): 下拉選單相關組件。
- [`Custom-subTitle.js`](#custom-subtitlejs): 小標題。
- [`Custom-switch.js`](#custom-switchjs): 切換狀態的按鈕(IOS樣式)。
- [`Custom-Tabs-valueCard.js`](#custom-tabs-valuecardjs): tab分頁內區塊所使用的小標題與註解組件。
- [`Custom-Tabs.js`](#custom-tabsjs): tab組件。
- [`Custom-TextEditer.js`](#custom-textediterjs): 文字編輯器組件。
- [`Custom-TextField.js`](#custom-textfieldjs): 輸入框組件。
- [`Custom-timePicker.js`](#custom-timepickerjs): 時間選擇器。
- [`Custom-upLoad.js`](#custom-uploadjs): 上傳檔案組件。
#### 特殊元件
- [`table-Collapsible.js`](#特殊表格): 表格基底(根據顯示欄位不同要設定不同的內容)
## Page 資料夾
此資料夾包含應用程序的所有頁面組件。
### addActivity 子資料夾
此子資料夾包含"新增行程"頁面的所有相關組件。
- `tab_0.js`: 行程資料。
- `tab_0` tab_0.js所用到的組件:
  - `AttributesTable.js`: 活動類別的屬性一覽表組件。
  - `Category.js`: 活動類別組件。
  - `Information.js`: 行程資料組件。
  - `Feature.js`: 行程特色組件。
  - `Plan.js`: 是否加入行銷活動方案組件。
  - `Notify.js`: 行前通知組件。
  - `CardImages.js`: 產品卡片照片組件。
  - `TopImages.js`: 上方輪播照片組件。
- `tab_1.js`: 方案選擇。
- `tab_1` tab_1.js所用到的組件:
  - `table-Collapsible.js`: 方案選擇表格
  
  - (注意:此處較特別，以下的元件是用在"新增方案") 新增方案的位置在 `pages/activity/addActivity/addPlan.js` 由於是獨立頁面，所以必須單獨一頁，只是還是歸類在新增行程的tab系統下。
  - `PlanSetting.js`: 方案設定組件。
  - `moneySetting.js`: 費用設定組件。
  - `SignupSetting.js`: 報名設定組件。
  - `SaleDate.js`: 銷售日期組件。
  - `SpecialDate.js`: 特殊日設定組件。
  - `Specialtable.js`: 特殊日設定的表格組件。
- `tab_2.js`: 關於活動。
- `tab_2` tab_0.js所用到的組件:
  - `AboutEvent.js`: 關於活動組件。
### IndexActivity 子資料夾
- `table-Collapsible.js`: 行程列表的表格組件。

---
# pages 資料夾
## activity 資料夾
此資料夾包含所有跟行程管理有關的相關畫面。
### addActivity.js 
新增行程的所有畫面整理
### addActivity 子資料夾
此資料夾處理新增行程內需要獨立一頁的畫面。
- `addPlan.js` tab_1.js所用到的"新增方案"畫面，元件放置於tab_1內:

### index.js 
行程列表的所有畫面整理

---

#共用元件功能說明
## CustomAlbum.js 
[返回](#通用元件)
此組件提供了相簿選取功能，允許用戶選擇、新增相簿並選擇圖片。

### Props
- `onConfirmSelection`: 函數，當用戶點擊"確認選取"按鈕後，會被調用並傳遞選取的圖片。

### 功能描述
1. **預設圖片列表**: 包括預設的圖片URL和名稱。
2. **選擇相簿**: 用戶可以從下拉列表中選擇已存在的相簿。
3. **新增相簿**: 用戶可以點擊"新增相簿"按鈕來創建新的相簿。(尚未製作)
4. **選擇圖片**: 顯示預設的圖片列表，用戶可以通過點擊圖片來選擇或取消選擇。
5. **確認選取**: 用戶可以點擊"確認選取"按鈕來確認選擇的圖片。選擇的圖片將通過 `onConfirmSelection` 函數傳遞給父組件。

### 狀態管理
- `selectedImages`: 一個包含選擇狀態的布爾數組，用於追踪每個圖片是否被選擇。
- `albums`: 存儲所有相簿名稱的數組。
- `selectedAlbum`: 目前選擇的相簿名稱。

### 樣式
- 使用了自定義的按鈕樣式如 `buttonStyle_green` 和 `buttonStyle_blue`。
- 選擇的圖片將以綠色輪廓突出顯示。

### 使用示例
```
<CustomAlbum onConfirmSelection={handleAlbumSelection} />
```


---
## Custom-CardHeader.js 
[返回](#通用元件)
此組件為卡片的標頭部分，可以包括標題和最多兩個按鈕。
### Props
- `title`: 字符串，卡片標題。如果 `title` 不存在，整個標題區塊將不會顯示。
- `button1Label`: 字符串，第一個按鈕的標籤文字。
- `button2Label`: 字符串，第二個按鈕的標籤文字。
- `onButton1Click`: 函數，當第一個按鈕被點擊時的回調函數。
- `onButton2Click`: 函數，當第二個按鈕被點擊時的回調函數。

### 功能描述
1. **卡片標題**: 顯示由 `title` 傳入的標題文字，如果 `title` 為空或不存在，整個標題區塊將不會顯示。
2. **第一個按鈕**: 根據 `button1Label` 的存在與否來控制顯示，並且按鈕內含有一個加號圖標。點擊時觸發 `onButton1Click` 回調。
3. **第二個按鈕**: 根據 `button2Label` 的存在與否來控制顯示，並且按鈕內含有一個刷新圖標。點擊時觸發 `onButton2Click` 回調。

### 樣式
- 使用了自定義的按鈕樣式如 `buttonStyle_green`。
- 根據 `title` 是否存在來設置不同的 `padding` 值。

### 使用示例
```
<CustomCardHeader
  title="標題示例"
  button1Label="新增"
  button2Label="刷新"
  onButton1Click={() => console.log('新增按鈕點擊')}
  onButton2Click={() => console.log('刷新按鈕點擊')}
/>
```
---

## Custom-Chip.js 
[返回](#通用元件)
此組件允許用戶通過模態窗口界面添加和刪除標籤，並以視覺化的方式呈現當前的標籤列表。
### Props
- `title`: 字符串，用於模態窗口的標題。
- `labelName`: 字符串，用於標籤名稱的標題。
- `maxCharacters`: 字符串，用於表示字符限制的提示。
- `label`: 字符串，用於自定義文本字段的標籤。

### 功能描述
1. **標籤列表**: 顯示當前添加的標籤。
2. **新增標籤**: 點擊加號圖標可以打開模態窗口，用戶可以在其中輸入新標籤並點擊“新增”按鈕來添加。
3. **刪除標籤**: 用戶可以點擊標籤上的刪除圖標來刪除特定標籤。
4. **字符限制**: 在添加新標籤時，字符限制由 `maxCharacters` 屬性控制。

### 樣式
- 使用了自定義的按鈕樣式，如 `buttonStyle_green`。
- 標籤以 `Chip` 元件形式呈現，並排列在一個 `Paper` 元件中。

### 使用示例
```
<CustomChip
  title="添加新標籤"
  labelName="標籤名稱"
  maxCharacters="最多7個字符"
  label="標籤"
/>
```
---
## Custom-ColorPicker.js 
[返回](#通用元件)
此組件提供了一個顏色選擇器，允許用戶選擇和查看特定的顏色值。

### Props
此組件不接受任何特定的props。

### 功能描述
1. **顏色顯示和選擇**: 顏色選擇器以一個按鈕的形式呈現當前選擇的顏色。當用戶點擊按鈕時，會彈出一個包含 `SketchPicker` 的彈出窗口，允許用戶選擇顏色。
2. **顏色值顯示**: 顏色選擇器旁邊顯示了當前選擇的顏色的16進制值。

### 樣式
- 按鈕的背景色為當前選擇的顏色，文字顏色為白色。
- 16進制顏色值顯示在一個具有灰色邊框的區域中。

### 使用示例
```
<ColorPicker></ColorPicker>
```
---

## Custom-datePicker.js 
[返回](#通用元件)
此組件提供了一個日期選擇器，允許選擇日期並對選擇的日期進行驗證。

### Props
- `isDateRequired`: 布爾值，如果為`true`，則日期為必填字段。

### 功能描述
1. **選擇日期**: 用戶可以通過點擊輸入字段來打開日期選擇器並選擇日期。
2. **驗證**: 如果`isDateRequired`為`true`，當用戶未選擇日期並且輸入字段失去焦點時，將顯示錯誤消息。
3. **本地化**: 日期選擇器使用中文化。

### 樣式
- 如果日期為必填且未選擇，則輸入框將具有紅色邊框，並顯示紅色的錯誤消息。

### 使用示例
```
<CustomDatePicker isDateRequired={true}></CustomDatePicker>
```
---
## Custom-imageUpload.js 
[返回](#通用元件)
此組件用於上傳和選擇圖片，並顯示選定的圖片。

### Props
- `images`: 數組，包含當前選定的圖片。
- `setImages`: 函數，用於設置選定的圖片。
- `inputId`: 字符串，用於上傳按鈕的 HTML id 屬性。

### 功能描述
1. **上傳圖片**: 通過點擊 "上傳圖片" 按鈕來上傳圖片。
2. **相簿選取**: 通過點擊 "相簿選取" 按鈕從相簿中選擇圖片。
3. **顯示圖片**: 選定的圖片將顯示，並附有圖片名稱和刪除按鈕。
4. **刪除圖片**: 通過點擊每個圖片下的刪除按鈕來刪除圖片。
5. **空間使用情況**: 顯示總空間和剩餘空間。

### 樣式
- 使用了自定義的按鈕樣式，如 `buttonStyle_green`。
- 圖片排列在一個網格中，並帶有方框和刪除按鈕。

### 使用示例
```
<CustomimageUpload
  images={images}
  setImages={setImages}
  inputId="image-upload"
/>
```
---
## Custom-Model.js 
[返回](#通用元件)
此組件提供一個可自定義的彈出視窗元件，用於顯示額外內容或選項。

### Props
- `isOpen`: 布爾值，用於控制模態窗口的開啟/關閉。
- `linkText`: 字符串或元素，用作觸發模態窗口的鏈接文本。
- `linkStyle`: 對象，用於定義觸發鏈接的樣式。
- `title`: 字符串，用於模態窗口的標題。
- `children`: 元素，將在模態窗口內部呈現的內容。
- `onOpen`: 函數，當觸發鏈接被點擊時將被調用。
- `onClose`: 函數，當模態窗口被關閉時將被調用。

### 功能描述
1. **打開/關閉**: 通過點擊觸發鏈接來打開模態窗口，並通過外部點擊或關閉按鈕來關閉。
2. **自定義內容**: 可以在模態窗口內呈現任何自定義內容。

### 樣式
- 位置居中，具有自定義寬度和最大高度。
- 可滾動的內容區域。
- 根據需要，可以通過 `linkStyle` prop 自定義觸發鏈接的樣式。

### 使用示例
```
<CustomModal
  isOpen={isOpen}
  linkText="打開視窗"
  title="自定義視窗"
  linkStyle={{ }}
  onOpen={() => setIsOpen(true)}
  onClose={() => setIsOpen(false)}
>
  <p>這是模態窗口的內容。</p>
</CustomModal>
```
---
## Custom-Select.js 
[返回](#通用元件)
此組件提供一個可自定義的下拉選擇框，支持自動寬度、錯誤處理、必填選項等功能。
### Props
- `options`: 對象數組，表示選擇器的可選項。每個對象包括 `label` 和 `value` 屬性。
- `defaultOption`: 字符串，表示選擇器的初始選項。
- `label`: 字符串，表示選擇器的標籤。
- `onChange`: 函數，當選擇改變時被調用，並將新選擇的值作為參數。
- `required`: 布爾值，表示是否必選。預設為 `false`。
- `customLabel`: 字符串，表示自定義標籤的文本。
- `disabled`: 布爾值，表示是否禁用選擇器。預設為 `false`。

### 功能描述
1. **自動寬度**: 此選擇器可以自動調整其寬度以適合其內容。
2. **錯誤處理**: 如果選擇器被標記為必填，並且在失去焦點時沒有選擇值，則會顯示錯誤。
3. **自定義標籤**: 可以提供自定義標籤，將其顯示在選擇器上方。

### 使用示例
```
<CustomSelectAutoWidth
  options={[
    { label: "選項1", value: "option1" },
    { label: "選項2", value: "option2" }
  ]}
  defaultOption="option1"
  label="選擇選項"
  onChange={(value) => console.log(value)}
  required={true}
  customLabel="自定義標籤"
/>
```
## Custom-subTitle.js 
[返回](#通用元件)
此組件用於顯示一個副標題，並可選擇性地添加一串提示。

### Props
- `title`: 字符串，表示副標題的主要文字內容。
- `limit`: 字符串，表示副標題旁邊的限制或附加信息。以小字體和灰色顯示。

### 功能描述
`SubTitle` 組件用於顯示帶有可選限制提示的副標題。限制提示以較小的字體和灰色顯示，位於副標題的右側。

### 使用示例
```
<SubTitle title="副標題文字" limit="限制提示" />
```
---
## Custom-switch.js 
[返回](#通用元件)

此組件用於創建一個自定義的 iOS 風格開關元件。

### 主要組件
- `IOSSwitch`: 一個帶有自定義樣式的開關元件。

### 功能描述
`CustomizedSwitches` 組件提供了一個可切換的開關元件，具有 iOS 風格的外觀和感覺。它允許用戶在兩個不同的狀態之間切換。

### 使用示例
```
<CustomizedSwitches></CustomizedSwitches>
```
---
## Custom-Tabs-valueCard.js 
[返回](#通用元件)
此組件用於創建一個具有可選副標題的外框卡片。

### Props
- `title`: (必填) 卡片的主標題。
- `subtitle`: (可選) 卡片的副標題。如果未提供，則不會顯示副標題部分。
- `children`: 主要內容。

### 主要組件
- `Box`: 用於包裝卡片，並設置最小寬度和外邊距。
- `Card`: 主卡片組件，具有外框變體。
- `CardContent`: 用於包裝卡片內容。
- `Typography`: 用於呈現卡片的標題、副標題和主要內容。

### 使用示例
```
<OutlinedCard title="卡片標題" subtitle="卡片副標題">
  卡片的主要內容
</OutlinedCard>
```
---
## Custom-Tabs.js 
[返回](#通用元件)
此組件用於創建標籤欄，每個標籤可以有標籤文字和完成狀態的圖標。

### Props

- `labels`: (必填) 一個對象的陣列，包括每個標籤的標籤和完成狀態。例如：`[{ label: 'Tab 1', completed: true }, { label: 'Tab 2', completed: false }]`。
- `value`: (必填) 當前選定標籤的索引。
- `onChange`: (必填) 處理標籤更改的函數。

### 主要組件
- `Box`: 用於包裝標籤欄。
- `Tabs`: MUI 的標籤組件，用於創建可滾動的標籤。
- `Tab`: 用於創建單個標籤。

### 樣式
- 完成狀態圖標：綠色表示完成，紅色表示未完成。

### 使用示例
```
<ScrollableTabsButtonAuto
  labels={[
    { label: 'Step 1', completed: true },
    { label: 'Step 2', completed: false }
  ]}
  value={0}
  onChange={(event, newValue) => setValue(newValue)}
/>
```
---
## Custom-TextEditer.js 
[返回](#通用元件)
此組件提供了一個基於 `react-quill` 的自定義富文本編輯器。

### Props
- `placeholder`: (可選) 一個 HTML 字串，作為編輯器的佔位符文本。

### 狀態
- `editorHtml`: 存儲當前編輯器中的 HTML。
- `isFocused`: 一個布爾值，表示編輯器是否處於焦點狀態。

### 方法
- `handleChange(html)`: 處理編輯器內容變化的函數。
- `handleFocus()`: 處理編輯器獲得焦點的函數。
- `handleBlur()`: 處理編輯器失去焦點的函數。

### 附加功能
- 佔位符：當編輯器為空且未聚焦時，會顯示 `placeholder` 屬性作為佔位符。
- 字數統計：在編輯器底部顯示當前的字數。

### 使用示例
```
<CustomTextEditor placeholder="<p>請在此輸入內容...</p>" />
```
---
## Custom-TextField.js 
[返回](#通用元件)
`CustomTextField` 是一個自定義文本字段組件，基於 MUI 的 `TextField` 組件。

### Props

- `label`: (必需) 文本字段的標籤。
- `id`: (必需) 文本字段的 ID。
- `required`: (可選) 布爾值，指定文本字段是否必填。預設為 `false`。
- `maxLength`: (可選) 整數，指定文本字段的最大字符長度。
- `multiline`: (可選) 布爾值，指定文本字段是否多行。預設為 `false`。
- `...other`: 其他通過給 MUI `TextField` 的任何 props。

### 狀態
- `value`: 存儲文本字段的當前值。
- `error`: 布爾值，表示文本字段是否有錯誤。

### 方法
- `handleChange(event)`: 處理文本字段值的更改。
- `handleBlur()`: 處理文本字段失去焦點事件。

### 使用示例

```
<CustomTextField
  label="姓名"
  id="name"
  required={true}
  maxLength={50}
  multiline={false}
/>
```
---
## Custom-timePicker.js 
[返回](#通用元件)

`ResponsiveTimePickers` 是一個具有時間選擇和時間標籤功能的組件。

### Props

- `enableAddButton`: (可選) 布爾值，指定是否啟用「新增時間」按鈕。預設為 `true`。
- `enableChips`: (可選) 布爾值，指定是否啟用時間標籤。預設為 `true`。
- `isTimeRequired`: (可選) 布爾值，指定時間是否為必填。預設為 `false`。

### 狀態

- `selectedDate`: 存儲當前選擇的時間。
- `timeChips`: 存儲所有添加的時間標籤。
- `error`: 存儲錯誤信息或布爾值，表示是否有錯誤。
- `isOpen`: 布爾值，表示時間選擇器是否打開。

### 方法

- `handleAddClick()`: 新增選擇的時間到標籤。
- `handleDateChange(date)`: 處理選擇的時間更改。
- `handleClose()`: 關閉時間選擇器。
- `handleOpen()`: 打開時間選擇器。
- `handleDelete(timeToDelete)`: 刪除指定的時間標籤。

### 使用示例

```
<ResponsiveTimePickers
  enableAddButton={true}
  enableChips={true}
  isTimeRequired={false}
/>
```
---
## Custom-upLoad.js  
[返回](#通用元件)
`CustomUpLoad` 是一個用於上傳、下載和刪除檔案的組件。

### 狀態

- `file`: 存儲當前選擇的檔案。

### 方法

- `handleFileChange(event)`: 處理檔案選擇變更。
- `handleDelete()`: 刪除當前選擇的檔案。
- `handleDownload()`: 下載當前選擇的檔案。

### 使用示例

```
<CustomUpLoad></CustomUpLoad>
```
---
## table-Collapsible.js 
#### 特殊表格
[返回](#特殊元件)

`table-Collapsible` 是一個具有排序、分頁、刪除以及自定義樣式的表格組件。它使用了 MUI 和 Dnd Kit。
### 狀態和方法

#### 狀態

- `page`: 當前頁碼。
- `rowsPerPage`: 每頁的行數。
- `sortedRows`: 排序後的行數據。

#### 方法

- `handleChangePage(event, newPage)`: 處理頁碼變更。
- `handleChangeRowsPerPage(event)`: 處理每頁行數變更。
- `handleDragEnd({ active, over })`: 處理拖放結束事件。
- `handleDeleteRow(rowId)`: 刪除指定的行。

### 使用示例

```
<StickyHeadTable rows={rows} columns={columns} />
```
另外說明：如果不需要排序功能就將Dnd kit 的部分移除
page / IndexActivity / table-Collapsible.js << 有排序(dnd)的版本
page / addActivity / tab_1 / table-Collapsible.js << 無排序(dnd)的版本






