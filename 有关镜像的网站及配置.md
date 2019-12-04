## 淘宝 mirror
* https://npm.taobao.org/
## atom
* 使用apm替换源：apm config set registry http://registry.npm.taobao.org  
* 检查是否配置成功 apm install --check
## 淘宝npm镜像
* 搜索地址：http://npm.taobao.org/
* registry地址：http://registry.npm.taobao.org/
* cnpmjs镜像
* 搜索地址：http://cnpmjs.org/
* registry地址：http://r.cnpmjs.org/
## 使用配置npm

* 1.临时使用  

npm --registry https://registry.npm.taobao.org install express
* 2.持久使用  

npm config set registry https://registry.npm.taobao.org  

// 配置后可通过下面方式来验证是否成功  

npm config get registry  

// 或npm info express  

* 3.通过cnpm使用
npm install -g cnpm --registry=https://registry.npm.taobao.org  

// 使用cnpm install expresstall express
