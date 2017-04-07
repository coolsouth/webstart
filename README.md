# webstart<br/>
第一步：基础环境<br/>
1.默认已购买：域名，阿里云云服务器esc：CPU：4核；内存： 8192 MB (I/O优化)；5Mbps；CentOS 7.2 64位；一年5000+<br/>
2.服务器实例重置密码，重启。<br/>
3.mac 终端：$ ssh root@192.1.1.1  (实例公网IP。之后都用192.1.1.1代替) $yes(提问要打yes，直接回车不行的) $实例输入密码  <br/>就可以看到Welcome to Alibaba Cloud Elastic Compute Service !那就可以了，基本操作环境搞定了，暂时不考虑数据盘。第一步已完成<br/><br/>
第二步：jsp＋tomcat环境<br/>
4.下载安装jdk<br/>下载：http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html<br/>
安装目录：/usr/java/jdk，$ scp /Users/zhengnan/Downloads/new/jdk-8u121-linux-x64.tar.gz root@192.1.1.1:/usr/java/jdk/<br/>
解压：#tar -xvf jdk-8u121-linux-x64.tar.gz<br/>
修改环境变量：#vi /etc/profile  <br/>
最后面加上：<br/>
#set java environment<br/>
export JAVA_HOME=/usr/java/jdk/jdk1.8.0_121<br/>
export JRE_HOME=/usr/java/jdk/jdk1.8.0_121/jre<br/>
export CLASSPATH=.:$JAVA_HOME/lib$:JRE_HOME/lib:$CLASSPATH<br/>
export PATH=$JAVA_HOME/bin:$JRE_HOME/bin/$JAVA_HOME:$PATH<br/>
执行：# source /etc/profile <br/>
检查：# java -version <br/>
5.下载安装tomcat <br/>下载：http://tomcat.apache.org/download-70.cgi <br/>
安装目录：/usr/java/，$ scp /Users/zhengnan/Downloads/new/apache-tomcat-7.0.76.tar.gz root@192.1.1.1:/usr/java/ <br/>
解压：#tar -xvf apache-tomcat-7.0.76.tar.gz 改名：#mv apache-tomcat-7.0.76 tomcat<br/>
编辑：#cd bin/ <br/>
#vi setclasspath.sh 加上<br/>
export JAVA_HOME=/usr/java/jdk/jdk1.8.0_121<br/>
export JRE_HOME=/usr/java/jdk/jdk1.8.0_121/jre <br/>
启动tomcat:# ./startup.sh <br/>
检查：外面浏览器输入：192.1.1.1:8080<br/>
