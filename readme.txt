你好吗
1、
中文乱码
gsettings set org.gnome.gedit.preferences.encodings candidate-encodings "['GB18030', 'UTF-8', 'CURRENT', 'ISO-8859-15', 'UTF-16']"

2、
# --purge选项会将配置文件、数据库等删除
$ sudo apt-get autoremove --purge cuda

sudo apt-get --purge remove 

3、
用户目录下的 .bashrc 文件
在用户主目录下，有一个 .bashrc 文件，编辑该文件：
$gedit ~/.bashrc 
在最后边加入需要设置变量的shell语句，例如：
export PATH=~/mypath/bin:$PATH
该文件编辑保存后，可立即在新打开的终端窗口内生效。
该方式添加的变量只能当前用户使用。
如果使其立即生效： source ~/.bashrc

4、
make: Nothing to be done for `all' 解决方法
这句提示是说明你已经编译好了，而且没有对代码进行任何改动。
若想重新编译，可以先删除以前编译产生的目标文件：
make clean
然后再
make

5、
查看CUDA版本
cat /usr/local/cuda/version.txt

6、
查看cudnn版本
cat /usr/local/cuda/include/cudnn.h | grep CUDNN_MAJOR -A 2

7、
错误：This is probably because cuDNN failed to initialize, so try looking to see if a warning log message was printed above.

开头加入
import tensorflow as tf
config = tf.ConfigProto()
config.gpu_options.allow_growth = True
sess = tf.Session(config=config)（备注：动态申请显存，按程序需要使用显存）

8、添加清华源
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes



cd /etc/apt/
然后会显示下面的源文件sources.list 

sudo cp sources.list sources.list.bak 

sudo gedit sources.list

deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted universe multiverse
 
# 预发布软件源，不建议启用
# deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse
# deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-proposed main restricted universe multiverse

sudo apt-get update
sudo apt-get upgrade
9、conda update --all
   conda install xxx

10、pip install xxx
    pip install --upgrade xxx

11、jt -t monokai -f fira -fs 12 -cellw 90% -ofs 11 -dfs 11 -T -N
 
12、
sudo add-apt-repository ppa:plushuang-tw/uget-stable
sudo add-apt-repository ppa:t-tujikawa/ppa
# 这里是uGet的客户端
sudo apt-get install uget 
# 这里是待会要用的下载方式
sudo apt-get install aria2
13、
pycharm快捷方式
sudo gedit /usr/share/applications/Pycharm.desktop

[Desktop Entry]
Type=Application
Name=Pycharm
GenericName=Pycharm5
Comment=Pycharm5:The Python IDE 
Exec="/home/hupeng/pycharm/bin/pycharm.sh"
Icon=/home/hupeng/pycharm/bin/pycharm.png
Terminal=pycharm
Categories=Pycharm
