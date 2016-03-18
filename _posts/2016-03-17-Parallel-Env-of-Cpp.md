---
layout: post
title: "Parallel Programming Environment of C++"
category: [C++]
tag: [C++, Parallel Computing, GDAL]
date: 2016-03-17 20:01:00
comments: true
---

- Microsoft Visual Studio 2010
- Microsoft HPC 2012 MS-MPI
安装vcredist_x64_2010和vcredist_x86_2010（机器装了VS2010则无需安装这两项）、mpi_x64，如果是32位机器则装mpi_x86，在命令行输入 mpiexec 测试是否安装成功

- GDAL 1.11.1
下载并安装gdal-111-1600-x64-core.msi
方法一：链接: http://pan.baidu.com/s/1c0saqQW 密码: ggbj
方法二：http://download.gisinternals.com/sdk/downloads/release-1600-x64-gdal-1-11-1-mapserver-6-4-1/gdal-111-1600-x64-core.msi
一路下一步就可以，安装路径在C:\Program Files\GDAL下，在环境变量里新建GDAL_DATA项，路径设置为C:\Program Files\GDAL\gdal-data。
