# 前言
	gitlab安装方法，gitlab比较占资源，宿主机的配置不能太差，请确保内存至少4GB。

# 使用指南
	首先建立数据卷容器
	docker run -v /app/tools/docker/gitlab/config:/etc/gitlab -v /app/tools/docker/gitlab/logs:/var/log/gitlab -v /app/tools/docker/gitlab/data:/var/opt/gitlab --name gitlab_volume alpine:3.7
	然后运行gitlab容器
	docker run -d -h gitlab.example.com -p 443:443 -p 80:80 -p 22:22 --name gitlab --restart always --volumes-from gitlab_volume gitlab/gitlab-ce