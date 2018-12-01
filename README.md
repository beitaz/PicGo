# cc

> 纯纯饰品客户端

## 构建 (NPM)

_提示:_ 通过 `npm install -g xxx` 全局安装后使用本地链接方式 `npm link xxx` 即可安装依赖。

```shell
$ npm config set registry 'https://registry.npm.taobao.org'
$ ELECTRON_MIRROR=http://npm.taobao.org/mirrors/electron/ npm install -g electron
$ SASS_BINARY_SITE=http://npm.taobao.org/mirrors/node-sass npm install -g node-sass
$ npm install -g phantomjs --phantomjs_cdnurl=http://npm.taobao.org/mirrors/phantomjs
$ npm install -g chromedriver --chromedriver_cdnurl=http://npm.taobao.org/mirrors/chromedriver
$ npm link electron node-sass phantomjs chromedriver
$ npm install
$ npm run dev
...
```

### 生产环境

```shell
$ npm run build:clean
$ npm run build:dir
$ npm run build:web
...
```

## 应用说明

**PicGo 在上传图片之后自动会将图片链接复制到你的剪贴板里，可选 5 种复制的链接格式。**

PicGo 目前支持了

- `微博图床` v1.0
- `七牛图床` v1.0
- `腾讯云COS v4\v5版本` v1.1 & v1.5.0
- `又拍云` v1.2.0
- `GitHub` v1.5.0
- `SM.MS` v1.5.1
- `阿里云OSS` v1.6.0
- `Imgur` v1.6.0

未来将不增加默认的图床支持。待 PicGo v2.0 出来后你可以自行开发第三方图床插件。

支持 macOS、windows 64 位（>= v1.3.1），linux（>= v1.6.0）。

支持快捷键`command+shift+p`（macOS）或者`control+shift+p`（windows\linux）用以支持快捷上传剪贴板里的图片（第一张）。PicGo v1.4.0 版本及以上支持自定义快捷键，使用方法见[配置手册](https://github.com/Molunerfinn/PicGo/wiki/%E8%AF%A6%E7%BB%86%E7%AA%97%E5%8F%A3%E7%9A%84%E4%BD%BF%E7%94%A8#%E8%87%AA%E5%AE%9A%E4%B9%89%E5%BF%AB%E6%8D%B7%E9%94%AE)。

开发进度可以查看[Projects](https://github.com/Molunerfinn/PicGo/projects)，会同步更新开发进度。

**如果第一次使用，请参考应用使用[手册](https://github.com/Molunerfinn/PicGo/wiki)。遇到问题了还可以看看[FAQ](https://github.com/Molunerfinn/PicGo/blob/dev/FAQ.md)以及被关闭的[issues](https://github.com/Molunerfinn/PicGo/issues?q=is%3Aissue+is%3Aclosed)。**

## 下载安装

macOS 用户请下载最新版本的`dmg`文件，windows 用户请下载最新版本的`exe`文件，linux 用户请下载`AppImage`文件。

点击此处下载[应用](https://github.com/Molunerfinn/PicGo/releases)。

**如果你是 Arch 类的 Linux 用户，可以直接通过`aurman -S picgo-appimage`来安装 PicGo。感谢@houbaron 的贡献！**

**如果是国内用户下载 github release 文件速度很慢的话，推荐使用[Free Download Manager](http://www.freedownloadmanager.org/download.htm)来下载，速度会快。**

## 应用截图

![](https://user-images.githubusercontent.com/12621342/34242857-d177930a-e658-11e7-9688-7405851dd5e5.gif)

![picgo-menubar](https://user-images.githubusercontent.com/12621342/34242310-b5056510-e655-11e7-8568-60ffd4f71910.gif)

## 开发说明

> 目前仅针对 Mac、Windows。Linux 平台并未测试。

如果你想要学习、开发、修改或自行构建 PicGo，可以依照下面的指示：

> 如果想学习 Electron-vue 的开发，可以查看我写的系列教程——[Electron-vue 开发实战](https://molunerfinn.com/tags/Electron-vue/)

1. 你需要有 node、git 环境。需要了解 npm 的相关知识。
2. `git clone https://github.com/Molunerfinn/PicGo.git` 并进入项目
3. `npm install` 下载依赖
4. Mac 需要有 Xcode 环境，Windows 需要有 VS 环境。

### 开发模式

输入`npm run dev`进入开发模式，开发模式具有热重载特性。不过需要注意的是，开发模式不稳定，会有进程崩溃的情况。此时需要：

```bash
ctrl+c # 退出开发模式
npm run dev # 重新进入开发模式
```

### 生产模式

如果你需要自行构建，可以`npm run build`开始进行构建。构建成功后，会在`build`目录里出现构建成功的相应安装文件。

**注意**：如果你的网络环境不太好，可能会出现`electron-builder`下载`electron`二进制文件失败的情况。这个时候需要在`npm run build`之前指定一下`electron`的源为国内源：

```bash
export ELECTRON_MIRROR="https://npm.taobao.org/mirrors/electron/"
npm run build
```

只需第一次构建的时候指定一下国内源即可。后续构建不需要特地指定。二进制文件下载在`~/.electron/`目录下。如果想要更新`electron`构建版本，可以删除`~/.electron/`目录，然后重新运行上一步，让`electron-builder`去下载最新的`electron`二进制文件。

## 其他相关

- [vs-picgo](https://github.com/Spades-S/vs-picgo)：picgo 的 VSCode 版。

## 赞助

如果你喜欢 PicGo 并且它对你确实有帮助，欢迎给我打赏一杯咖啡哈~

支付宝：

![](https://user-images.githubusercontent.com/12621342/34188165-e7cdf372-e56f-11e7-8732-1338c88b9bb7.jpg)

微信：

![](https://user-images.githubusercontent.com/12621342/34188201-212cda84-e570-11e7-9b7a-abb298699d85.jpg)

## License

[MIT](http://opensource.org/licenses/MIT)

Copyright (c) 2017 Molunerfinn
