# SharedSpace
随便放 


# Openpose安装教程阅读资料
1. 最一开始的官方的(需要翻墙)
   https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/master/doc/installation/0_index.
   
   md#compiling-and-running-openpose-from-source

2. 博客(按照我看的顺序)
3. 
   https://blog.csdn.net/qing101hua/article/details/53007847 (Cmake是啥？)

   https://www.cnblogs.com/riaol/p/12491077.html (安装了再说)

   https://cmake.org/download/

   然后Cmake编译的时候中间有一些下载的过程，会很慢，压缩包啥的我放里面。自己把东西都放好之后它就会跳过这些。

   https://blog.csdn.net/zb1165048017/article/details/82115724/ (从这个博客上下的，我已经下好了，注意按照里面的要求)

   https://blog.csdn.net/lgh0824/article/details/75949477/ (CUDA，开启GPU加速时必要的东西，显卡牌子是英伟达用的)

  《OpenPose笔记——windows 10下，自编译openpose代码（vs下能跑了，pythonAPI也能使了）》, 一起来围观吧 https://blog.csdn.net/xuelanlingying/article/details/102793110?utm_source=app&app_version=4.18.0&code=app_1562916241&uLinkId=usr1mkqgl919blen (手机上搜的)

   《windows10下openpose的安装和配置使用教程（C++），以及常见错误分析。》, 一起来围观吧 https://blog.csdn.net/weixin_42922831/article/details/110131984?utm_source=app&app_version=4.18.0&code=app_1562916241&uLinkId=usr1mkqgl919blen

   《window10下openpose和pyopenpose的配置》, 一起来围观吧 https://blog.csdn.net/weixin_41652829/article/details/114779305?utm_source=app&app_version=4.18.0&code=app_1562916241&uLinkId=usr1mkqgl919blen

   我的显卡显存不够，会报错，也可只选CPUONLY
   https://blog.csdn.net/qing101hua/article/details/78258972 (就像这样)

   而且不止要用cuda，在它之上还有个cudnn，可能也需要这个。

   https://developer.nvidia.com/cudnn

   https://blog.csdn.net/sinat_23619409/article/details/84202651

   再看看这些doc吧，我没咋看懂，看懂这些就差不多能交差了

   https://github.com/luckynote/openpose/tree/master/doc

   应该完成上述过程中在visual studio中运行openposedemo没啥问题了，摄像头模式，也可以试试其它模式，比如放张照片啥的。
   CMake中的每个选项一般不要出现xxx_NOT_FOUND的，说明没有完全解压或者文件位置不对或者可能也是环境变量的问题？？生成多半会不成功。

# OpenPose如何在python上运行？？？
#  正在反复观看这个视频，想要搞明白这个是啥，到底咋弄

   https://www.bilibili.com/video/av667869379

1. 按照文档上所说的在设置时选好BUILD_PYTHON就应该可以了，同时我也按照它的路径找到了相关的pyb库文件啥的(具体都是啥我一点没懂)
   但是当我使用Pycharm打开 D:\openpose\build\examples\tutorial_api_python 之中的那些py文件时发现报错，产生importError
   最最最开始时我打开最上面import cv2啥的是红的，说明我的python环境中没有安装opencv-python系列的包，为了防止我虚拟环境啥的搞不懂，
   我卸载了anaconda大蟒蛇，只采用本地的base默认环境，什么库都往里面装就行了。然后不管在pycharm还是vs什么的只要查教程设置就可以
   import那些我安装好的包了。
   https://www.runoob.com/python/python-install.html
   (百度什么时候有了开发者搜索功能？？？看看好用不)
   https://kaifa.baidu.com/searchPage?wd=python%E7%8E%AF%E5%A2%83&module=SEARCH
   
   以下杂七杂八，因为我也没解决。
   https://blog.csdn.net/zag666/article/details/104608616

   https://www.jb51.net/article/171647.htm


   我用#CSDN#这个app发现了有技术含量的博客，小伙伴们求同去《OpenPose基于Windows10的编译（包括python运行）》, 一起来围观吧 https://blog.csdn.net/weixin_44116060/article/details/115801204?utm_source=app&app_version=4.18.0&code=app_1562916241&uLinkId=usr1mkqgl919blen (手机上看的)

   我用#CSDN#这个app发现了有技术含量的博客，小伙伴们求同去《pyopenpose文档》, 一起来围观吧 https://blog.csdn.net/weixin_40802676/article/details/100830688?utm_source=app&app_version=4.18.0&code=app_1562916241&uLinkId=usr1mkqgl919blen

   https://blog.csdn.net/u010032054/article/details/104401051/?utm_term=openposepython%E5%AE%89%E8%A3%85&utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~all~sobaiduweb~default-0-104401051&spm=3001.4430

   https://blog.csdn.net/p690075426/article/details/109190570?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_ecpm_v1~rank_v31_ecpm-2-109190570.pc_agg_new_rank&utm_term=openpose+python+%E5%AE%89%E8%A3%85&spm=1000.2123.3001.4430

2. 文件路径问题？？
   在python向导api这些文件中(build中)，我发现里面一开始代码是添加环境变量(？)的。(没看懂)
   我对照着路径发现指向的位置可能没有什么问题，它到底要这些路径里面的什么东西？
   我把这些文件夹里面的文件都放在D:\openpose\build\bin 里面了，又把测试用的.py放进去了。(pycharm中运行的时候一定要看看运行时设置，是不是运行的是复制过去的那个脚本.py) 发现果然它报的不是上面的
   ### Error: OpenPose library could not be found. Did you enable `BUILD_PYTHON` in CMake and have this Python script in the   right folder?
   而是
   ### Starting OpenPose Python Wrapper...
   ###   ---------------------------------- WARNING ----------------------------------
   ###  We have introduced an additional boost in accuracy in the CUDA version of about 0.2% with respect to the CPU/OpenCL versions. We will not port this to CPU given the considerable slow down in speed it would add to it. Nevertheless, this accuracy boost is almost insignificant so the CPU/OpenCL versions can be safely used.
   ### -------------------------------- END WARNING --------------------------------
   ###  a bytes-like object is required, not 'NoneType'
   我已经在文件夹中搜索"requirement.txt"，并且pip install -r requirements.txt -i xxxx(镜像路径)了
   本地环境里面的包我感觉都有了，不知道为什么还会错，可能还是我在python设置的时候没有用好吧
   或者还是打开的方式不对……………………
   # 大家有空就水水吧，教教我接下来该怎么办。
   # 一定要在example里的python代码中的模型，素材文件路径设置好，并且移动到bin文件夹！前面环境变量的问题其实尚未解决我觉得，但是把上述这些文件dll，pyd啥的放到一个文件夹里面就成了。
   # 我觉得大家看看博客应该就成了

   


