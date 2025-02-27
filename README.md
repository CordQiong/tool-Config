# tool-Config


## 安装 oh my zsh
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```



## 设置git bash 默认使用 zsh
```
vim ~/.bashrc
```
输入
```
if [ -t 1 ]; then
  exec zsh
fi
```
设置WindowsTermianl 默认使用Git Bash



## 配置 zsh
```
vim ~/.zshrc
```

## 刷新zsh 配置
```
source ~/.zshrc
```

## zsh 添加开启终端操作
在.zshrc文件中添加下面代码
```
#开启终端代理
function proxyon() {
	export http_proxy="http://127.0.0.1:7890"
	export https_proxy=$http_proxy
	echo -e "terminal proxy on"

}

#关闭终端代理
function proxyoff() {
	unset http_proxy
	unset https_proxy
	echo -e "terminal proxy off"
}
```

7890为梯子固定的端口号。

## 安装插件

### 进入插件目录
```
cd ~/.oh-my-zsh/custom/plugins
```

### 安装zsh-autosuggestions 自动补全插件
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### 安装高亮插件 

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

如果安装失败，可以挂上梯子，然后终端执行 proxyon 命令 打开代理再试。

### 设置插件
在.zshrc 文件中添加 
plugins=(git xxx插件名 xxx插件名 z)