# DAAL-Sklearn
 比较了两个库的性能差异

在WIN 10和mac OSX均进行了实验
可视化结果展现于excel表格的第二页

## 安装
用conda 创建一个虚拟环境，python版本选3.7（3.8daal支持好像有点问题，intel的那个库bug非常多，而且是很明显的那种，后续会给官方库提交debug记录
### sklearn的安装比较容易，
例如 pip install sklearn

### intel daal由于官方文档的不及时更新以及国内教程的缺失，安装坑极其多
我找到的一个解决方案是 先用conda 安装已经编译好的 intelpython

conda install -c intel intelpython 

https://anaconda.org/intel/intelpython

然后再用conda安装已经编译好的 daal4py 

conda install -c intel daal4py  

https://software.intel.com/content/www/us/en/develop/articles/daal4py-overview-a-high-level-python-api-to-the-intel-data-analytics-acceleration-library.html

这里还得注意，由于我是在jupyter notebook中写的代码，但是在安装完前两个库后，还是无法import daal4py，但是在本地bash里可以，重安装一遍jupyter后问题解决

剩下的问题就是查api写代码的了

daal 文档链接 https://intelpython.github.io/daal4py/algorithms.html

daal中的算法支持比sklearn少

daal4py库的example可以参考，但是bug也不少，数据集为了方便对比性能，统一采取了example里的dataset

在比较不同数据集大小下的性能时，采用了sklearn的数据生成方案，可以看出在数据集变大的时候，性能差异变得明显（前提是不爆内存

好人一生平安
