---
title: PHP File System
date: 2018-09-25 10:59:07
tags: [PHP]
---

- `file()`
- `filetype($file_name)` --> return file type
- `filesize($file_name)` --> return file size --> bit size
- `filectime($file_name)` --> create time
- `filemtime()` --> modified time
- `fileatime()` --> access time
- `is_readable()` -- readable?
- `is_writeable() | is_writable()` --> writeable?
- `is_executable()` --> executable?
- `is_file()` --> is a file?
  
---
- `pathinfo()` --> file path
- `basename()` --> return base name
- `dirname()` --> return directory name
- `file_exists()` --> if exist

---

- `touch(file)` --> create file
- `unlink(file)` --> delete file
- `rename(old,new)` --> rename file/move file
- `copy(src, dest)` --> copy file (copy url needs to set `allow_url_fopen=On`)

--- 
## Read and Write 
- `fopen()` open a file with specific mode
  > `r`, `r+`, `w`, `w+`, `a+`
- `fread()` read a file
- `fwrite()` write a file
- `ftell()` --> return pointer index
- `fseek()` --> move pointer
- `frewind()` --> move pointer index to the 0
- `fclose()` --> close file
- `fwrite()/fputs()`
- `ftruncate()` --> slice file content 
- `fgetc()` --> get a character
- `fgets()` --> get a line
- `fgetss()` --> get a line and remove html tags
- `feof()` --> return true if reach end of file
- `strip_tags()` --> remove tags