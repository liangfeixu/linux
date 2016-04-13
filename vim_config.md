[root@mail test]#rpm -qa|grep vim
vim-minimal-6.1-29
vim-common-6.1-29
vim-enhanced-6.1-29

直接用yum升级安装就ok了，
[root@mail test]#yum -y install vim-enhanced

安装完毕后，vi个文件试试，还是不行，原来是链接文件也要修改，ok，因为如下：
[root@mail test]# ll /bin/vi
lrwxrwxrwx  1 root root 12 Dec  9 10:52 /bin/vi -> /usr/bin/vim

那就修改下吧：
[root@mail test]#mv /bin/vi /bin/vi.bak
[root@mail test]#ln -s /usr/bin/vim /bin/vi

顺便修改下vi的设置，对编写perl代码更方便：
[root@mail test]# vi /etc/vimrc

  syntax on
  set hlsearch
  set nu
  set tabstop=4
  set shiftwidth=4
  set expandtab
  set shiftround

colorscheme neon
