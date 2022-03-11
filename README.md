# upyun-upload
本脚本可以一键上传目录中的文件到又拍云存储,建议使用`Python3`运行,且需要安装扩展
```shell
pip install -r requirements.txt
```
# 特性
- 根据MD5忽略重复上传
- - 可取消
- 自定义上传路径
- 覆盖已存在的文件
- 忽略MD5验证
- 自定义源目录
- 自定义文件后缀
# 配置文件
```python
# UPYUN 参数 服务名、授权操作员账号、密码
service = ""
username = ""
password = ""
```
# 使用方法
```shell
# 上传运行路径内的所有文件 
python3 cos-upload.py
python3 cos-upload.py -d <指定目录>
python3 cos-upload.py -f <指定文件路径>
# 忽略MD5验证
python3 cos-upload.py -d <指定目录> -i true
# 忽略MD5验证，且只上传 php,js 文件
python3 cos-upload.py -d <指定目录> -i true -t php,js
```
|参数|说明|默认|
|:---|:---:|:---:|
|-f <文件路径>|指定单文件上传|运行目录
|-d <目录路径>|指定文件夹上传|运行目录
|-i true|忽略MD5验证|进行验证
|-t <文件后缀>|-t php,js,css|全部上传
## 如何优雅的上传整个目录的文件
1. 进入目录所在路径
```shell
python3 <脚本所在路径> -d <目录路径>
# 这个<目录路径> 则为您 上传存储路径
# 例 -d img/ 则存储路径为 img/*.*
```
