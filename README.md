# vim-verilog
Verilog vim 编辑器设置

### 解决中文乱码  
```
set encoding=utf-8
set fileencodings=utf-8,chinese,latin-1
if has("win32")
set fileencoding=chinese
else
set fileencoding=utf-8
endif
"解决菜单乱码
source $VIMRUNTIME/delmenu.vim
source $VIMRUNTIME/menu.vim
"解决consle输出乱码
language messages zh_CN.utf-8

```

### 更改Tab键为4个空格
```
set linespace=4
set tabstop=4
set expandtab
set nobackup
set nosmartindent
set noautoindent
set ruler
```

### System Verilog支持  
```
au BufRead,BufNewFile *.sv set filetype=systemverilog
au BufRead,BufNewFile *.vh set filetype=systemverilog
au BufRead,BufNewFile *.vt set filetype=systemverilog
au BufRead,BufNewFile *.inc set filetype=systemverilog

```

### 自动产生头文件  
```
func    Vheader()
    call append(1,  '//===============================================')
    call append(2,  '//  Filename       : '.expand("%"))
    call append(3,  '//  project        : ')
    call append(4,  '//  Department     : ')
    call append(5,  '//  Description    : ')
    call append(6,  '//')
    call append(7,  '//  Author         : wuzhangquan')
    call append(8,  '//  Email          : wzqim@qq.com')
    call append(9,  '//  CreateDate     : '.strftime("%Y-%m-%d %H:%M:%S"))
    call append(10, '//  Reversion      : ')
    call append(11, '//  Release Info   : ')
    call append(12, '//===============================================')
    call append(13, '')
endfunc

map <F2> :call Vheader()

```

## VIM 语法文件
在home目录创建 .vim/syntax 文件夹
将systemverilog.vim复制进去




