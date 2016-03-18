---
layout: post
title: "Python Environment Configuration for GISer"
category: [Python]
tag: [Python, Arcpy, GIS]
date: 2016-03-17 17:00:00
comments: true
---

1. ArcGIS 10.3.1，Arcpy，GDAL等
ArcGIS 10.3开始安装Desktop时必须选择安装Python，好在可通过ArcGIS_BackgroundGP_for_Desktop_103_141996.exe安装支持64位python的arcpy。
这样，装完ArcGIS10.3之后我们就有了32位和64位的Python 2.7.8，分别位于C:\Python27\ArcGIS10.3和C:\Python27\ArcGISx6410.3。
我们以使用64位Python为例进行配置，将C:\Python27\ArcGISx6410.3;C:\Python27\ArcGISx6410.3\Scripts添加至环境变量Path中;
但是此时如果右键以IDLE打开某py脚本，默认的python是32位版本的，需要做如下设置：
```
注册表中找到
HKEY_CLASSES_ROOT\\Python.CompiledFile\\shell\\open\\command\\(default)
将其value修改为"C:\Python27\ArcGISx6410.3\python.exe" "%1" %*
```

 2. 安装easy_install及pip
管理员方式运行cmd，cd到setuptools所在目录，输入python setup.py install；
同样，cd到pip所在目录，输入python setup.py install
这样，我们就可以离线安装whl格式的python第三方库啦，下载地址为http://www.lfd.uci.edu/~gohlke/pythonlibs/。
 3. GDAL
通过上述链接，可以下载完整的GDAL打包文件GDAL-1.11.3-cp27-none-win_amd64.whl，管理员方式运行cmd，cd到该文件目录，输入pip install GDAL-1.11.3-cp27-none-win_amd64.whl，提示安装成功即可，输入以下命令验证是否安装成功：
```
>>> python
>>> from osgeo import gdal
>>> from osgeo import ogr
>>> from osgeo import osr
>>> from osgeo import gdal_array
>>> from osgeo import gdalconst
```
 4. 其他python库安装，步骤类似：scipy，numexpr，PyQt4，wxPython（需要wxPython_common），PyGTK，python_dateutil，pytz，matplotlib，pywin32。。。
 5. 
- Ulipad 或 PyCharm

