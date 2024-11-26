# 操作

```bash
# 示例：Git命令使用流程
# 1. 初始化一个Git仓库
git init
# 2. 添加文件到暂存区
git add .
# 3. 提交更改
git commit -m "Initial commit"
# 4. 添加远程仓库地址
git remote add origin ***
*** 将更改推送到远程仓库
git push -u origin master
# 参数说明：
# init - 初始化一个空的Git仓库
# add - 添加文件到暂存区
# commit - 提交暂存区的更改
# remote add - 添加远程仓库
# push - 将本地更改推送到远程仓库
# 逻辑分析：
# 该代码块展示了使用Git进行版本控制的基本流程。初始化仓库后，开发者将代码添加到暂存区并提交，随后可以添加远程仓库地址并推送更改。
# 这个过程是配置管理中版本控制的基础操作，确保了代码的版本控制和协作开发的顺利进行。
```

## **1. 配置管理的关键任务梳理**

### **1.1 完成 SPM 项目的配置管理计划**

- **目标**：使用 Git 对项目的代码、文档等内容进行配置管理。
- 核心操作
  - 初始化 Git 仓库（`git init`）。
  - 进行版本控制（`git add`、`git commit`）。
  - 提交到远程仓库（`git push`）。
  - 创建分支进行功能开发（`git branch`、`git checkout`）。
  - 进行变更控制和合并（`git merge`、`git rebase`）。

------

### **1.2 配置标识、文档、代码的管理**

- **目标**：对项目的每一项内容进行标识和组织，确保清晰可追踪。
- 操作说明
  - **标识项目文件**：按照模块划分项目文件夹（如 `src/`、`docs/`）。
  - **跟踪文件变更**：使用 `git add` 和 `git commit` 提交文件变更。
  - 版本管理
    - 查看提交历史：`git log`。
    - 为关键版本打标签：`git tag`。

------

### **1.3 实验报告和结果清晰性**

- **目标**：确保配置管理的实验结果可视化且结构化。
- 操作说明
  - 提供分支变更记录：`git log --oneline --graph`。
  - 提供变更控制的具体流程记录：展示分支的创建、合并、冲突解决等操作。

------

### **1.4 制作实验视频**

- **目标**：录制 Git 操作的关键步骤，并进行解说。
- 操作说明
  - 展示仓库初始化和文件提交的过程。
  - 演示分支的创建与合并（包括冲突解决）。
  - 展示关键版本的恢复操作（`git reset` 或 `git checkout`）。

------

### **1.5 截止时间与提交**

- 提交截止日期是 **11月30日**，需准备好实验报告和视频文件。

------

## **2. 具体操作梳理与语法说明**

### **2.1 配置标识**

配置标识是对项目的所有关键文件和资源进行唯一标记，以便于跟踪和管理。

#### **(1) 文件夹结构和命名规范**

- 根据功能模块和文件类型组织文件夹，推荐以下结构：

  ```markdown
  SPM-Project/
  ├── docs/                   # 存放文档
  │   ├── requirements.md     # 需求文档
  │   ├── design.md           # 设计文档
  │   └── test-plan.md        # 测试计划
  ├── src/                    # 存放代码
  │   ├── module1/            # 模块1：登录模块
  │   │   └── login.py        # 登录功能代码
  │   ├── module2/            # 模块2：预算模块
  │   └── common/             # 公共模块
  ├── config/                 # 配置文件
  │   └── application.yml     # 应用配置
  └── README.md               # 项目说明
  ```

#### **(2) 配置项标识规则**

- 为项目中每个配置项（如文档、代码文件、配置文件）设定唯一的标识符。例如：

  - 文件命名采用模块名+功能描述的方式：

    - `login.py`: 登录模块的核心代码文件。
    - `test-plan.md`: 项目的测试计划文档。

  - 版本号以 

    ```bash
    vX.Y
    ```

     标记项目里程碑：

    - `v1.0`: 初始版本。
    - `v1.1`: 登录功能添加完成。
    - `v1.2`: 添加预算模块。

------

### **2.2 配置管理**

配置管理是对项目所有配置项（文件和资源）的控制和组织。以下是操作步骤：

#### **(1) 初始化 Git 仓库**

- 在项目目录下运行以下命令：

  ```bash
  git init
  ```

#### **(2) 跟踪文件**

- 添加项目文件到 Git：

  ```bash
  git add .
  git commit -m "Initialize project with basic structure"
  ```

#### **(3) 推送到远程仓库**

- 如果远程仓库已经存在（如 GitHub 上创建了仓库）：

  ```bash
  git remote add origin https://github.com/your-username/SPM-Project.git
  git branch -M main
  git push -u origin main
  ```

------

### **2.3 文档管理**

在项目中，文档管理通常包括需求文档、设计文档和测试文档。

#### **(1) 添加需求文档**

创建并提交需求文档文件：

```markdown
docs/requirements.md
```

示例内容：

```markdown
e# 项目需求文档

## 需求1：用户登录模块
- 用户能够通过用户名和密码登录。
- 登录失败时显示错误提示。

## 需求2：预算管理模块
- 用户能够查看、创建和修改预算数据。
```

提交到 Git 仓库：

```bash
git add docs/requirements.md
git commit -m "Add requirements document"
git push
```

#### **(2) 添加设计文档**

创建设计文档文件：

