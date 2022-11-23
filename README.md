# gym_order_auto
> auto order gym in specific time

> 自动运行预定健身房脚本，可以指定时间，日期，地点，并可选通过邮件通知

## 使用方法:
> Ubuntu16.04为例
### 1.下载代码
    git clone https://github.com/WSure00/gym_order.git
### 2.写入cookie，用来登录健身房网站。写入到./cookies.txt
    modify your cookie in ./cookies.txt
### 3.在 gym_order.py文件中修改以下变量为你自己的：{mail_receiver},{smtpserver},{sender},{psw} (邮件通知可选，也可以不设置)
    set your own vars in gym_order.py: {mail_receiver},{smtpserver},{sender},{psw}
    
    ps:function send email is optional
### 4.可选操作: 在Linux中可以设置crontab来自动定时运行脚本
    optional: use crontab to auto run the script:
#### &emsp;     i.在 gym.sh 文件中修改{absolute_path}变量为绝对路径 
    change the {absolute_path} in gym.sh
#### &emsp;     ii.编辑crontab文件，输入定时命令
    crontab -e
#### &emsp;     iii.以早上10:55，每周一、二、三、四、日为例，crontab命令格式如下
    55 10 * * sun,mon,tue,wed,thu /bin/sh {absolute_path}/gym.sh # formation like this
#### &emsp;     iv.重新加载crond服务，使crontab设置生效
    service crond reload
    service crond restart