GitHub 是一个基于 Git 的代码托管平台，被广泛用于项目管理、版本控制以及团队协作。下面为你详细介绍 GitHub 的基本使用方法：

### 一、注册与配置 GitHub 账号
首先，你要访问 [GitHub 官网](https://github.com) 完成账号注册。注册时需设置用户名、邮箱并创建密码。注册完成后，还需要配置 SSH 密钥（可选操作），这样就能更安全地推送和拉取代码，具体配置步骤如下：
1. 检查本地是否已有 SSH 密钥：
```bash
ls -al ~/.ssh
```
2. 若没有密钥，就生成一个新的 SSH 密钥：
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
3. 复制 SSH 公钥到剪贴板：
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```
4. 登录 GitHub，进入 Settings → SSH and GPG keys → New SSH key，把刚才复制的公钥粘贴进去。

### 二、创建与管理仓库
1. **创建新仓库**：
    - 点击 GitHub 界面右上角的“+”号，然后选择“New repository”。
    - 填写仓库名称、描述，设置仓库的公开或私有属性，还可以选择初始化 README 文件。
2. **克隆仓库到本地**：
```bash
git clone git@github.com:username/repo-name.git
```
3. **添加文件到仓库**：
```bash
git add .
git commit -m "Initial commit"
git push origin main
```

### 三、提交代码变更
1. **查看文件状态**：
```bash
git status
```
2. **暂存文件**：
```bash
git add filename.txt  # 添加单个文件
git add .           # 添加所有文件
```
3. **提交变更**：
```bash
git commit -m "Add new feature"
```
4. **推送到远程仓库**：
```bash
git push origin main
```

### 四、分支管理
1. **创建并切换到新分支**：
```bash
git checkout -b new-feature
```
2. **查看所有分支**：
```bash
git branch
```
3. **切换分支**：
```bash
git checkout main
```
4. **合并分支**：
```bash
git merge new-feature
```
5. **删除分支**：
```bash
git branch -d new-feature
```

### 五、协作开发流程
1. **Fork 仓库**：
    - 进入目标仓库页面，点击右上角的“Fork”按钮，将仓库复制到自己的账号下。
2. **克隆自己账号下的仓库**：
```bash
git clone git@github.com:your-username/forked-repo.git
```
3. **添加上游仓库**：
```bash
git remote add upstream git@github.com:original-owner/original-repo.git
```
4. **同步上游仓库更新**：
```bash
git fetch upstream
git merge upstream/main
```
5. **提交 Pull Request**：
    - 在自己的仓库页面点击“New Pull Request”按钮，选择要合并的分支，填写说明后提交。

### 六、其他 GitHub 功能
1. **Issue 管理**：
    - 用于追踪 bug、提出功能需求等。进入仓库的“Issues”标签页，点击“New issue”即可创建。
2. **Pull Request (PR)**：
    - 用于提交代码变更并请求他人审核。提交 PR 后，可以进行代码审查、讨论，之后再合并到主分支。
3. **GitHub Actions**：
    - 可实现自动化构建、测试和部署。在仓库的“.github/workflows”目录下创建 YAML 配置文件就能设置。
4. **Wiki**：
    - 用于项目文档编写。进入仓库的“Wiki”标签页即可开始创建和编辑。

### 七、常用命令速查表
```bash
# 配置用户信息
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

# 查看日志
git log

# 撤销暂存
git reset HEAD filename.txt

# 撤销提交
git revert <commit-hash>

# 查看远程仓库
git remote -v

# 添加远程仓库
git remote add origin git@github.com:username/repo-name.git
```

### 八、学习资源推荐
- [GitHub 官方文档](https://docs.github.com/)
- [Git 官方文档](https://git-scm.com/doc)
- [GitHub 学习实验室](https://lab.github.com/)
- [Pro Git 电子书](https://git-scm.com/book/en/v2)

通过上述步骤，你可以掌握 GitHub 的基本使用方法。如果在使用过程中遇到问题，可以查阅官方文档或者在社区中寻求帮助。
