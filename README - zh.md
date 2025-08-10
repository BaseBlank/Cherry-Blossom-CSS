# Cherry-Blossom-CSS
Cherry-Blossom-CSS项目的大多数原始的CSS代码来自于各个互联网社区的分享，原作者将优秀的CSS代码在社区中进行分享，其中本人喜欢的一些CSS代码，我在使用过程中会发现存在一些不合理之处或者bug，本项目本项目在保留原作灵感的基础上，依据自己的需求进行了修改，统一修复了这些问题，以解决bug与潜在的不合理之处。

其中 original version 版本为原作者版本，patch version 为修复bug后的补丁版本。

本项目所有测试均在Windows 11系统上进行，如果MacOS用户遇到问题，本项目暂时无法进行修复，但是本项目积极欢迎MacOS系统相关的修复代码贡献。

# 主题1：歌蕾蒂娅-返航

原始CSS代码出处：

[Cherry Studio 题库](https://cherrycss.com/)

[cherry-studio主题分享 双色主题：歌蕾蒂娅-返航](https://linux.do/t/topic/432753)

https://linux.do/t/topic/432753

CSS效果：

![歌蕾蒂娅-返航 主题](https://github.com/BaseBlank/Cherry-Blossom-CSS/blob/main/imgs/%E6%AD%8C%E8%95%BE%E8%92%82%E5%A8%85-%E8%BF%94%E8%88%AA%20%E4%B8%BB%E9%A2%98.png)

修复的代码的位置：

[歌蕾蒂娅-返航](https://github.com/BaseBlank/Cherry-Blossom-CSS/tree/main/CSS/01%20%E6%AD%8C%E8%95%BE%E8%92%82%E5%A8%85-%E8%BF%94%E8%88%AA)

本项目修复的说明：

主要是“字体选择”问题，主要的修改就是字体，本项目修改为了：优先使用小米的Misans，如果电脑里没有Misans，就使用微软雅黑。所以，使用这个修复版本的字体，前提是电脑安装小米字体Misans。

本修复版本只在黑色模式下进行了充分测试。

[Misans]: https://hyperos.mi.com/font/download

Windows系统安装字体的教程很容易找到。

使用的字体是Misans Regular，不同粗细的字体可以自行去CSS文件中进行替换，例如"MiSans Medium"。

# 主题2：CherryYou

原始CSS代码出处：

[CherryYou](https://linux.do/t/topic/762150)

https://linux.do/t/topic/762150

CSS效果

![cherryou主题](https://github.com/BaseBlank/Cherry-Blossom-CSS/blob/main/imgs/CherryYou%E4%B8%BB%E9%A2%98.png)

修复的代码的位置：

[CherryYou](https://github.com/BaseBlank/Cherry-Blossom-CSS/tree/main/CSS/02%20CherryYou)

本项目修复的说明：

## 1 在线资源加载转换为本地加载

在线资源全部修复为本地资源加载，包括字体与背景图像。所以，你要使用本项目的修复版本代码，就要将依赖的字体在电脑上进行安装，将背景图片下载到本地；

如果你嫌使用本地资源加载操作起来很麻烦，那么就把patch version版本的原始代码的前几行取消注释，或者手动自己添加进去（就是下面的12行代码）。

### 1.1 背景图像

原始的：

```css
@import url('https://fonts.googleapis.com/css2?family=Audiowide:wght@400&family=Noto+Sans+SC:wght@300;400;500;700&display=swap');
@import url('https://cdn.bootcdn.net/ajax/libs/lxgw-wenkai-screen-webfont/1.7.0/style.min.css');
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&display=swap');

/* ===== 背景图片（别问图片链接了球球了） ===== */
:root {
  /* 深色模式背景图片 */
  --cherry-bg-image-dark: url('https://w.wallhaven.cc/full/j8/wallhaven-j831k5.png');
  /* 浅色模式背景图片 */
  --cherry-bg-image-light: url('https://w.wallhaven.cc/full/2k/wallhaven-2k33rx.jpg');
}

```

修改后：

```css
/* Fonts are now installed locally on Windows 11 - no need for web imports */
/* @import url('https://fonts.googleapis.com/css2?family=Audiowide:wght@400&family=Noto+Sans+SC:wght@300;400;500;700&display=swap'); */
/* @import url('https://cdn.bootcdn.net/ajax/libs/lxgw-wenkai-screen-webfont/1.7.0/style.min.css'); */
/* @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&display=swap'); */

/* ===== 背景图片（别问图片链接了球球了） ===== */
:root {
  /* 深色模式背景图片 */
  --cherry-bg-image-dark: url('file:///C:/Users/YourUsername/Pictures/wallhaven-j831k5.png');
  /* 浅色模式背景图片 */
  --cherry-bg-image-light: url('file:///C:/Users/YourUsername/Pictures/wallhaven-2k33rx.jpg');
}

```

文件路径

> C:/Users/YourUsername/Pictures/wallhaven-2k33rx.jpg

替换为你自己存放背景图片的文件路径，Windows路径怎么转换为CSS代码的路径，这个写法直接问AI，这么简单的问题任何一个AI都能答对。

### 1.2 字体

涉及到四种字体：

- **Audiowide**：来自 Google Fonts ——用于标题和主要UI的显示字体
- **Noto Sans SC**：来自 Google Fonts ——支持中文的字体，包含多种字重（300、400、500、700）
- **LXGW WenKai Screen**：来自 bootcdn.net 的中文字体——屏幕优化的中文网页字体
- **JetBrains Mono**：来自 Google Font ——用于代码的等宽字体（字重：400、500、600）

这些字体你都需要安装在本地电脑上。谷歌搜索自己很容易搜到。

嫌麻烦不想安装，就每次在线加载字体，开头的这几行保持与original version 版本一致，patch version 使用的是本地加载，所以把这几行直接注释了。

```css
@import url('https://fonts.googleapis.com/css2?family=Audiowide:wght@400&family=Noto+Sans+SC:wght@300;400;500;700&display=swap');
@import url('https://cdn.bootcdn.net/ajax/libs/lxgw-wenkai-screen-webfont/1.7.0/style.min.css');
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&display=swap');
```

## 2 文字大小修改

original version 版本使用的默认字体大小为16，使用中个人感觉太小了，所以进行了修改，如下：

- **基准字号**：16.5px
- **内容区域**：16.5px × 1.05em = **17.325px**
- 比默认16px增大约**8.3%**

## 3 模型列表显示bug

bug显示如下：

![模型列表显示bug](https://github.com/BaseBlank/Cherry-Blossom-CSS/blob/main/imgs/%E6%A8%A1%E5%9E%8B%E5%88%97%E8%A1%A8%E6%98%BE%E7%A4%BAbug.png)

original version 版本的CSS中使用了`div[class*="ListItemContainer-"]`选择器（第224-229行），它会匹配任何类名中包含“ListItemContainer-”的div。这既包括：

- 用于侧边栏/导航的通用ListItemContainer组件
- 用于模型管理模态框的特定ModelListItemContainer组件

CSS规则中强制设置的`max-width: 120px`本意是针对侧边栏项，但错误地应用到了需要全宽以展示模型名称和描述的模型列表项。

## 4 数据设置与其他设置显示bug

数据设置与其他设置中，第二列都会显示错误，图标与文字相互挤压导致上下排列。

修复后的文件CherryYou patch version-v04.css



> 如果Cherry-Blossom-CSS项目中涉及到的任何CSS代码的引用来源标注不正确，请原作者通过Github issue与本项目进行联系，提供可信的说明与佐证后，本项目会立刻进行引用错误的修改。





