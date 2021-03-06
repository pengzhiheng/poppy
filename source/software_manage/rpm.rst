rpm
=======


- -i 安装
- -e 卸载
- -q 查询
- -a 所有包
- -v 显示过程
- -Uvh 升级包

rpm安装软件
-----------------
这里我们安装一个名为httpd.rpm的rpm包。

::

    rpm -ivh httpd.rpm

查看指定rpm包是否安装
---------------------
::

    rpm -q httpd

rpm卸载软件
-----------------
这里我们卸载一个名为httpd的rpm包的安装。

::

    rpm -evh httpd

查看所有已安装的rpm包
----------------------

::

    rpm -qa

其他详细资料
-------------
以下内容来自网络：https://www.cnblogs.com/xxpal/articles/816692.html

::

    rpm命令参数详解
    1. rpm 常用命令
    (01)安装一个包：# rpm -ivh
    (02) 升级一个包：# rpm -Uvh
    (03) 移走一个包：# rpm -e
    (04) 安装参数：
          --force 即使覆盖属于其它包的文件也强迫安装
          --nodeps 如果该RPM包的安装依赖其它包，即使其它包没装，也强迫安装。
    (05) 查询一个包是否被安装：# rpm -q < rpm package name>
    (06) 得到被安装的包的信息：# rpm -qi < rpm package name>
    (07) 列出该包中有哪些文件：# rpm -ql < rpm package name>
    (08) 列出服务器上的一个文件属于哪一个RPM包：#rpm -qf
    (09) 可综合好几个参数一起用：# rpm -qil < rpm package name>
    (10) 列出所有被安装的rpm package：# rpm -qa
    (11) 列出一个未被安装进系统的RPM包文件中包含有哪些文件：# rpm -qilp < rpm package name>


    2. rpm参数详解
    (1) 安装命令
    命令格式：# rpm -i(or --install) [options] file1.rpm ... fileN.rpm
    参数列表：file1.rpm ... fileN.rpm（将要安装的RPM包的文件名）
    详细选项：
    -h (或 --hash) 安装时输出hash记号 (``#'')
    --test 只对安装进行测试，并不实际安装。
    --percent 以百分比的形式输出安装的进度。
    --excludedocs 不安装软件包中的文档文件
    --includedocs 安装文档
    --replacepkgs 强制重新安装已经安装的软件包
    --replacefiles 替换属于其它软件包的文件
    --force 忽略软件包及文件的冲突
    --noscripts 不运行预安装和后安装脚本
    --prefix 将软件包安装到由 指定的路径下
    --ignorearch 不校验软件包的结构
    --ignoreos 不检查软件包运行的操作系统
    --nodeps 不检查依赖性关系
    --ftpproxy 用 作为 FTP代理
    --ftpport 指定FTP的端口号为
    通用选项：
    -v 显示附加信息
    -vv 显示调试信息
    --root 让RPM将指定的路径做为“根目录”，这样预安装程序和后安装程序都会安装到这个目录下
    --rcfile 设置rpmrc文件为
    --dbpath 设置RPM 资料库存所在的路径为

    (2) 删除命令
    命令格式：# rpm -e(or --erase) [options] pkg1 ... pkgN
    参数列表：pkg1 ... pkgN （要删除的软件包）
    详细选项：
    --test 只执行删除的测试
    --noscripts 不运行预安装和后安装脚本程序
    --nodeps 不检查依赖性
    通用选项：
    -vv 显示调试信息
    --root 让RPM将指定的路径做为"根目录"，这样预安装程序和后安装程序都会安装到这个目录下
    --rcfile 设置rpmrc文件为
    --dbpath 设置RPM 资料库存所在的路径为

    (3) 升级命令
    命令格式：# rpm -U(or --upgrade) [options] file1.rpm ... fileN.rpm
    参数列表：file1.rpm ... fileN.rpm （软件包的名字）
    详细选项：
    -h (or --hash) 安装时输出hash记号 (``#'')
    --oldpackage 允许"升级"到一个老版本
    --test 只进行升级测试
    --excludedocs 不安装软件包中的文档文件
    --includedocs 安装文档
    --replacepkgs 强制重新安装已经安装的软件包
    --replacefiles 替换属于其它软件包的文件
    --force 忽略软件包及文件的冲突
    --percent 以百分比的形式输出安装的进度
    --noscripts 不运行预安装和后安装脚本
    --prefix 将软件包安装到由 指定的路径下
    --ignorearch 不校验软件包的结构
    --ignoreos 不检查软件包运行的操作系统
    --nodeps 不检查依赖性关系
    --ftpproxy 用 作为 FTP代理
    --ftpport 指定FTP的端口号为
    通用选项：
    -v 显示附加信息
    -vv 显示调试信息
    --root 让RPM将指定的路径做为"根目录"，这样预安装程序和后安装程序都会安装到这个目录下
    --rcfile 设置rpmrc文件为
    --dbpath 设置RPM 资料库存所在的路径为

    (4) 查询命令
    命令格式：# rpm -q(or --query) [options]
    参数列表：pkg1 ... pkgN （查询已安装的软件包）
    详细选项：
    -p (or ``-'') 查询软件包的文件
    -f 查询属于哪个软件包
    -a 查询所有安装的软件包
    -g 查询属于组的软件包
    --whatprovides 查询提供了 功能的软件包
    --whatrequires 查询所有需要 功能的软件包
    信息选项：
    显示软件包的全部标识
    -i 显示软件包的概要信息
    -l 显示软件包中的文件列表
    -c 显示配置文件列表
    -d 显示文档文件列表
    -s 显示软件包中文件列表并显示每个文件的状态
    --scripts 显示安装、卸载、校验脚本
    --queryformat (or --qf) 以用户指定的方式显示查询信息
    --dump 显示每个文件的所有已校验信息
    --provides 显示软件包提供的功能
    --requires (or -R) 显示软件包所需的功能
    通用选项：
    -v 显示附加信息
    -vv 显示调试信息
    --root 让RPM将指定的路径做为"根目录"，这样预安装程序和后安装程序都会安装到这个目录下
    --rcfile 设置rpmrc文件为
    --dbpath 设置RPM 资料库存所在的路径为

    (5) 校验已安装的软件包
    命令格式： # rpm -V(or --verify, or -y) [options]
    参数列表：pkg1 ... pkgN （将要校验的软件包名）
    软件包选项：
    -p 校验包文件
    -f 校验所属的软件包
    -a 校验所有的软件包
    -g 校验所有属于组 的软件包
    详细选项：
    --noscripts 不运行校验脚本
    --nodeps 不校验依赖性
    --nofiles 不校验文件属性
    通用选项：
    -v 显示附加信息
    -vv 显示调试信息
    --root 让RPM将指定的路径做为"根目录"，这样预安装程序和后安装程序都会安装到这个目录下
    --rcfile 设置rpmrc文件为
    --dbpath 设置RPM 资料库存所在的路径为

    (6) 校验软件包中的文件
    语法：# rpm -K(or --checksig) [options] file1.rpm ... fileN.rpm
    参数：file1.rpm ... fileN.rpm （软件包的文件名）
    详细选项：
    --nopgp 不校验PGP签名
    通用选项：
    -v 显示附加信息
    -vv 显示调试信息
    --rcfile 设置rpmrc文件为

    (7) 其它参数选项
    --rebuilddb 重建RPM资料库
    --initdb 创建一个新的RPM资料库
    --quiet 尽可能的减少输出
    --help 显示帮助文件
    --version 显示RPM的当前版本