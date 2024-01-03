# fontconfig-zh_CN

针对简体中文的 fontconfig 偏好配置。避免<span lang="ja">「门上插刀、直字拐弯、天顶加盖、船顶漏雨」</span>[^门上插刀]。

[^门上插刀]: https://blog.lilydjwg.me/2023/3/5/linux-fonts.216591.html

### 介绍

这是一个简单的字体偏好设置，设置使用 Fontconfig 的程序默认使用 Noto 字体和 Source Code Pro.

- Sans Serif 默认 Note Sans, Noto Sans CJK SC
- Serif 默认 Noto Serif, Noto Serif CJK SC
- monospace 默认 Source Code Pro

### 安装字体

#### Arch Linux
```sh
sudo pacman -S noto-fonts noto-fonts-cjk noto-fonts-emoji adobe-source-code-pro-fonts
```

一些可能被使用到的字体:

```sh
sudo pacman -S adobe-source-han-serif-cn-fonts wqy-zenhei noto-fonts-extra ttf-liberation ttf-roboto 
```

### 安装配置

[下载 `fonts.conf`](https://raw.githubusercontent.com/wngtk/fontconfig-zh_CN/main/fonts.conf) 放到 `$XDG_CONFIG_HOME/fontconfig/fonts.conf`[^fonts.conf]。

###### Linux
```sh
curl -fLo "${XDG_CONFIG_HOME:-$HOME/.config}"/fontconfig/fonts.conf --create-dirs \
    https://raw.githubusercontent.com/wngtk/fontconfig-zh_CN/main/fonts.conf
```

[^fonts.conf]: man fonts.conf

### 参考配置

- https://szclsya.me/zh-cn/posts/fonts/linux-config-guide/
- https://github.com/meribold/dotfiles/tree/master/home/config/fontconfig
