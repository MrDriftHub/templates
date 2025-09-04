# python 项目模板

```python
# -*- coding: UTF-8 -*-
"""
@Project    ：${PROJECT_NAME}/${DIR_PATH}
@File       ：${FILE_NAME}
@IDE        ：${PRODUCT_NAME} 
@Author     ：Mr.Drift.
@Date ：${DATE} ${TIME}  
@description：  
"""
```  

## 系统要求

- **Python**: 已安装python或有python的虚拟环境
- **项目管理工具**: uv

>>> 注意：项目工具和环境因个人爱好而定，只是本人偏向于uv进行项目管理，主要还是项目模板；

## 快速开始

### 1. 环境准备

确保系统已安装Python和uv：

```bash

python --version
uv --version
```

### 2. 克隆项目

```bash

git@github.com:MrDriftHub/templates.git
cd python-script
```

### 3. 初始化虚拟环境

>>> 注意：由于从github下面拉取时并不是一个项目模板，可能包含整个仓库中的项目模板，所以拉取下来后复制该项目模板并修改项目名称即可；

```bash

uv init
uv venv
```

### 4. 激活虚拟环境

```bash

source .venv/bin/activate
```

## 项目结构说明

```text
python-script
├── .venv                          # Python虚拟环境目录，隔离项目依赖，避免包版本冲突
├── app                            # 主应用程序源码根目录，包含所有业务逻辑和应用结构
│   ├── docs                       # 应用模块相关文档目录，存放开发、设计或配置文档
│   │   └── dev.sql                # 开发环境数据库初始化脚本，用于创建表结构和测试数据
│   ├── src                        # 源代码主目录，包含项目所有模块化代码
│   │   ├── api                    # API路由定义模块，负责HTTP端点注册与请求分发
│   │   ├── config                 # 配置管理模块，集中管理环境变量、数据库连接等配置
│   │   ├── constants              # 常量定义模块，存放项目中使用的全局常量（如状态码、路径等）
│   │   ├── context                # 请求上下文管理模块，用于传递用户、权限等运行时信息
│   │   ├── core                   # 核心框架逻辑模块，封装项目基础功能
│   │   │   ├── database           # 数据库核心配置与连接管理，如Session、Engine初始化
│   │   │   └── entities           # 核心领域实体定义，用于跨层数据传递（可与ORM模型区分）
│   │   ├── entities               # 应用层实体模型，描述业务对象（通常映射为Pydantic模型）
│   │   ├── enums                  # 枚举类型定义，如状态、类型等结构化常量
│   │   ├── exceptions             # 自定义异常类，统一错误处理机制
│   │   ├── libs                   # 第三方库封装或工具类库，避免直接依赖外部包
│   │   ├── middleware             # 请求中间件，实现日志、认证、CORS等横切逻辑
│   │   ├── models                 # 数据层模型（ORM模型），如SQLAlchemy定义的数据表结构
│   │   ├── repository             # 数据访问层，封装对数据库的CRUD操作
│   │   ├── schemas                # 控制层架构模型（如Pydantic模型），用于请求/响应数据校验与序列化
│   │   ├── services               # 业务逻辑层，实现核心业务规则与流程编排
│   │   ├── tasks                  # 异步任务模块，如Celery任务或后台作业
│   │   ├── utils                  # 通用工具函数，如时间处理、字符串操作等
│   │   ├── static                 # 静态资源目录（如CSS、JS、图片），供前端使用
│   │   └── test                   # 测试代码目录，存放单元测试、集成测试用例
│   └── docker                     # Docker相关配置文件，支持容器化部署
│       ├── redis                  # Redis服务的Docker配置或初始化脚本
│       │   └── __init__.py        # 空文件，可能用于Python包识别（非必需）
│       ├── docker-compose.yml     # 多容器编排配置文件，定义服务依赖与网络
│       └── Dockerfile             # 构建应用镜像的指令文件，定义运行环境
├── docs                           # 项目级文档目录，存放架构设计、API文档等
├── .env                           # 环境变量配置文件（本地开发用），存储敏感信息或配置
├── .env.example                   # 环境变量示例文件，提示所需配置项（不包含敏感数据）
├── .python-version                # 指定项目使用的Python版本（用于pyenv等版本管理工具）
├── pyproject.toml                 # 现代Python项目配置文件，定义依赖、构建、工具配置（如Poetry）
├── README.md                      # 项目说明文档，包含简介、安装、使用方法等
└── requirements.txt               # 传统依赖列表文件，列出项目所需Python包及版本

```


