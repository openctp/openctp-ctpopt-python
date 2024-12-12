# CTP股票期权接口Python版

## 直接使用

openctp提供了pip install和文件下载两种方法安装CTPOPT-Python库，可以直接使用，均支持3.5.8~3.7.0各个版本。

### pip install方式

```bash
pip install openctp-ctpopt==3.7.0.* -i https://pypi.tuna.tsinghua.edu.cn/simple --trusted-host=pypi.tuna.tsinghua.edu.cn
```

### 文件下载方式

[CTPOPT-Python接口下载](http://openctp.cn/download.html)

## 自己编译
CTPOPT-Python使用Swig技术开发，可以自己按以下步骤编译，需要安装swig等组件，详细攻略见：[CTPAPI-Python开发攻略](https://zhuanlan.zhihu.com/p/688672132)。

### Windows编译
本仓库选用的是CTPOPT-3.7.0，如需编译其它版本，请下载相应的CTPOPT文件覆盖对应目录下的CTPOPT文件。

#### Win32
```
cd CTPOPT
mkdir build
cd build
cmake ..
cmake --build . --config Release
```

#### Win64
```
cd CTPOPT
mkdir build
cd build
cmake -A x64 ..
cmake --build . --config Release
```

### Linux编译
```
cd CTPOPT
mkdir build
cd build
cmake ..
make
```
### 效果
```
[luojian@ecs-395321-0004 build]$ cmake ..
-- The C compiler identification is GNU 9.3.1
-- The CXX compiler identification is GNU 9.3.1
-- Check for working C compiler: /opt/rh/devtoolset-9/root/usr/bin/cc
-- Check for working C compiler: /opt/rh/devtoolset-9/root/usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working CXX compiler: /opt/rh/devtoolset-9/root/usr/bin/c++
-- Check for working CXX compiler: /opt/rh/devtoolset-9/root/usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
generate swig wrap files ...
/home/luojian/programming/github-ssh/openctp-ctp-python/CTPAPI/lin64/ThostFtdcTraderApi.h:30: Warning 514: Director base class CThostFtdcTraderSpi has no virtual destructor.
/home/luojian/programming/github-ssh/openctp-ctp-python/CTPAPI/lin64/ThostFtdcMdApi.h:30: Warning 514: Director base class CThostFtdcMdSpi has no virtual destructor.
-- Configuring done
-- Generating done
-- Build files have been written to: /home/luojian/programming/github-ssh/openctp-ctp-python/CTPAPI/build
[luojian@ecs-395321-0004 build]$ make
Scanning dependencies of target _thostmduserapi
[ 50%] Building CXX object CMakeFiles/_thostmduserapi.dir/thostmduserapi_wrap.cxx.o
Linking CXX shared library _thostmduserapi.so
[ 50%] Built target _thostmduserapi
Scanning dependencies of target _thosttraderapi
[100%] Building CXX object CMakeFiles/_thosttraderapi.dir/thosttraderapi_wrap.cxx.o
Linking CXX shared library _thosttraderapi.so
[100%] Built target _thosttraderapi
[luojian@ecs-395321-0004 build]$
```
