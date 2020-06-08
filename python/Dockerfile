#基于的基础镜像
FROM python:3.6

#代码添加到code文件夹
ADD . /code

# 设置code文件夹是工作目录
WORKDIR /code

# 导出端口
# EXPOSE 5120

# 安装支持
RUN pip install -r requirements.txt -i http://pypi.douban.com/simple --trusted-host pypi.douban.com

CMD ["python", "/code/main.py"]