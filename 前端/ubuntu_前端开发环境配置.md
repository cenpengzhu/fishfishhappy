## �޸��ն�ǰ׺

### ΪʲôҪ�޸��ն�ǰ׺��

��Ϊ�ն�ǰ׺Ĭ����ʾ��ǰ����·����̫���˲��ÿ���

### ����

+ �༭.bashrc���ļ�

```
��:PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
�޸�Ϊ:PS1='${debian_chroot:+($debian_chroot)}\u:\W\$ '

ע:
Сд\w��ʾ��������Ŀ¼����д\W��ʾ��ǰ����Ŀ¼
��Ϊ�Ƶ�������\h̫���ˣ���Ҫ��ʾ�ˡ�
```

+ Ӧ��bash�ļ����޸�

```bash
source ~/.bashrc
```



## ��װ���°汾��node

### ΪʲôҪ��װ���°汾��node��

��Ϊvue��node�汾��Ҫ��Ϊ�˷�ֹ�ܶ�ӣ�����ֱ�������°汾��node��

### ����

+ ��װnvm��Node Version Manager��

```bash

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

```

+ �رղ����´��ն�

+ ʹ��nvm��װ���°汾��node

```bash

nvm install node

```

+ ʹ��nvm�л�node�汾

```bash
nvm use 22
```

+ �鿴node�汾

```bash
node -v
```

