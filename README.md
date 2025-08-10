# Cherry-Blossom-CSS
A collection of refined and bug-fixed community themes for Cherry Studio.

Most of the original CSS code for the Cherry-Blossom-CSS project comes from various online communities, where the original authors shared excellent CSS snippets. Some of these CSS codes are among my personal favorites, but during use, I discovered certain issues or bugs. This project modifies those codes to suit my own needs while preserving the spirit of the originals, and it systematically fixes these problems to address bugs and any potential issues.

The original version refers to the authors' original code, while the patch version contains the bug-fixed patches.

All testing for this project has been done on Windows 11. If MacOS users encounter problems, the project is currently unable to provide a fix, but contributions of relevant MacOS fixes are very welcome.

<p align="center">
  <a href="README - zh.md">
    <img src="https://img.shields.io/badge/中文文档-README--zh.md-blue?style=flat-square" alt="中文文档">
  </a>
</p>



# Theme 1：歌蕾蒂娅-返航

Original CSS code source:

[Cherry Studio 题库](https://cherrycss.com/)

[cherry-studio主题分享 双色主题：歌蕾蒂娅-返航](https://linux.do/t/topic/432753)

CSS effects:

![歌蕾蒂娅-返航 主题](https://github.com/BaseBlank/Cherry-Blossom-CSS/blob/main/imgs/%E6%AD%8C%E8%95%BE%E8%92%82%E5%A8%85-%E8%BF%94%E8%88%AA%20%E4%B8%BB%E9%A2%98.png)

The location of the fixed code:

[歌蕾蒂娅-返航](https://github.com/BaseBlank/Cherry-Blossom-CSS/tree/main/CSS/01%20%E6%AD%8C%E8%95%BE%E8%92%82%E5%A8%85-%E8%BF%94%E8%88%AA)

Explanation of the fixes in this project:

The main issue addressed is "font selection," with the primary modification being the font itself. In this project, MiSans by Xiaomi is given priority—if your computer doesn't have MiSans installed, it will use Microsoft YaHei instead. So, to use the font in this patched version, you’ll need to have the MiSans font installed on your computer.

This patched version has only been thoroughly tested in dark mode.

[Misans]: https://hyperos.mi.com/font/download

It's easy to find tutorials online for installing fonts on Windows.

The font used is MiSans Regular. If you want different font weights, you can replace it in the CSS file yourself—for example, use "MiSans Medium."

# Theme 2：CherryYou

Original CSS code source:

[CherryYou](https://linux.do/t/topic/762150)

CSS effects:

![cherryou主题](https://github.com/BaseBlank/Cherry-Blossom-CSS/blob/main/imgs/CherryYou%E4%B8%BB%E9%A2%98.png)

The location of the fixed code:

[CherryYou](https://github.com/BaseBlank/Cherry-Blossom-CSS/tree/main/CSS/02%20CherryYou)

Explanation of the fixes in this project:

## 1. Switching Online Resource Loading to Local Loading

All online resources have been replaced with local resource loading, including fonts and background images. Therefore, to use the patched version of this project, you’ll need to install the required fonts on your computer and download the background images locally.

If you find working with local resources too inconvenient, you can simply uncomment the first few lines of code in the original patch version, or manually add them yourself (these are the 12 lines of code shown below).

### 1.1 Background Image

Original:

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

After modification:

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

File path: 

> C:/Users/YourUsername/Pictures/wallhaven-2k33rx.jpg

Replace it with the file path where you’ve saved your background image. If you’re not sure how to convert a Windows path to a CSS file path, just ask an AI—any AI can answer such a simple question.

### 1.2 Fonts

There are four fonts involved:

- **Audiowide**: From Google Fonts—used as a display font for headings and main UI
- **Noto Sans SC**: From Google Fonts—a font that supports Chinese, available in multiple weights (300, 400, 500, 700)
- **LXGW WenKai Screen**: A Chinese web font from bootcdn.net—optimized for readability on screens
- **JetBrains Mono**: From Google Fonts—a monospaced font for code (weights: 400, 500, 600)

You’ll need to install all of these fonts locally on your computer. Just search on Google—they’re easy to find.

If you don’t want to bother with installation and prefer loading fonts online each time, keep the few lines at the beginning the same as in the original version. The patch version uses local loading, so those lines are commented out.

```css
@import url('https://fonts.googleapis.com/css2?family=Audiowide:wght@400&family=Noto+Sans+SC:wght@300;400;500;700&display=swap');
@import url('https://cdn.bootcdn.net/ajax/libs/lxgw-wenkai-screen-webfont/1.7.0/style.min.css');
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&display=swap');
```

## 2. Font Size Adjustment

The original version used a default font size of 16, which felt too small to me, so I made the following changes:

- **Base font size**: 16.5px
- **Content area**: 16.5px × 1.05em = **17.325px**
- This is about **8.3%** larger than the default 16px

## 3. Model List Display Bug

The bug appears as follows:

![模型列表显示bug](https://github.com/BaseBlank/Cherry-Blossom-CSS/blob/main/imgs/%E6%A8%A1%E5%9E%8B%E5%88%97%E8%A1%A8%E6%98%BE%E7%A4%BAbug.png)

 fix: prevent model list items from inheriting sidebar width constraints

  The selector `div[class*="ListItemContainer-"]` was catching both sidebar items
  and model list items. Added `:not([class*="ModelListItemContainer-"])` to exclude
  model list components, fixing the truncated display in Cherry Studio's model
  management modal while preserving sidebar styling.



## 4 Display Bug in Data Settings and Other Settings

In both Data Settings and Other Settings, the second column always displays incorrectly, with the icon and text squeezed together and stacking vertically.

CherryYou patch version-v04.css

This commit fixes a UI bug in the Settings menu where navigation items were incorrectly stacked vertically and long text was truncated. The root cause was an overly broad CSS selector that improperly targeted menu list items, disrupting their flexbox layout. The fix removes this problematic selector and introduces new, specific rules to enforce the correct horizontal alignment for icons and text. Additionally, width and overflow properties were adjusted to ensure full menu item text is always visible without truncation.

Resolved a CSS layout issue in the Settings menu caused by the overly broad `div[class^="SettingGroup-"] label` selector. This selector inadvertently applied container styles to menu list items, breaking their flex layout. The fix removes this rule entirely and adds specific styles for `div[class*="ListItemContent"]` to enforce `display: flex` and for `.ant-typography` to prevent text truncation, fully restoring the intended horizontal menu design.



> If any of the CSS code sources cited in the Cherry-Blossom-CSS project are incorrect, original authors are encouraged to contact this project via a Github issue. Once credible information and evidence are provided, any citation errors will be corrected immediately.





