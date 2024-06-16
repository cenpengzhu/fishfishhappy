# 环境配置


## 安装最新的sqlite版本

### 为什么要安装最新的sqlite版本

由于django的测试需要用到sqlite数据库，sqlite版本较低的话会导致django无法运行。而且sqlite是直接编译在python里的，所以要放在python前安装。

### 步骤

+ 卸载sqlite

```bash

sudo yum remove sqlite-devel

```

+ 下载最新的sqlite源码

```bash
cd /usr/src

wget https://www.sqlite.org/2024/sqlite-autoconf-3460000.tar.gz
```

+ 解压源码包

```bash
tar -zxvf sqlite-autoconf-3460000.tar.gz
```

+ 配置源码以准备编译

```bash
cd ./sqlite-autoconf-3460000
mkdir /usr/local/sqlite346

./configure --prefix=/usr/local/sqlite346

```


+ 编译源码

```bash

make

```

+ 安装新版本的sqlite

```bash

sudo make install

```

+ 查看sqlite版本

```bash
sqlite3 --version
```


## 安装最新版本的python

### 为什么要安装最新版本的python

因为我们要用到最新版本的django，需要最新版本的python才能支持。

### 步骤


+ 删除旧的python3

```bash
 whereis python3 | xargs rm -frv
```

+ 安装依赖

```bash

sudo yum groupinstall -y "Development Tools"
sudo yum install -y zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel

```

+ 下载最新版本的python源码

```bash

cd /usr/src


wget https://www.python.org/ftp/python/3.12.0/Python-3.12.0.tgz

```

+ 解压源码包

```bash


tar xvf Python-3.12.0.tgz

```

+ 编译安装

```bash


cd Python-3.12.0
./configure --prefix=/usr/local/Python312/ 
make altinstall

```

+ 替换python命令

```bash
```

## 安装最新的git版本

### 为什么要安装最新的git版本？

因为我们要用vscode的插件gitlens，对git版本有要求。

### 步骤

+ 卸载当前git

```bash

sudo yum remove git

```

+ 安装依赖的包

```bash

sudo yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel
sudo yum install gcc perl-ExtUtils-MakeMaker

```

+ 下载git源码

```bash
cd /usr/src
sudo wget https://www.kernel.org/pub/software/scm/git/git-2.9.5.tar.gz
```

+ 解压源码包

```bash
sudo tar xzf git-2.9.5.tar.gz
```

+ 编译和安装git

```bash

cd git-2.9.5
sudo make prefix=/usr/local all
sudo make prefix=/usr/local install

```

+ 将git添加到环境变量

```bash

echo 'export PATH=$PATH:/usr/local/bin' >> ~/.bashrc
source ~/.bashrc

```

+ 查看git版本

```bash

git --version

```


## 安装mysql > 10.5

1. 添加mariadb官方yum源

```bash
sudo tee /etc/yum.repos.d/MariaDB.repo <<EOF
# MariaDB 10.5 CentOS repository list - created 2021-02-16 11:20 UTC
# http://downloads.mariadb.org/mariadb/repositories/
[mariadb]
name = MariaDB
baseurl = https://mirrors.cloud.tencent.com/mariadb/yum/10.5/centos7-amd64
gpgkey=https://mirrors.cloud.tencent.com/mariadb/yum/RPM-GPG-KEY-MariaDB
gpgcheck=1
EOF
```

2. 安装mariadb 10.5

```bash
sudo yum install MariaDB-server MariaDB-client
```

3. 修改配置文件