```markdown
docs/design.md
```

示例内容：

```markdown
# 项目设计文档

## 系统架构
- MVC 模型
- 数据库：MySQL
- 后端：Python Flask
- 前端：HTML + CSS + JavaScript

## 模块设计
### 登录模块
- 功能：验证用户名和密码。
- API：/api/login (POST)
```

提交到 Git：

```bash
git add docs/design.md
git commit -m "Add system design document"
git push
```

------

### **2.4 代码提交与版本控制**

#### **(1) 模拟代码的开发**

创建源代码文件夹 `src/` 和示例代码文件：

```makefile
src/module1/login.py
```

示例代码：

```python
# src/module1/login.py

def login(username, password):
    if username == "admin" and password == "1234":
        return "Login successful"
    else:
        return "Login failed"

if __name__ == "__main__":
    print(login("admin", "1234"))
```

提交到 Git：

```bash
git add src/module1/login.py
git commit -m "Add login module"
git push
```

#### **(2) 使用分支进行功能开发**

1. 创建一个新分支用于开发预算模块：

   ```bash
   git checkout -b feature/budget-module
   ```

2. 开发预算模块代码：

   ```markdown
   src/module2/budget.py
   ```

   示例代码：

   ```python
   # src/module2/budget.py
   
   def calculate_budget(income, expense):
       return income - expense
   
   if __name__ == "__main__":
       print(calculate_budget(5000, 2000))
   ```

3. 提交代码：

   ```bash
   git add src/module2/budget.py
   git commit -m "Add budget calculation module"
   git push -u origin feature/budget-module
   ```

#### **(3) 合并开发分支**

完成开发后，将 `feature/budget-module` 分支合并到主分支：

```bash
git checkout main
git merge feature/budget-module
git push
```

------

### **2.5 变更控制**

变更控制是 Git 中最重要的功能，用于追踪和管理文件的修改。

#### **(1) 提交变更**

1. 修改登录模块代码：

   ```python
   # src/module1/login.py
   
   def login(username, password):
       if username == "admin" and password == "1234":
           return f"Welcome, {username}"
       else:
           return "Login failed"
   ```

2. 提交变更：

   ```bash
   git add src/module1/login.py
   git commit -m "Enhance login module to include username in response"
   git push
   ```

#### **(2) 查看变更历史**

- 查看提交记录：

  ```bash
  git log --oneline --graph
  ```

  示例输出：

  ```pgp
  1234567 Enhance login module to include username in response
  abcdefg Add login module
  ```

- 查看某文件的变更历史：

  ```bash
  git log src/module1/login.py
  ```

#### **(3) 恢复到之前版本**

如果需要恢复到某个版本：

```bash
git reset --hard 提交哈希值
```

### **2.6 实验报告和视频录制**

#### 报告内容：

1. **工具使用说明**：简要介绍 Git 的使用方法。
2. **实验操作记录**：包含每个阶段的关键命令和效果截图。
3. **变更流程记录**：展示分支管理、版本管理和冲突解决的过程。

#### 视频内容：

1. 演示文件初始化、提交和推送。
2. 展示分支开发、合并和冲突解决。
3. 演示版本标签创建和版本回滚。

------

## **3. Git 命令语法详解**

| **命令**                    | **作用**                         |
| --------------------------- | -------------------------------- |
| `git init`                  | 初始化 Git 仓库                  |
| `git add .`                 | 将所有更改的文件添加到暂存区     |
| `git commit -m "说明"`      | 提交到本地仓库并添加提交信息     |
| `git branch 分支名`         | 创建一个新分支                   |
| `git checkout 分支名`       | 切换到指定分支                   |
| `git checkout -b 分支名`    | 创建并切换到一个新分支           |
| `git merge 分支名`          | 合并指定分支到当前分支           |
| `git log --oneline --graph` | 查看简洁的提交历史和分支图       |
| `git tag 标签名`            | 创建标签                         |
| `git push origin 分支名`    | 推送分支到远程仓库               |
| `git push --tags`           | 推送所有标签到远程仓库           |
| `git reset --hard 哈希值`   | 回滚到指定提交，并丢弃之后的更改 |



```e
SSM-Project/
├── docs/                   # 文档目录
│   ├── requirements/       # 各模块的需求文档
│   ├── design/             # 各模块的设计文档
│   ├── test-plans/         # 测试计划和报告
│   ├── user-manual/        # 用户手册
├── src/                    # 源代码目录
│   ├── module1/            # 模块 1（预算管理）
│   ├── module2/            # 模块 2（内控登录）
│   ├── module3/            # 模块 3（生产数据管理）
│   └── common/             # 公共模块和工具函数
├── test/                   # 测试相关代码和脚本
│   ├── unit/               # 单元测试代码
│   ├── integration/        # 集成测试代码
│   └── scripts/            # 自动化测试脚本
├── config/                 # 配置文件
│   ├── database/           # 数据库配置文件
│   ├── server/             # 服务端配置文件
│   └── application.yml     # 应用程序配置
├── scripts/                # 项目脚本
│   ├── build.sh            # 构建脚本
│   ├── deploy.sh           # 部署脚本
│   └── clean.sh            # 清理脚本
├── README.md               # 项目介绍
├── LICENSE                 # 许可证文件
└── .gitignore              # Git 忽略文件

```

