# GitHub

## GitHub 配置 SSH Key

1. **生成 SSH 密钥对**

   使用 `ssh-keygen` 命令在本地生成一对全新的 SSH 密钥：

   ```bash
   # 生成 Ed25519 算法的密钥对，邮箱仅作为密钥备注，通常填写 GitHub 账号邮箱
   ssh-keygen -t ed25519 -C "<github-email>"
   ```

   如果旧系统不支持 Ed25519，可改用 RSA 4096 位密钥：

   ```bash
   ssh-keygen -t rsa -b 4096 -C "<github-email>"
   ```

   执行命令后，终端会提示保存路径及是否设置密码。首次配置且本机没有同名密钥时，可以按回车使用默认保存路径；是否设置密码短语可按个人安全需求决定。

   执行完毕后，系统会在当前用户主目录下的 `~/.ssh/` 路径中生成两个核心文件：

   - **`id_ed25519`（私钥）**：本地认证凭证。属于机密文件，不可泄露或上传至网络。

   - **`id_ed25519.pub`（公钥）**：对外公开的凭证。需配置在 GitHub 服务器上，用于验证与之匹配的私钥请求。

2. **在 GitHub 中配置公钥**

   接下来，需将本地生成的公钥（`id_ed25519.pub`）添加至 GitHub 账号。

   **配置路径**：登录 GitHub 网页端，点击头像，依次点击 **Settings** -> **SSH and GPG keys** -> **New SSH key**，打开配置表单。

   **表单配置**：

   - **Title**：自定义，一般写密钥的用途或设备名称。

   - **Key type**：保持默认的 **Authentication Key**。

   - **Key**：将 `id_ed25519.pub` 文件中的内容粘贴至此处。

   点击 **Add SSH key** 确认保存。

3. **测试连接状态**

   配置完成后，使用以下命令测试本地与 GitHub 之间的 SSH 连接是否建立：

   ```bash
   ssh -T git@github.com # 这里的 git@github.com 不用替换为注册邮箱
   ```

   > [!note]
   > 首次执行连接命令时，终端会触发安全警告并询问是否信任该主机的指纹 `Are you sure you want to continue connecting (yes/no/[fingerprint])?`。此时需手动输入 `yes` 并回车确认。

   **成功标识**：若终端返回如下包含 GitHub 用户名的信息，即代表 SSH 认证配置成功：

   > `Hi <github-username>! You've successfully authenticated, but GitHub does not provide shell access.`
