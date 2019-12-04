检查中文冲突。
# 1.合并遇到换行符
warning: LF will be replaced by CRLF in book.txt.  
The file will have its original line endings in your working directory  
解决方法：windows 换行符为回车换行CRLF，unix/linux/mac为LF。  
git config --global core.autocrlf false
# 2.中文乱码
* $ git config --global core.quotepath false          # 显示 status 编码
* $ git config --global gui.encoding utf-8            # 图形界面编码
* $ git config --global i18n.commit.encoding utf-8    # 提交信息编码
* $ git config --global i18n.logoutputencoding utf-8  # 输出 log 编码
* $ export LESSCHARSET=utf-8
* # 最后一条命令是因为 git log 默认使用 less 分页，所以需要 bash 对 less 命令进行 utf-8 编码
* [gui]encoding = utf-8
说明：我们的代码库是统一用的 utf-8，这样设置可以在 git gui 中正常显示代码中的中文。
* [i18n]commitencoding = GB2312
说明：如果没有这一条，虽然我们在本地用 $ git log 看自己的中文修订没问题，但，一、我们的 log 推到服务器后会变成乱码；二、别人在 Linux 下推的中文 log 我们 pull 过来之后看起来也是乱码。这是因为，我们的 commit log 会被先存放在项目的 .git/COMMIT_EDITMSG 文件中；在中文 Windows 里，新建文件用的是 GB2312 的编码；但是 Git 不知道，当成默认的 utf-8 的送出去了，所以就乱码了。有了这条之后，Git 会先将其转换成 utf-8，再发出去，于是就没问题了。
