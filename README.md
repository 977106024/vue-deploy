# vue项目自动部署到服务器


## 方式一 使用scp2
* 在项目里安装scp2
* 项目中添加deploy文件夹里的代码
* 在deploy/products.js中写入主机名、同户名、登录密码、服务器存放打包文件的目录
* 使用命名`npm run deploy:dev`

### 方式二 阿里云 云效部署
* 在阿里云code建立代码仓库
* 创建仓库的流水线
* 设置流水线的构建与部署 见阿里云文档 [流水线配置文档](https://thoughts.teambition.com/sharespace/5d8325488acc9d00143ac6ef/docs/5dcf86438a05fe001424c1ea?spm=a2cl9.flow_devops2020_goldlog_detail.0.0.37145bf2jlH3Jw)


