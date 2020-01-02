nginx file share

1 设置文件共享
    server {
        listen       8000;#共享端口
        server_name  localhost;
        location / {
            root   html;
            index  index.html index.htm;
        }
        location /share {
            alias    D:\work\share;  #显示的根索引目录，注意这里要改成你自己的，目录要存在
            allow all;
            autoindex on;             #开启索引功能
            autoindex_exact_size off; # 关闭计算文件确切大小（单位bytes），只显示大概大小（单位kb、mb、gb）
            autoindex_localtime on;   # 显示本机时间而非 GMT 时间
        }

    }

2 启动 nginx 
	进入到项目路径下 ，执行 start nginx

3 打开浏览器,ip是你的计算机ip，port是共享端口，此处配置为8000，
	输入ip：port/share，即可访问文件