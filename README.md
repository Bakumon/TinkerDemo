使用步骤：

### 1. 执行 assembleRelease 任务

会在 `app\build\bakApk` 文件夹下生成三个文件，安装 apk 到手机

```
apk: app-release-2017-10-23-17-50-41.apk
mapping: app-release-2017-10-23-17-50-41-mapping.txt
R: app-release-2017-10-23-17-50-41-R.txt
```

### 2. 修改 app/build.gradle 文件中的 ext 节点

修改 tinkerOldApkPath 、tinkerApplyMappingPath 、 tinkerApplyResourcePathd 的值，对于上面上个文件名

tinkerBuildFlavorDirectory 忽略

### 3. 写修复代码

比如修改 TextView 的 text

### 4. 执行 tinkerPatchRelease 任务

改任务将生成 patch apk文件，用于热修复加载。

复制 `app\build\outputs\tinkerPatch\release` 文件夹下的 `patch_signed_7zip.apk` 文件到手机根目录下。

### 5. 打开步骤 1 安装的 app，点击按钮进行热修复加载

会自动退出app，tinker 不支持即时修复。