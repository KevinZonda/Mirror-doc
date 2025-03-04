## 镜像配置

Ubuntu 24.04+ 的配置文件位于`/etc/apt/sources.list.d/ubuntu.sources`。


1. 直接替换文件

    可通过如下命令直接下载配置文件并替换原有的`/etc/apt/sources.list.d/ubuntu.sources`：
    ```bash
    sudo wget http://mirrors.pku.edu.cn/repoconfig/ubuntu{ubuntu_version}/ubuntu.sources -O /etc/apt/sources.list.d/ubuntu.sources
    ```
    
    注：`{ubuntu_version}`为 Ubuntu 版本号，例如 `24.04`。

    修改文件后需要更新索引：
    ```bash
    sudo apt-get update
    ```

2. 或手动替换文件内容为：
    ```yaml
    Types: deb
    URIs: http://mirrors.pku.edu.cn/ubuntu 
    Suites: noble noble-updates noble-backports
    Components: main restricted universe multiverse
    Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg

    Types: deb
    URIs: http://security.ubuntu.com/ubuntu/
    Suites: noble-security
    Components: main restricted universe multiverse
    Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg
    ```

    修改文件后需要更新索引：
    ```bash
    sudo apt-get update
    ```
