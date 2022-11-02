# 安装zsh和git

```
sudo apt-get install git zsh
```

# 安装 ohmyzsh

```
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

# 环境变量

之前的环境变量都是配置在`/etc/profile`中，如果使用zsh，环境变量需要配置在`/etc/zsh/zprofile`中

# zsh_to_fish

https://github.com/abhigenie92/zsh_to_fish

How to make zsh like fish?


1. Install oh-my-zsh
```
sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

2. Clone necessary plugins.
```
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

3. Add plugins to `~/.zshrc` as
```
plugins = ( [plugins...] zsh-autosuggestions history-substring-search zsh-syntax-highlighting)
```
Note: make sure zsh-syntax-highlighting is the last one in the above list.

4. Fix background theme issues(, not necessary depends on your theme.)
Add the following line to your `~/.zshrc`.
```
ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=white'
```

5. Restart zsh
```
source ~/.zshrc
```

# 中文支持

```sh
sudo apt-get install locales locales-all
```

.zshrc中配置LANG LANGUAGE

# thefuck

```sh
sudo apt install python3-dev python3-pip
sudo pip3 install thefuck
```

.zshrc配置别名

# autojump

```sh
sudo apt install autojump
```

.zshrc中配置插件
