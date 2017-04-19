## devEops
devEops通过封装Ansible api来处理实际业务运行可能遇到的安装部署运维工作

## Getting started
devEops是一个django项目，依赖于

* gradle
* Python2.7+
* Ansible2.2+
* HTTP文件服务器环境
* 基础YUM源

## Log
### 2017-3-28
#### Info
  完成了除了Nginx之外的所有应用批量部署的功能。针对重新采用的动态主机列表，将底端的封装api重新修改，去除所有的server字段。
#### For
* 重新思考页面的业务解决方式(目前倾向于部署只部署应用 通过初始化来配置以及启动关闭)
* 在页面尝试配置修改并且批量推送的功能
* 数据库添加历史记录表 规划dashboard的组织方法

### 2017-4-6
#### Info
  考虑了一下模板的方式不能够解决多个版本的应用问题，如果要每个应用的每个版本都制作不同的应用模板就比较有问题了。采用修改配合文件的方式。
  使用ansible的fetch的模块来远程获取文件，并以时间戳的形式在/tmp目录下产生文件并且读取出来。当修改后，重新入这个文件，并且批量推送到主机上。
#### For
* 尝试使用原生的bootstrap来构建网页

### 2017-4-17
#### Info
  考虑到后期的功能拓展，重新构建更加好的前台模板。不使用已有的bootstrap模板，而是全部自己进行编码。
  目前已经构思了基础的dashboard界面以及group界面。可以沿用原来的js数据处理或者重构接口
#### For
* 完成host界面设计以及编码
* 前台代码重构

### 2017-4-18
#### Info
  构建了devEopsWeb的group页面和host页面。对dashboard的app-bell中的get more info按钮进行了ajax事件的绑定。
#### Bug
  * Page: pages/dashboard.html
  * Do: 点击app-bell元素中的 get more info <a>
  * Result: 两次点击中，一次点击会进行ajax页面修改。有一次会直接跳转到pages/host.html，样式全无。

### 2017-4-19
#### Info
  构建了devEopsWeb的redis的部署界面。我觉得自己做的很棒！我觉得自己很帅！在构建提交的模态框，对于HTML和JS的提交的数据的存储方式提出问题。
#### Img
  ![BATCH-REDIS](img/batch-redis.jpg)