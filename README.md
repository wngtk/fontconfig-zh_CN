# fontconfig-zh_CN

针对简体中文的 fontconfig 偏好配置。避免<span lang="ja">「门上插刀、直字拐弯、天顶加盖、船顶漏雨」</span>[^门上插刀]。

[^门上插刀]: https://blog.lilydjwg.me/2023/3/5/linux-fonts.216591.html

### 介绍

这是一个简单的字体偏好设置，使用 Noto 系列字体：

- 使用 `Noto Sans CJK SC` （又称 思源黑体）作为无衬线字体（`Sans-Serif`）
- 使用 `Noto Serif CJK SC` （又称 思源宋体）作为衬线字体（`Serif`）
- 使用 `Noto Sans Mono` 作为等宽字体（`monospace`）

Note: 如果 `LANG=en_US.UTF-8` 在网页上“中文双引号”没有表现为全角，是因为首先匹配了 Noto Sans，但这似乎在安卓上也是这样的表现。但是这好像无伤大雅，“Worse is better”。对于更 Hack 的字体配置可以参考：

- https://catcat.cc/post/2021-03-07/

### 安装字体

#### Arch Linux
```sh
sudo pacman -S noto-fonts noto-fonts-cjk noto-fonts-emoji adobe-source-code-pro-fonts
```

有几个好像没用到但是[其他教程](https://arch.icekylin.online/guide/rookie/desktop-env-and-app.html#_6-%E5%AE%89%E8%A3%85%E5%9F%BA%E7%A1%80%E5%8A%9F%E8%83%BD%E5%8C%85)中推荐安装的字体：
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

### Credits

- https://szclsya.me/zh-cn/posts/fonts/linux-config-guide/
