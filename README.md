# CocoaPodsReintall
CocoaPods重新安装、版本降级方法，仅作学习之用。

1、打开终端，输入命令 rvm implode ，回车，然后输入yes，回车 —— 删除已有的rvm资源；    
2、前往文件夹 ~/.rvm ，删除该文件夹下的所有文件和文件夹；    
3、在终端中输入命令 rm -rf ~/.rvm ，回车 —— 删除.rvm文件夹；    
4、在终端中输入命令 rm -rf ~/.cocoapods/ ，回车 —— 删除已有的cocoapods资源；    
5、在终端中输入命令 curl -L get.rvm.io | bash -s stable ，回车 —— 链接rvm服务器；    
6、在终端中输入命令 source ~/.rvm/scripts/rvm ，回车 —— 启用“rvm”命令；    
7、在终端中输入命令 rvm reload ，回车 —— 重新加载rvm（不然步骤8可能会显示不出可安装的版本）；    
8、在终端中输入命令 rvm list known ，回车 —— 列出可安装的rvm版本；    
8、在列出的版本中选择一个版本来安装（例如安装2.2.4版本），在终端中输入命令 rvm install 2.2.4 --verify-downloads 2 ，回车 —— 安装新版本rvm；    
9、在终端中输入命令 rvm use 2.2.4 --default ，回车 —— 将安装完成的新版本设置为默认；    
10、在终端中输入命令 rvm list ，回车 —— 可查看已安装的版本；    
11、在终端中输入命令 gem source ，回车 —— 查看源是否已经切换到淘宝镜像服务器；    
12、若没有切换到淘宝镜像服务器，则在终端中输入命令 gem sources -r https://rubygems.org/ ，回车 —— 移除原有的镜像服务器；    
13、在终端中输入命令 gem sources -a https://ruby.taobao.org/ ，回车 —— 添加淘宝镜像服务器；    
14、在终端中输入命令 rvm use 2.2.4，回车 —— 启用新安装的rvm版本；    
15、在终端中输入命令 sudo gem install cocoapods --version 0.39.0，回车 ——     安装新版本cocoapods（可修改指定安装的版本，这里举例是0.39.0，如果步骤8中安装的rvm版本为2.3.0及以上版本的话，那么将要安装的cocoapods版本必须要在1.0.0及以上）；    
16、在终端中输入命令 pod setup，回车 —— 启用新安装的cocoapods版本(此步骤比较耗时)；    
17、若步骤16成功完成后即可完成重新安装或降级cocoapods版本；    
18、若步骤16发生错误（如：[!] /usr/bin/Git clone 'https://github.com/CocoaPods/Specs.git' master —depth=1），则在终端中输入命令 sudo gem update --system ，回车 —— 更新gem版本；    
19、在终端中输入命令 sudo -rm -rf ~/.cocoapods/，回车 —— 删除之前发生错误的cocoapods资源；    
20、完成后再执行步骤16即可；
21、若步骤16发生错误（如：Operation not permitted - /usr/bin/xcodeproj），则在终端中输入命令 sudo gem install -n /usr/local/bin cocoapods --version 0.39.0 ，回车 —— 重新安装cocoapods；    
22、步骤21完成后，再依次执行步骤19、20即可。    
