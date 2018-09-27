---
title: PPHP File System
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
- 