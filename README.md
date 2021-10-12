# http服务器搭建
>搭建这个服务器的原因是兴趣所在；服务器很简陋，以后将一步步优化，加油！！
## 目录结构:
<pre>
    ├── Readme.md       // help
    ├── http            // web服务器--可执行文件
    ├── app.html        // 主页面
    ├── Makefile        // 编译工具链
    ├── src             // c语言web服务器文件
    │ ├── cJSON.c
    │ ├── cJSON.h
    │ ├── main.c
    │ ├── main.h
    │ └── ...
    ├── icon            //图片文件夹
    │ ├── ...
    │ └── ...
    ├── css             //html所需的css文件
    │ ├── ...
    │ └── ...
    └── js              //html所需的css文件
    │ ├── ...
    │ └── ...
    └── ...
</pre>
### 服务器怎么运行：
<pre>
    1、make编译工程，将会生产一个http的可执行文件
    2、运行服务器：./http（默认端口号8080）
        或者 ./http 8080（8080指服务器的端口号，可自行指定）
    3、ifconfig查看本地ip地址
    4、修改app.js文件中的function get_file_from_server()函数
        将 url: "http://192.168.13.132:8080/app.html/allfile" 中的IP地址和端口号改成你的主机地址
            或者把ip地址改为 localhost:8080, 但这样修改，将只能在Ubuntu的浏览器中访问服务器
    5、访问服务器：浏览器输入 http://192.168.13.132:8080/app.html 即可
        或者 http://localhost:8080/app.html
    6、服务器启动成功
</pre>
### 下载仓储
<pre>
    git clone https://github.com/S-xiejiahui/http_v1.0.git
    cd http_v1.0
    chmod 777 ./ -R 
    <h6>以下内容只需执行一次</h6>
    ssh-keygen -t rsa -C "e-mail@qq.com"                //获取ssh-key密钥
    cat /home/xjh/.ssh/id_rsa.pub                       //GitHub服务器添加你的密钥，你才能有上传代码权限
    git config --global user.name "username"            //设置你的ssh名
    git config --global user.email e-mail@qq.com        //设置你的ssh邮箱
    cat .git/config                                     //查看你的设置是否生效
</pre>
### 怎么提交代码:
<pre>
    git fetch                                           //同步远端服务器内容到本地分支
    git rebase origin master                            //如果有打印信息，说明你本地代码落后，GitHub上的代码
                                                        //则使用这条命令，同步
    git add ...                                         //添加修改的文件
    git commit -m "..."                                 //添加修改此次文件的备注
    git log --graph                                     //查看修改历史
    git push origin master                              //将修改的文件，推送到GitHub
</pre>
