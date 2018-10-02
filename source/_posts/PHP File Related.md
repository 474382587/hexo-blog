---
title: PHP File Related
date: 2018-09-30 10:59:07
tags: [PHP]
---

# File Related Functions

---

```php
// this is a helper function to create file
<?php
  /**
  * Create file
  * @method createFile
  * @param string    $fileName
  * @return boolean    true | false
  */
  function createFile(string $fileName) {
    // check if file exist
    if(file_exists($fileName)) {
      return false;
    }
    if(file_exsists(dirname($fileName))) {
      // create directory/ multiple level
      mkdir(dirname($fileName), 0777, true);
    }
    if(touch($fileName)) {
      return true;
    }
    else {
      return false;
    }
  }
?>
```

---

```php
// this is a helper function to delete file
<?php
  /**
  * Delete file
  * @method deleteFile
  * @param string    $fileName
  * @return boolean    true | false
  */
  function deleteFile(string $fileName) {
    // check if file exist and have access to delete
    if(!file_exists($fileName) || !is_writeable($fileName)) {
      return false;
    }
    if(unlink($fileName)) {
      return true;
    }
    else {
      return false;
    }
  }
?>
```

---

```php
// this is a helper function to copy file
<?php
  /**
  * Copy file
  * @method copyFile
  * @param string $fileName  string $dest
  * @return boolean    true | false
  */
  function copyFile(string $fileName, string $dest) {
    // check if destination is a directory, if not, create one
    if(!is_dir($dest)) {
      mkdir($dest, 0777, true);
    }
    $destName = $dest.DIRECTORY_SEPARATOR.basename($fileName);
    if(file_exisits($destName)) {
      return false;
    }
    if(copy($fileName, $destName)) {
      return true;
    }
    else {
      return false;
    }
  }
?>
```

---

```php
// this is a helper function to rename file
<?php
  /**
  * Rename file
  * @method renameFile
  * @param string $fileName  string $newName
  * @return boolean    true | false
  */
  function copyFile(string $fileName, string $newName) {
    // check if file exist
    if(!if_file($fileName)) {
      return false;
    }
    $path = dirname($fileName);
    $destName = $path.DIRECTORY.SEPARATOR.$newName;
    if(is_file($destName)) {
      return false;
    }
    if(rename($fileName, $newName)) {
      return true;
    }
    else {
      return false;
    }
  }
?>
```

---

```php
// this is a helper function to cut file
<?php
  /**
  * Cut file
  * @method cutFile
  * @param string $fileName  string $dest
  * @return boolean    true | false
  */
  function cutFile(string $fileName, string $dest) {
    // check if file exist
    if(!if_file($fileName)) {
      return false;
    }
    if(!is_dir($dest)) {
      mkdir($dest, 0777, true);
    }
    $destName = $dest.DIRECTORY.SEPERATOR.basename($fileName);
    if(is_file($destName)) {
      return false;
    }
    if(rename($fileName, $destName)) {
      return true;
    }
    else {
      return false;
    }
  }
?>
```

---

```php
<?php
  /**
  * @method getFileInfo
  * @param String $fileName
  * @return Array contains info of the file
  */
  function getFileInfo(string $fileName) {
    if(!is_file($fileName) || !is_readable($fileName)) {
      return false;
    }
    return [
      'atime' => date("Y-m-d H:i:s", fileatime($fileName)),
      'mtime' => date("Y-m-d H:i:s", filemtime($fileName)),
      'ctime' => date("Y-m-d H:i:s", filectime($fileName)),
      'size' => filesize($fileName),
      'type' => filetype($fileName)
    ]
  }
?>
```

---

```php
<?php
  /**
  * Convert Bit to Byte
  * @method ConvertToByte
  * @param String $byte string $precision, default as 2 digits
  * @return int byte
  */
  function ConvertToByte(int $byte, int $precision = 2) {
    $kb = 1024;
    $mb = 1024 * $kb;
    $gb = 1024 * $mb;
    $tb = 1024 * $gb;
    if($byte < $kb) {
      return $byte.'B';
    }
    else if ($byte < $mb) {
      return round($byte / $kb, $precision).'$KB';
    }
    else if ($byte < $gb) {
      return round($byte / $mb, $precision).'$MB';
    }
    else if ($byte < $tb) {
      return round($byte / $gb, $precision).'GB';
    }
    else {
      return round($byte / $tb, $precision).'TB';
    }
  }
?>
```

---

```php
<?php
  /**
  * read content from file
  * @method readFile
  * @param string $fileName
  * @return file content
  */
  function readFile(string $fileName) {
    if(is_file($fileName) && is_readable($fileName)) {
      return file_get_contents($fileName);
    }
  }
?>
```

---

```php
<?php
  /**
  * read content from file
  * @method readFile
  * @param string $fileName
  * @return file content
  */
  function readFileArray(string $fileName, bool $skipEmptyLines = false) {
    if(is_file($fileName) && is_readable($fileName)) {
      if($skipEmptyLines) {
        return file($fileName, FILE_IGNORE_NEW_LINES|FILE_SKIP_EMPTY_LINES);
      }
      else {
        return file($fileName)
      }
    }
  }
?>
```
---
```php
<?php
  /**
  * Write content from file
  * @method writeFile
  * @param string $fileName, $data
  * @return file content
  */
  function writeFile(string $fileName, $data) {
    $dirName = dirname($fileName);
    if(!file_exists($dirName)) {
      mkdir($dirName, 0777, true);
    }
    if(is_array($data) || is_object($data)) {
      $data = serialize($data);
    }
    if(file_put_contents !== false) {
      return true;
    }
    else {
      return false;
    }
  }
?>
```
