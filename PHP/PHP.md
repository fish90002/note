## 安裝

https://www.apachefriends.org/zh_tw/index.html

- 資料夾 htdocs 下新增自己的資料夾

## 基本

變數

```PHP
$x = '123';
```

基本函數

- isset()函數是用來判斷變數是不是有存在，如果有就回傳 1(true)，如果沒有就回傳空值

- empty()函數用來判斷"值"是不是空的，如果沒有就回傳 1(true)，如果有"值"就不回傳

## 表單

<<<<<<< HEAD
**表單不能混用，methods 是什麼 $_就是什麼**
=======
>>>>>>> d089724a74ec245db7fc349310c64508dddfea2d

### 取得參數

```PHP
$_GET['表單的name'];
$_POST['表單的 name'];
```

### 表單範例

```js
// 前端
<form action="傳送到哪個PHP" method="GET&POST">
  <input type="text" name="傳送的參數" id="">
  <input type="submit" value="送出">
</form>
```

```PHP
後端
<<<<<<< HEAD
if (empty($_POST['name'])) { //如果是空值
echo ' 錯誤';
exit(); // 不在跑下面的程式
}
=======
<?php
  if (empty($_POST['傳送的參數'])) { //如果是空值
  echo ' 錯誤';
  exit(); // 不在跑下面的程式
  }

  echo $_POST&GET['傳送的參數'];
?>
>>>>>>> d089724a74ec245db7fc349310c64508dddfea2d
```

## 與 MySQL 連線

<<<<<<< HEAD
```PHP
=======
```php
<?php
>>>>>>> d089724a74ec245db7fc349310c64508dddfea2d
$servername = '';
$name = '';
$password = '';
$dbname = '';

$conn = new mysqli('serve 的名稱','帳號','密碼','database')

if ($conn->connect_error) {
   die('資料庫連線錯誤:' . $conn->connect_error); // 輸出文字後 後面的都不會執行
}
<<<<<<< HEAD

$conn->query('SET NAMES UTF8');
$conn->query('SET time_zone = "+8:00"');

=======
//database的設定
$conn->query('SET NAMES UTF8');
$conn->query('SET time_zone = "+8:00"');
?>
>>>>>>> d089724a74ec245db7fc349310c64508dddfea2d
```

## 外部連接

- 發生錯誤只會跳警告
  > - include('要連接的 php');
  > - include_once('要連接的 php');
- 程式終止執行
  > - require('要連接的 php');
  > - require_once('要連接的 php');
