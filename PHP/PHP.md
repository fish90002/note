## 安裝

https://www.apachefriends.org/zh_tw/index.html

- 資料夾 htdocs 下新增自己的資料夾

## 基本

變數

```php
$x = '123';
```

基本函數

- isset()函數是用來判斷變數是不是有存在，如果有就回傳 1(true)，如果沒有就回傳空值

- empty()函數用來判斷"值"是不是空的，如果沒有就回傳 1(true)，如果有"值"就不回傳

## 表單


### 取得參數

```PHP
$_GET['表單的name'];
$_POST['表單的 name'];
```

### 表單範例

```js
// 前端
<form action="傳送到哪個PHP" method="GET&POST">
　<input type="text" name="傳送的參數">
　<input type="submit" value="送出表單">
</form>
```

```PHP
後端
<?php
  if (empty($_POST['傳送的參數'])) { //如果是空值
  echo ' 錯誤';
  exit(); // 不在跑下面的程式
  }

  echo $_POST&GET['傳送的參數'];
?>
```

## 與 MySQL 連線

```php
$servername = '';
$name = '';
$password = '';
$dbname = '';

$conn = new mysqli('serve 的名稱','帳號','密碼','database')

if ($conn->connect_error) {
   die('資料庫連線錯誤:' . $conn->connect_error); // 輸出文字後 後面的都不會執行
}
```

## 外部連接

- 發生錯誤只會跳警告
  > - include('要連接的 php');
  > - include_once('要連接的 php');
- 程式終止執行
  > - require('要連接的 php');
  > - require_once('要連接的 php');
