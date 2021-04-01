### 动漫头像生成器

目前只在Windows 10，Python：3.6.12，cudatoolkit：10.0.130，tensorflow-gpu：1.14.0，环境下进行了测试。其他环境的可执行情况未知。（只支持含有CUDA的机器）

欢迎Star以获取后续更新版本。

**请点击右侧Release标签栏下载！**

生成模型采用的是StyleGANv2。



因压缩包有1.1G，若下载较慢可以使用百度云：

链接：https://pan.baidu.com/s/1TSM1c1nasW6aKZj-rqWFVA  提取码：oyij 

**使用说明：**

下载软件压缩包并解压到任意文件夹

<img src="https://banni.oss-cn-beijing.aliyuncs.com/img/20210401200955.jpg" alt="img" style="zoom: 80%;" />

2.打开文件夹并找到MakeAnimeFace.exe文件，双击打开

<img src="https://banni.oss-cn-beijing.aliyuncs.com/img/20210401200959.jpg" alt="img" style="zoom:80%;" />

3.生成初始页面

<img src="https://banni.oss-cn-beijing.aliyuncs.com/img/20210401201001.jpg" alt="img" style="zoom:50%;" />

4.点击Generate按钮生成动漫头像图片

<img src="https://banni.oss-cn-beijing.aliyuncs.com/img/20210401201004.jpg" alt="img" style="zoom:50%;" />

5.获得喜欢的动漫头像后，点击Save按钮保存文件。

<img src="https://banni.oss-cn-beijing.aliyuncs.com/img/20210401201006.jpg" alt="img" style="zoom:50%;" />

下方会图像保存的路径位置。

6.打开当前目录下的result文件夹，可以查看到保存的所有图片。

<img src="https://banni.oss-cn-beijing.aliyuncs.com/img/20210401201008.jpg" alt="img" style="zoom: 80%;" />

 

**Anime face generator/Anime avatar generator**

Currently only tested under Windows 10, Python: 3.6.12, cudatoolkit: 10.0.130, tensorflow-gpu: 1.14.0. The executable status of other environments is unknown. (Only supports machines with CUDA)

Welcome to Star to get the follow-up updated version.

**Please click on the Release tab on the right to download!**

The generative model uses StyleGANv2.



#### 常见报错信息

```
Traceback (most recent call last):
  File "main.py", line 2, in <module>
  File "D:\2019Download\Anaconda\Anaconda\envs\openaibaselinetf1\lib\site-packages\PyInstaller\loader\pyimod03_importers.py", line 623, in exec_module
  File "run_generator.py", line 7, in <module>
  File "D:\2019Download\Anaconda\Anaconda\envs\openaibaselinetf1\lib\site-packages\PyInstaller\loader\pyimod03_importers.py", line 623, in exec_module
  File "dnnlib\tflib\__init__.py", line 7, in <module>
  File "D:\2019Download\Anaconda\Anaconda\envs\openaibaselinetf1\lib\site-packages\PyInstaller\loader\pyimod03_importers.py", line 623, in exec_module
  File "dnnlib\tflib\network.py", line 7, in <module>
  File "D:\2019Download\Anaconda\Anaconda\envs\openaibaselinetf1\lib\site-packages\PyInstaller\loader\pyimod03_importers.py", line 623, in exec_module
  File "site-packages\tensorflow\__init__.py", line 28, in <module>
  File "D:\2019Download\Anaconda\Anaconda\envs\openaibaselinetf1\lib\site-packages\PyInstaller\loader\pyimod03_importers.py", line 623, in exec_module
  File "site-packages\tensorflow\python\__init__.py", line 49, in <module>
  File "D:\2019Download\Anaconda\Anaconda\envs\openaibaselinetf1\lib\site-packages\PyInstaller\loader\pyimod03_importers.py", line 623, in exec_module
  File "site-packages\tensorflow\python\pywrap_tensorflow.py", line 30, in <module>
  File "site-packages\tensorflow\python\platform\self_check.py", line 70, in preload_check
ImportError: Could not find 'nvcuda.dll'. TensorFlow requires that this DLL be installed in a directory that is named in your %PATH% environment variable. Typically it is installed in 'C:\Windows\System32'. If it is not present, ensure that you have a CUDA-capable GPU with the correct driver installed.
```

