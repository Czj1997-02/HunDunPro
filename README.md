# HunDunPro

[![](https://img.shields.io/badge/HunDunPro-V2.0.0-gray.svg?longCache=true&colorB=green)](https://pro.hundun.ink/doc) [![](https://img.shields.io/badge/README-EN-gray.svg?longCache=true&colorB=orange)](./README-EN.md) 

HunDunPro是一个基于Django开发的低代码框架，支持通过数据库配置或表单字段填写，生成CRUD代码、接口及前端界面。

## 技术栈
- [x] Python3.12.x
- [x] Django5.x
- [x] Mysql8.x
- [x] Vue2.x
- [ ] Uniapp
- [ ] Flutter

## 项目设计
- [x] 后端接口
- [x] 管理后台
- [x] 前端界面
- [ ] 移动端界面
- [ ] 小程序/H5

## 功能设计
- [x] 用户管理
- [x] 权限管理
- [x] 文件管理
- [x] 文档管理
- [x] 定时任务
- [x] 拖拽生成界面
- [x] 代码生成
- [x] AI模型嵌入

## 管理后台
管理后台基于`Django`框架自带的`Admin`后台进行拓展，使用`SimpleUI`美化，增加了导出、代码生成操作等自定义动作，增加了富文本编辑器、JSON编辑器等功能。
自动生成的`Admin`后台能够更自由、高效的实现管理业务，极大的减少相应的开发工作。
![admin](https://github.com/user-attachments/assets/61d45d7f-16fc-4d09-90de-18b01f1ae840)

## 代码生成
代码生成功能使用`Jinja`模板语言设计实现，能够一键生成后端接口、后台管理界面及前端界面。目前支持三种模式生成代码：表单编辑模式、原始代码引入模式、数据库引入模式
![jinja](https://github.com/user-attachments/assets/fcf28f09-758c-4be8-90fb-cc134c3b422c)
### 表单编辑模式
使用表单编辑设计应用模块的数据表及属性字段，在对应功能增加有AI模型嵌入进行辅助设计和相关数据生成。
![table](https://github.com/user-attachments/assets/37626e85-7844-4f98-99b7-6b11a19d401a)
### 原始代码引入模式
对于自由编写或从其他地方植入的非系统生成的模型代码，允许通过选择模块模型的方式，引入该部分代码生成对应数据，然后执行代码生成，对接口和前端界面进行生成补全。
![import](https://github.com/user-attachments/assets/89e2c7e0-e029-4d41-b8a9-2c07526e98e6)
### 数据库引入模式
对于有一定编码能力的用户，可以自由设计sql数据库后，通过数据库引入生成对应数据和代码。
![sql](https://github.com/user-attachments/assets/2a9f96bb-39f0-4eaa-8e78-f7d8b1efd5f6)

## 拖拽设计生成界面
自研了一套全开放的`Drag`指令，用于实现拖拽操作及相关逻辑，并对应设计有允许高度定制化的低代码拖拽生成功能，实现前端界面的高效开发。
对于一些非标界面，代码生成的表单界面不满足使用，可以通过此工具进行界面设计后导出对应界面代码进行使用。
![web](https://github.com/user-attachments/assets/063b31bf-8608-4c05-a94b-e24d00e01acb)

## Docker容器化构建部署
使用`Docker`容器化构建项目，轻轻松松几行指令，实现项目的部署、及后续常态化更新运维。
### 部署
```
# Docker 部署运维
# 切换到项目目录
cd /opt/HunDunPro
# 部署
docker-compose up -d
```
### 更新
```
# 后端更新依赖（无依赖变化时无需操作）
docker exec hundun pip install --no-cache-dir -r requirements.txt -i https://pypi.doubanio.com/simple
# 后端数据映射（无数据模型变化时无需操作）
docker exec hundun python manage.py makemigrations
docker exec hundun python manage.py migrate
# 容器内安装前端依赖（无依赖变化时无需操作）
docker exec -it hundun /bin/bash -c "source ~/.nvm/nvm.sh && cd /pro/HunDunPro/hundun-web && npm install --registry=https://registry.npmmirror.com"
# 前端打包
docker exec -it hundun /bin/bash -c "source ~/.nvm/nvm.sh && cd /pro/HunDunPro/hundun && python manage.py build"
# 更新
git pull
docker-compose restart
```

## 跨端设计
本项目由个人项目进行优化改版，对应移动端等代码持续升级开发中……
![hundun](https://github.com/user-attachments/assets/2971eb86-e33e-4d4a-94ae-3dc7bc73a55a)

