### [Tsinghua Mirrors](https://mirrors.tuna.tsinghua.edu.cn/help/pypi/)

- pypi

  ```bash
  pip install pip -U
  pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
  ```

- ubuntu

  `vim /etc/apt/sources.list`

  ```
  # 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
  
  # 预发布软件源，不建议启用
  # deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
  ```

###  [Open Port](https://askubuntu.com/questions/648970/open-a-port-on-ubuntu-14-04#825061)

- temporary

  `sudo iptables -I INPUT -p tcp -s 0.0.0.0/0 --dport 9000 -j ACCEPT`

- permanent

  ```bash
  iptables-save > /etc/iptables.conf # Save this changes to file
  touch /etc/network/if-up.d/iptables # Create file to call conf from
  echo "iptables-restore < /etc/iptables.conf" >> /etc/network/if-up.d/iptables # Add this line to this file
  chmod +x /etc/network/if-up.d/iptables  # Make the script executable
  ```

### [/usr/bin/ld: Cannot find -l$name](https://stackoverflow.com/questions/16710047/usr-bin-ld-cannot-find-lnameofthelibrary)

`apt-get install libfoo-dev`

### [pip install - locale.Error: unsupported locale setting](https://stackoverflow.com/questions/36394101/pip-install-locale-error-unsupported-locale-setting)

just run the following command:

`export LC_ALL=C`

If you keep getting the error in new terminal windows, add it at the bottom of your `.bashrc` file.

### [Apache shows php code instead of executing](https://stackoverflow.com/questions/12142172/apache-shows-php-code-instead-of-executing)

```bash
sudo apt-get install php libapache2-mod-php
sudo a2enmod mpm_prefork && sudo a2enmod php7.0
sudo service apache2 restart
```

Of course, you need to install apache2 firstly.





### 



