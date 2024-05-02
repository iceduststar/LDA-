# LDA-
LDA
本仓库转载自知乎老哥mute.X的文章，原贴见链接 https://zhuanlan.zhihu.com/p/372269493
# 运行准备
## 安装库
在命令行中输入
```shell
pip install tqdm requests multitasking retry bs4 pandas pyLDAvis==3.4.0 scikit-learn numpy jieba xlrd openpyxl
```
## 修改文件名
```shell
# 本地 csv 文件，可以是本地文件，也可以是远程文件
source_csv_path = 'BV1qX4y1W7qt.csv'
# 文本 csv 文件里面文本所处的列名,注意这里一定要填对，要不然会报错的！
document_column_name = '评论内容'
```
## 修改内置函数
打开“环境路径\Lib\site-packages\pyLDAvis\_prepare.py”
修改243行
```shell
default_term_info = default_term_info.sort_values(
        by='saliency', ascending=False).head(R).drop('saliency', 1)
```
为
```shell
default_term_info = default_term_info.sort_values(
        by='saliency', ascending=False).head(R).drop(labels=['saliency'], axis=1)
```

接着运行即可成功