在环境变量中没有找到`'nvcuda.dll'`，需要安装CUDA（推荐版本为10.0.130）。

No'nvcuda.dll' is found in the environment variables, and CUDA needs to be installed (The recommended version is 10.0.130).



```
Loading networks from "model/network.pkl"...
Traceback (most recent call last):
  File "main.py", line 43, in <module>
  File "run_generator.py", line 105, in generate_anime_face
  File "dnnlib\submission\submit.py", line 218, in submit_run
  File "dnnlib\submission\submit.py", line 186, in submit
  File "dnnlib\submission\submit.py", line 148, in run_wrapper
  File "run_generator.py", line 54, in generate_images_prepare
  File "load_networkds.py", line 10, in load_networks
  File "dnnlib\tflib\tfutil.py", line 123, in init_tf
  File "dnnlib\tflib\tfutil.py", line 146, in create_session
  File "site-packages\tensorflow\python\client\session.py", line 1570, in __init__
  File "site-packages\tensorflow\python\client\session.py", line 693, in __init__
tensorflow.python.framework.errors_impl.InternalError: cudaGetDevice() failed. Status: CUDA driver version is insufficient for CUDA runtime version
[17920] Failed to execute script main
```

CUDA驱动版本不符合运行要求（推荐重新安装版本为10.0.130的驱动）。

The CUDA driver version does not meet the operating requirements (it is recommended to reinstall the driver with version 10.0.130).



```
Traceback (most recent call last):
  File "main.py", line 43, in <module>
  File "run_generator.py", line 105, in generate_anime_face
  File "dnnlib\submission\submit.py", line 218, in submit_run
  File "dnnlib\submission\submit.py", line 186, in submit
  File "dnnlib\submission\submit.py", line 148, in run_wrapper
  File "run_generator.py", line 54, in generate_images_prepare
  File "load_networkds.py", line 12, in load_networks
  File "dnnlib\tflib\network.py", line 253, in __setstate__
  File "dnnlib\tflib\network.py", line 110, in _init_graph
  File "<string>", line 491, in G_synthesis_stylegan2
  File "<string>", line 455, in layer
  File "<string>", line 99, in modulated_conv2d_layer
  File "<string>", line 68, in apply_bias_act
  File "dnnlib\tflib\ops\fused_bias_act.py", line 68, in fused_bias_act
  File "dnnlib\tflib\ops\fused_bias_act.py", line 122, in _fused_bias_act_cuda
  File "dnnlib\tflib\ops\fused_bias_act.py", line 16, in _get_plugin
  File "dnnlib\tflib\cudautil.py", line 103, in get_plugin
  File "dnnlib\tflib\cudautil.py", line 68, in _prepare_nvcc_cli
RuntimeError: Could not find MSVC/GCC/CLANG installation on this computer. Check compiler_bindir_search_path list in "D:\GAN\main\dnnlib\tflib\cudautil.pyc".
[1496] Failed to execute script main
```

C++编译器版本找不到，查看电脑中有没有`C:/Program Files (x86)/Microsoft Visual Studio/2017/Community/VC/Tools/MSVC/14.14.26428/bin/Hostx64/x64`或`C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.24.28314/bin/Hostx64/x64`文件夹，如果没有，需要下载上述两个中的任一个`Microsoft Visual Studio`版本。或者也可以提供您的编译器路径，将会在后续版本中更新。

The C++ compiler version cannot be found, check if there is `C:/Program Files (x86)/Microsoft Visual Studio/2017/Community/VC/Tools/MSVC/14.14.26428/bin/Hostx64/x64` or `C:/Program in the computer Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.24.28314/bin/Hostx64/x64` folder, if not, you need to download either of the above two Microsoft Visual Studio versions. Or you can provide your compiler path, which will be updated in subsequent versions.

