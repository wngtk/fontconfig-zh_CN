# fontconfig-zh_CN

针对中文的 fontconfig 偏好配置。

### 介绍

这是一个简单的字体偏好设置，使用 Noto 系列字体：

- 使用 `Noto Sans CJK SC` （又称 思源黑体）作为无衬线字体（`Sans-Serif`）
- 使用 `Noto Serif CJK SC` （又称 思源宋体）作为衬线字体（`Serif`）
- 使用 `Source Code Pro` 作为等宽字体（`monospace`）

### 安装字体

#### Arch Linux
```sh
sudo pacman -S noto-fonts noto-fonts-cjk noto-fonts-emoji adobe-source-code-pro-fonts
```

有几个好像没用到但是其他教程中推荐安装的字体：
```sh
sudo pacman -S adobe-source-han-serif-cn-fonts wqy-zenhei noto-fonts-extra 
```

### 安装配置

[下载 `fonts.conf`](https://raw.githubusercontent.com/wngtk/fontconfig-zh_CN/main/fonts.conf) 放到 `$XDG_CONFIG_HOME/fontconfig/fonts.conf`[^fonts.conf]。

###### Linux
```sh
curl -fLo "${XDG_CONFIG_HOME:-$HOME/.config}"/fontconfig/fonts.conf --create-dirs \
    https://raw.githubusercontent.com/wngtk/fontconfig-zh_CN/main/fonts.conf
```

[^fonts.conf]: man fonts.conf

