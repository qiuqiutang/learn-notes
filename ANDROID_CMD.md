## 查看本地keystore文件（前提是有keystore的密码）

keytool -list -v -keystore 目标文件路径 -storepass keystore密码  


## gradle 批量打包 

### 检查是否配置了gradle PATH环境变量 

命令行下执行gradle -v 
如果不能识别则到AndroidStudio的安装目录下找到gradle目录，把其下的bin目录添加到Path中 

### 执行打包命令 

gradle assembleRelease 



## 有用的命令

### 查看所有的依赖 

.\gradlew :app:dependencies > deps.txt


### 查看当前模拟器上显示的页面对应的Activity 

adb shell "dumpsys activity top | grep ACTIVITY | tail -n 1"
