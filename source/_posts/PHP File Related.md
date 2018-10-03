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
  * Write content to file
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
    if(file_put_contents($fileName, $data) !== false) {
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
  * Write content to file
  * @method writeFile
  * @param string $fileName, $clearFlag, $data
  * @return file content
  */
  function writeFile(string $fileName, $data, $clearFlag = false) {
    $dirName = dirname($fileName);
    if(!file_exists($dirName)) {
      mkdir($dirName, 0777, true);
    }
    if(is_file($fileName) && is_readable($fileName)) {
      if(filesize($fileName) > 0) {
        $srcData = file_get_contents($fileName);
      }
    }
    if(is_array($data) || is_object($data)) {
      $data = serialize($data);
    }
    $data = srcData.$data;
    if(file_put_contents($fileName, $data) !== false) {
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
  * Truncate content from file
  * @method truncateFile
  * @param string $fileName, int $length
  * @return file content
  */
  function truncateFile(string $fileName, int $length) {
    if(is_file($fileName) && is_writeable($fileName)) {
      $handle = fopen($fileName, 'rb+');
      $length < 0 ? 0 : $length;
      ftruncate($fileName, $length);
      fclose($fileName);
      return true;
    }
    else {
      return false;
    }
  }
?>
```

---

## File Download

```php
<?php
  /**
  * Download File
  * @method  downloadFile
  * @param string $fileName, array $allowDownloadExtension
  * @return void
  */
  function downloadFile(string $fileName, array $allowDownloadExtension = ['jpg', 'jpeg', 'gif', 'txt', 'png', 'html', 'zip', 'rar']) {
    // test if downloadable and exisit
    if(!is_file($fileName) || !is_readable($fileName)) {
      return false;
    }
    $extension = strtolower(pathinfo($fileName, PATHINFO_EXTENSION))；
    if(!in_array($extension, $allowDownloadExtension)) {
      return false;
    }

    // header() send header info
    header('content-type:application/octet-stream');
    // tell client that size is calculated base on bytes
    header('Accept-Ranges:bytes');
    header('Accept-Length:'.filesize($fileName));
    // tell client this is an attachment
    header('Content-Disposition:attachment;filename='.basename($fileName));
    readfile($fileName);
  }
?>
```

---

```php
<?php
  /**
  * Download File slice
  * @method  downloadFile
  * @param string $fileName, array $allowDownloadExtension
  * @return void
  */
  function downloadFile(string $fileName, array $allowDownloadExtension = ['jpg', 'jpeg', 'gif', 'txt', 'png', 'html', 'zip', 'rar']) {
    // test if downloadable and exisit
    if(!is_file($fileName) || !is_readable($fileName)) {
      return false;
    }
    $extension = strtolower(pathinfo($fileName, PATHINFO_EXTENSION))；
    if(!in_array($extension, $allowDownloadExtension)) {
      return false;
    }

    // header() send header info
    header('content-type:application/octet-stream');
    // tell client that size is calculated base on bytes
    header('Accept-Ranges:bytes');
    $fileSize = filesize($fileName)
    header('Accept-Length:'.$fileSize);
    // tell client this is an attachment
    header('Content-Disposition:attachment;filename='.basename($fileName));

    $readeBuffer = 1024;
    $sumBuffer = 0;
    $handle = fopen($fileName, 'rb');
    while(!fendf($handle) && $sumBuffer < $fileSize) {
      echo fread($handle, $readBuffer);
      $sumBuffer += $readBuffer;
    }
    fclose($handle);
    exit;
  }
?>
```

---

## File Upload

```php
<?php
  function uploadFile(array $fileInfo, string $uploadPath = './uploads', bool $imageFlag = true, array $allowUploadExtension = ['jpeg', 'gif', 'txt', 'png', 'html', 'zip', 'rar'], int $maxSize = 2097152) {
    define('UPLOAD_ERRS',[
      'upload_max_filesize' => 'upload_max_filesize exceeded',
      'form_max_size' => 'form_max_size exceeded',
      'upload_file_partial' => 'partial file uploaded',
      'no_upload_file_selected' => 'no_upload_file_selected',
      'upload_system_error' => 'system error',
      'file_type_not_supported' => 'file type not supported',
      'exceed_max_size' => 'max size exceed',
      'not_true_image' => 'not true image',
      'not_http_post' => 'not post',
      'move_error' => 'move_error'
    ]);
    // check if upload error
    if($fileInfo['error'] === UPLOAD_ERR_OK) {
      $ext = strtolower(pathinfo($fileInfo['name'], PATH_EXTENSION));
      if(!in_arry($ext, $allowUploadExtension)) {
        return UPLOAD_ERRS['file_type_not_supported'];
      }
      if($fileInfo['size'] > $maxSize) {
        return UPLOAD_ERRS['exceed_max_size'];
      }
      if($imageFlag) {
        if(@!getimagesize($fileInfo['tmp_name'])) {
          return UPLOAD_ERRS['not_true_image'];
        }
      }
      if(!is_uploaded_file($fileInfo['tmp_name'])) {
        return UPLOAD_ERRS['not_http_post'];
      }

      if(!is_dir($uploadPath)) {
        mkdir($uploadPath, 0777, true);
      }
      $uniName = md5(uniqueid(microtime(true), true)), '.'.$ext;

      $dest = $uploadPath.DIRECTORY_SEPARATOR.$uniName;
      if(@!move_uploaded_file($fileInfo['tmp_name'], $dest)) {
        return UPLOAD_ERRS['move_error'] ;
      }
      return $dest;
    }
    else {
      switch($fileInfo['error']) {
        case 1:
          $mes = UPLOAD_ERRS['upload_max_filesize'];
          break;
        case 2:
          $mes = UPLOAD_ERRS['form_max_size'];
          break;
        case 3:
          $mes = UPLOAD_ERRS['upload_file_partial'];
          break;
        case 4:
          $mes = UPLOAD_ERRS['no_upload_file_selected'];
          break;
        case 5:
          $mes = UPLOAD_ERRS['upload_system_error'];
          break;
      }
      return $mes;
    }
  }
?>
```

---

## File Archive

```php
// Single File
<?php
  function zip_file(string $fileName) {
    if(!is_file($fileName)) {
      return false;
    }
    $zip = new ZipArchive();
    $zipName = basename($fileName).'.zip';
    if($zip->open($zipName, ZipArchive::CREATE|ZipArchive::OVERWRITE)) {
      if($zip=>addFile($fileName)) {
        @unlink($fileName);
      }
      $zip->close();
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
// Multiple File
<?php
  function zip_files(string $zipName, ...$files) {

    $zipExt = strtolower(pathinfo($zipName,PATH_EXTENSION));
    if('zip' !== $zipExt) {
      return false;
    }
    $zip = new ZipArchive();
    if($zip->open($zipName, ZipArchive::CREATE|ZipArchive::OVERWRITE)) {
      foreach($files as $file) {
        if(is_file($file)) {
          if($zip=>addFile($fileName)) {
            @unlink($fileName);
          }
          $zip->close();
            return true;
          }
        }
    }
    else {
      return false;
    }
  }
?>
```

---

```php
// Multiple File
<?php
  function unzip_file(string $zipName, string $dest) {
    if(!is_file($zipName)) {
      return false;
    }
    if(!is_dir($dest)) {
      mkdir($dest, 0777, true);
    }
    $zip = new ZipArchive();
    if($zip->open($zipName)) {
      $zip->extractTo($dest);
      $zip->close();
      return true;
    }
    else {
      return false;
    }
  }
?>
```
