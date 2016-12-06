# 前言II (React 构建工具介绍)

工欲善其事，必先利其器。React 的火爆得力于来自社区的工具，而 React 也推动了这些工具的进步。笔者是刚刚接触前端,初学react,这里介绍一些,构建react工程需要用到的一些工具 . 如 `npm`,`nvm`,`webpack`,`babel`,`eslint`

## npm
NPM（Node Package Manager）是 Node.js 下的主流套件管理工具.npm用于下载和管理react相关的依赖包,是构建react环境不可缺少的工具.node.js 中就自带有nmp,所以我们要安装node.
**安装node**

1, 如果安装了nvm,直接使用命令安装node.js
```bash
nvm install node
```
2, 如果不想使用nvm,使用macOS可以通过homebrew安装
```bash
brew install node
```
3, 还可以去node官方网站下载相应的安装包进行安装.
官网: [https://nodejs.org/zh-cn/][1]
## nvm
在开发的过程中,我们可能需要切换node的版本,所以建议使用nvm (全名为 node.js version manager) 来管理node.
nvm的github地址  [https://github.com/creationix/nvm][2]

**安装nvm**
对于macOS用户

1, 使用 `cURL`
```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash
```
或者 `Wget`
```bash
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.32.1/install.sh | bash
```

2, 在 (~/.bash_profile, ~/.zshrc, ~/.profile, or ~/.bashrc).任意配置文件中(建议在`~/.bash_profile`)配置
```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```
3, 保存生效
```bash
source ~/.bash_profile
```

windows 用户 
nvm-windows gitlub地址 : [https://github.com/coreybutler/nvm-windows][3]

直接选择安装包下载安装即可.
![enter description here](./img/nvm_setup_window.png)

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


  [1]: https://nodejs.org/zh-cn/
  [2]: https://github.com/creationix/nvm
  [3]: https://github.com/coreybutler/nvm-windows