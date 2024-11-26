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

根据实验要求，操作分为几个阶段：

### **阶段 1：初始化仓库并组织项目结构**

#### 操作步骤：

1. 在本地创建一个文件夹作为项目根目录：（这一步直接在本地进行手动操作更方便）

   ```bash
   mkdir SPM-Project
   cd SPM-Project
   ```

2. 初始化 Git 仓库：

   ```bash
   git init
   ```

3. 创建项目的文件结构：

   ```bash
   SPM-Project/
   ├── docs/                   # 存放文档
   │   ├── requirements.md     # 需求文档
   │   ├── design.md           # 设计文档
   ├── src/                    # 存放代码
   │   ├── main.py             # 示例代码文件
   ├── README.md               # 项目介绍
   ```

4. 将文件添加到仓库并提交：

   ```bash
   git add .
   git commit -m "Initialize project with structure and initial files"
   ```

5. 推送到远程仓库：

   ```bash
   git remote add origin https://github.com/your-username/SPM-Project.git
   git branch -M main
   git push -u origin main
   ```

------

### **阶段 2：分支开发与变更控制**

#### 操作步骤：

1. **创建新功能分支**：

   - 为开发登录模块创建分支：

     ```bash
     git checkout -b feature/login-module
     ```

   - 修改代码后提交：

     ```bash
     git add .
     git commit -m "Add login functionality"
     ```

2. **合并分支**：

   - 切换到主分支：

     ```bash
     git checkout main
     ```

   - 合并开发分支：

     ```bash
     git merge feature/login-module
     ```

3. **解决冲突**：

   - 如果合并时出现冲突，Git 会提示冲突文件：

     ```pgp
     CONFLICT (content): Merge conflict in src/main.py
     ```

   - 打开冲突文件，按照需求修改冲突部分，保存后运行：

     ```bash
     git add src/main.py
     git commit
     ```

------

### **阶段 3：版本管理**

#### 操作步骤：

1. **查看版本历史**：

   ```bash
   git log --oneline --graph
   ```

   示例输出：

   ```pgp
   * abc1234 (HEAD -> main) Add login functionality
   * def5678 Initialize project with structure and initial files
   ```

2. **创建版本标签**：

   - 为稳定版本创建标签：

     ```bash
     git tag v1.0
     git push origin v1.0
     ```

3. **回滚版本**：

   - 如果需要回滚到某个历史版本：

     ```bash
     git reset --hard 提交哈希值
     ```

------

### **阶段 4：实验报告和视频录制**

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

