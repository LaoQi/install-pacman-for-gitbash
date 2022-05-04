# 在你的git-bash上安装pacman



Script to install pacman in git-bash

 run `./install_pacman.sh` from git-bash



给你的`git-bash` 安装 pacman 包管理器

> 由于`mingw`仓库使用`zstd`压缩，脚本会自动从[facebook/zstd](https://github.com/facebook/zstd/releases/download/v1.5.2/zstd-v1.5.2-win64.zip) 下载，但由于网络问题不一定能下载成功，所以在 [releases](https://github.com/LaoQi/install-pacman-for-gitbash/releases) 里提供了带有`zstd`的包，但是你只要稍微思考一下就知道，如果前面的都下载失败，你又怎么能从这个仓库的releases下载成功呢？🤪



#### 已知的问题与解决方案

> 由于 `pacman`是拷贝进来的，`git-for-windows`中原有的软件均不在包管理的数据库中(类似通过 `make install`手工安装的软件)，所以在安装其他软件时可能会导致文件冲突。
>
> 解决方案：将需要管理的软件重新纳入 `pacman`进行管理，比如 `vim`，执行 ` pacman -S --needed --dbonly vim`
>
> 需要批量重建，可以参考仓库 [git-for-windows/build-extra](https://github.com/git-for-windows/build-extra) ，其中 `versions/package-version-x.x.x.txt`列举了所有安装的包。



> `git-for-windows` 安装后，根目录下的文件权限可能导致普通用户无法修改，在安装过程中会出现`Permission denied`错误，或者`Could not unlink`警告。
>
> 解决方案：权限问题请使用管理员运行`git-bash`，通常执行过一次安装后，文件权限将变更，下次更新时普通用户也可以进行修改。



#### 参考来源

* [Windows 的终端配置(给 git-windows 添加 msys2 包管理器)](https://blog.zeromake.com/pages/windows-terminal-configuration/)
* [git-for-windows/build-extra](https://github.com/git-for-windows/build-extra)
* [wiki.archlinux.org "Restore local database"](https://wiki.archlinux.org/title/Pacman_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)/Restore_local_database_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))
* [www.msys2.org](https://www.msys2.org/) 



```text
            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                    Version 2, December 2004

 Copyright (C) who care?

 Everyone is permitted to copy and distribute verbatim or modified
 copies of this license document, and changing it is allowed as long
 as the name is changed.

            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
   TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

  0. You just DO WHAT THE FUCK YOU WANT TO.
```