## 项目中遇到的坑

+ 可以监听$route来实现路由变动监测

+ 别机访问本地项目--package.json文件第八行，加上本机ip

      "dev": "webpack-dev-server --inline --progress --config build/webpack.dev.conf.js --host 192.168.0.135",
