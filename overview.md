# 综述

Auto.js 使用[JavaScript](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)作为脚本语言，目前使用[Rhino 1.7.14](https://developer.mozilla.org/zh-CN/docs/Mozilla/Projects/Rhino)作为脚本引擎，支持 ES5 与部分 ES6 特性。

- 因为 Auto.js 是基于 JavaScript 的，学习 Auto.js 的 API 之前建议先学习 JavaScript 的基本语法和内置对象，可以使用教程前面的两个 JavaScript 教程链接来学习。
- 如果您想要使用 TypeScript 来开发，目前已经有开发者公布了一个可以把使用 TypeScript 进行 Auto.js 开发的工具，参见[Auto.js DevTools](https://github.com/pboymt/autojs-dev)。
- 如果想要在电脑而不是手机上开发 Auto.js，可以使用 VS Code 以及相应的 Auto.js 插件使得在电脑上编辑的脚本能推送到手机运行，参见[Auto.js-VSCode-Extension](https://marketplace.visualstudio.com/items?itemName=aaroncheng.auto-js-vsce-fixed)。

本文档的章节大致上是以模块来分的，总体上可以分成"自动操作"类模块(控件操作、触摸模拟、按键模拟等)和其他类模块(设备、应用、界面等)。

"自动操作"的部分又可以大致分为基于控件和基于坐标的操作。基于坐标的操作是传统按键精灵、触摸精灵等脚本软件采用的方式，通过屏幕坐标来点击、长按指定位置模拟操作，从而到达目的。例如`click(100, 200)`, `press(100, 200, 500)`等。这种方式在游戏类脚本中比较有可行性，结合找图找色、坐标放缩功能也能达到较好的兼容性。但是，这种方式对一般软件脚本却难以达到想要的效果，而且这种方式需要安卓 7.0 版本以上或者 root 权限才能执行。所以对于一般软件脚本(例如批量添加联系人、自动提取短信验证码等等)，我们采用基于控件的模拟操作方式，结合通知事情、按键事情等达成更好的工作流。这些部分的文档参见[基于控件的操作](widgets-based-automation.html)和[基于坐标的操作](coordinates-based-automation.html)。

# Auto.js 的功能

- [x] Auto.js 项目工程化：结合 webpack vscode 插件，开发、编译、打包、部署、混淆、加密一体化 [文档资料](https://github.com/kkevsekk1/webpack-autojs)
- [x] vscode 插件右键，自动提示操作等[下载地址](https://marketplace.visualstudio.com/items?itemName=aaroncheng.auto-js-vsce-fixed)
- [x] vscode 自动补全、方法注释等， [文档资料](https://github.com/kkevsekk1/webpack-autojs)
- [x] websocket 支持

其他部分主要包括：

- app: 应用。启动应用，卸载应用，使用应用查看、编辑文件、访问网页，发送应用间广播等。
- console: 控制台。记录运行的日志、错误、信息等。
- device: 设备。获取设备屏幕宽高、系统版本等信息，控制设备音量、亮度等。
- engines: 脚本引擎。用于启动其他脚本。
- events: 事件与监听。按键监听，通知监听，触摸监听等。
- floaty: 悬浮窗。用于显示自定义的悬浮窗。
- files: 文件系统。文件创建、获取信息、读写。
- http: HTTP。发送 HTTP 请求，例如 GET, POST 等。
- websocket: websocket 客户端、服务器端，可以进行主动推送消息
- images, colors: 图片和图色处理。截图，剪切图片，找图找色，读取保存图片等。
- keys: 按键模拟。比如音量键、Home 键模拟等。
- shell: Shell 命令。
- threads: 多线程支持。
- ui: UI 界面。用于显示自定义的 UI 界面，和用户交互。
- AI：人工智能相关，包含OCR等功能。
- zips：压缩解压。
- crypto：加密解密。
- base64：编码解码。

除此之外，Auto.js 还内置了对[Promise](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise)的支持。


