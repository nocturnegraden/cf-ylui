# cf-ylui
## 简介

基于 IBM Cloudfoundry 运行

在此鸣谢YLUI作者

[源码地址](https://github.com/yuri2peter/ylui)

## 使用

1.准备必需

- IBM CIL

- Git

- Nodejs

  ### 步骤1：克隆示例应用

  首先，克隆应用程序

  ```
  git clone https://github.com/nocturnegraden/cf-ylui.git
  ```

  ### 步骤2：在本机执行应用程式

  使用NPM软件包管理器安装依赖项并运行您的应用程序。

  1. 在命令行上，切换到工程目录。

     ```
     cd get-started-node
     ```

  2. 安装[package.json](https://docs.npmjs.com/files/package.json)文件中列出的依赖项以在本地运行该应用程序。

     ```
     npm install
     ```

  3. 运行应用程序。

     ```
     npm start
     ```

  4. 通过以下URL查看您的应用： `http://localhost:3000`

  ### 步骤3：准备要部署的应用

打开`manifest.yml`文件，并将`appname`更改为您的应用名称

 

```
 applications:
- name: appname
  disk_quota: 1G
  instances: 1
  memory: 64M
  routes:
  - route: appname.us-south.cf.appdomain.cloud
```

### 步骤4：部署应用

您可以使用IBM Cloud CLI将应用程序部署到IBM Cloud。

1. 登录到您的IBM Cloud帐户，然后选择一个API端点。

   ```
   ibmcloud login
   ```

定位到Cloud Foundry组织和空间：

```
ibmcloud target --cf
```

从`ylui`目录中，将您的应用程序推送到IBM Cloud。

```
ibmcloud cf push
```