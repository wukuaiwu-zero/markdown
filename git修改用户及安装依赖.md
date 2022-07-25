### 修改账户及密码
#### 控制面板->用户账户->个人凭据->Windows凭据->查找git个人信息->修改个人信息

### 安装依赖出现 ERR code 128问题
#### 跳过git SSL验证
`git config --global http.sslverify "false"`    

`git config --global url."https://".insteadOf git://`