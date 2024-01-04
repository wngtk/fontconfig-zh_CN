# fontconfig-zh_CN

针对简体中文的 fontconfig 偏好配置。避免<span lang="ja">「门上插刀、直字拐弯、天顶加盖、船顶漏雨」</span>[^门上插刀]。

[^门上插刀]: https://blog.lilydjwg.me/2023/3/5/linux-fonts.216591.html

### 介绍

添加 `64-language-selector-prefer.conf` 到 `/etc/fonts/conf.d`。

### 安装字体

#### Arch Linux
```sh
sudo pacman -S ttf-liberation ttf-roboto gsfonts ttf-dejavu noto-fonts-cjk noto-fonts-emoji adobe-source-code-pro-fonts
```

gsfonts: Helvetica 被替换成 Nimbus Sans

一些可能被使用到的字体:

```sh
sudo pacman -S adobe-source-han-serif-cn-fonts wqy-zenhei
```

### 安装 `64-language-selector-prefer.conf`

###### Linux
```sh
curl -fLo /etc/fonts/conf.d/64-language-selector-prefer.conf --create-dirs \
    https://raw.githubusercontent.com/wngtk/fontconfig-zh_CN/main/64-language-selector-prefer.conf
```

### 安装 `fonts.conf`

###### Linux
```sh
curl -fLo "${XDG_CONFIG_HOME:-$HOME/.config}"/fontconfig/fonts.conf --create-dirs \
    https://raw.githubusercontent.com/wngtk/fontconfig-zh_CN/main/fonts.conf
```

### 参考配置

用户目录下的配置将在 `50-user.conf` 中被加载，可能会覆盖掉安装字体自带的配置。因此直接将 `64-language-selector-prefer.conf` 安装到系统目录反而配置最简单，其余的都交给字体包。
或者直接将英文字体写到中文字体的前面。

- https://szclsya.me/zh-cn/posts/fonts/linux-config-guide/
- https://github.com/meribold/dotfiles/tree/master/home/config/fontconfig
