# 前言II (React 构建工具介绍)

工欲善其事，必先利其器。React 的火爆得力于来自社区的工具，而 React 也推动了这些工具的进步。笔者是刚刚接触前端,初学react,这里介绍一些,构建react工程需要用到的一些工具 . 如 `npm`,`nvm`,`webpack`,`babel`,`eslint`

## npm

## nvm
在开发的过程中,我们可能需要切换node的版本,所以建议使用nvm (全名为 node.js version manager) node的版本控制工具.
nvm的github地址  [https://github.com/creationix/nvm][1]

**安装nvm**
对于macOS用户
1. 使用 `cURL`
```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash
```
或者 `Wget`
```bash
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash
```

2. 在 (~/.bash_profile, ~/.zshrc, ~/.profile, or ~/.bashrc).任意配置文件中(建议在`~/.bash_profile`)配置
```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```
3. 保存生效
```bash
source ~/.bash_profile
```

windows 用户 
nvm-windows gitlub地址 : [https://github.com/coreybutler/nvm-windows][2]

直接选择安装包下载安装即可.
![enter description here][3]

**nvm 基本使用**
安装指定版本的node
```bash
nvm install version_code # (4.2.2)
```
安装最新版本
```bash
nvm install node
```

版本切换
```bash
nvm use 4.2.2
```

切换到最新版：
```bash
nvm use node
```

删除某个版本:
```bash
nvm uninstall 4.2.2
```

列出本地的所有版本:
```bash
nvm ls 
```

列出服务器的所有版本
```bash
nvm ls-remote
```

其他指令请查询官网.


  [1]: https://github.com/creationix/nvm
  [2]: https://github.com/coreybutler/nvm-windows
  [3]: ./images/nvm_setup_window.png "nvm_setup_window.png"