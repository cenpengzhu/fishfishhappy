## 修改终端前缀

### 为什么要修改终端前缀？

因为终端前缀默认显示当前完整路径，太长了不好看。

### 步骤

+ 编辑.bashrc问文件

```
将:PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
修改为:PS1='${debian_chroot:+($debian_chroot)}\u:\W\$ '

注:
小写\w表示完整工作目录，大写\W表示当前工作目录
华为云的主机名\h太长了，不要显示了。
```

+ 应用bash文件的修改

```bash
source ~/.bashrc
```



## 安装最新版本的node

### 为什么要安装最新版本的node？

因为vue对node版本有要求，为了防止很多坑，我们直接用最新版本的node。

### 步骤

+ 安装nvm（Node Version Manager）

```bash

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

```

+ 关闭并重新打开终端

+ 使用nvm安装最新版本的node

```bash

nvm install node

```

+ 使用nvm切换node版本

```bash
nvm use 22
```

+ 查看node版本

```bash
node -v
```

