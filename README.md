# SkiaDemo
# 编译skia
## 开发环境
### visual studio2019
为了方便高度，预先安装好visua Studio 2019。本人安装的版本是
```
Microsoft Visual Studio Community 2019 版本 16.11.26
winsdk 版本10.0.19041.0
```
### 科学上网
需要下载外网下载代码。务好vpn.
## 下载好skia代码
### 下载depot_tools
https://chromium.googlesource.com/chromium/tools/depot_tools.git

可以clone下载
```
git clone https://chromium.googlesource.com/chromium/tools/depot_tools.git
```
然后执行update_depot_tools.bat更新该工具。
```
cd depot_tools
update_depot_tools.bat
```
然后把depot_tools完整路径，加入到环境变量中,比如D:\depot_tools。

### skia
下载skia
```
git clone https://skia.googlesource.com/skia.git
cd skia
python3 tools/git-sync-deps
bin/fetch-ninja
```
如果python3 tools/git-sync-deps这一步出错，多跑几次，值到把依赖的代码都下载下来。
## 编译

下载以编译Debug版本为例。
### 使用Visual Studio编译
```
bin/gn gen --ide=vs out/Debug
```
如果发现没有gn，则可以运行以下命令，会把gn.exe下载到bin目录
```
python3 tools/git-sync-deps
```

执行完后gen生成后，会在out/Debug目录中看到all.sln。
再执行以下命令，就会编译生成对应的库和exe文件了。可以直接运行HelloWorld.exe
```
ninja -C out/Static
```
### 如果需要使用Visual Studio

# 参考
[https://skia.org/docs/user/build/](https://skia.org/docs/user/build/)