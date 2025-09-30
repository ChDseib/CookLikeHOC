# 设计系统文档 (Design System Documentation)

## 概述

本文档说明了 CookLikeHOC 网站的 Apple 风格设计系统。设计目标是创建一个简洁、优雅、易用的食谱浏览体验，特别针对移动端进行了优化。

## 设计理念

### Apple 设计语言特征

1. **简洁性 (Simplicity)**
   - 减少视觉噪音
   - 清晰的信息层级
   - 充足的留白空间

2. **优雅 (Elegance)**
   - 精致的字体排版
   - 流畅的动画过渡
   - 一致的圆角设计

3. **功能性 (Functionality)**
   - 直观的导航
   - 易于触摸的交互元素
   - 响应式设计

## 配色方案

### 浅色模式 (Light Mode)

主色调采用黑白灰系统，避免过多彩色干扰：

- **背景色**
  - 主背景: `#ffffff`
  - 次背景: `#f5f5f7`
  - 柔和背景: `#fafafa`

- **文字色**
  - 主文字: `#1d1d1f`
  - 次文字: `#6e6e73`
  - 辅助文字: `#86868b`

- **边框色**
  - 边框: `#d2d2d7`
  - 分隔线: `#e5e5e7`

- **强调色**
  - 品牌色: `#000000`

### 暗色模式 (Dark Mode)

- **背景色**
  - 主背景: `#000000` (纯黑)
  - 次背景: `#1c1c1e`
  - 柔和背景: `#2c2c2e`

- **文字色**
  - 主文字: `#f5f5f7`
  - 次文字: `#a1a1a6`
  - 辅助文字: `#86868b`

- **强调色**
  - 品牌色: `#ffffff`

## 字体系统

### 字体族

优先使用 Apple 的 SF Pro 字体系列：

```css
font-family: -apple-system, BlinkMacSystemFont, 
             "SF Pro SC", "SF Pro Display", "SF Pro Text",
             "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei",
             system-ui, sans-serif;
```

### 字体大小层级

#### 桌面端
- H1: 40px (首页可达56px)
- H2: 28px
- H3: 21px
- 正文: 17px
- 小字: 15px

#### 移动端
- H1: 32px (首页40px)
- H2: 24px
- H3: 19px
- 正文: 16px
- 小字: 14px

### 字重 (Font Weight)

- 常规文本: 400
- 次要强调: 500
- 标题: 600
- 超级标题: 700

## 间距系统

使用 8px 基准的间距系统：

- `--vp-space-1`: 4px
- `--vp-space-2`: 8px
- `--vp-space-3`: 12px
- `--vp-space-4`: 16px
- `--vp-space-5`: 24px
- `--vp-space-6`: 32px
- `--vp-space-7`: 48px

## 圆角设计

- 小圆角: 8px (按钮、代码块)
- 标准圆角: 12px (卡片、图片)
- 大圆角: 16px (特殊容器)
- 超大圆角: 980px (胶囊按钮)

## 阴影系统

使用轻量级阴影增加层次感：

- 层级1: `0 1px 2px rgba(0, 0, 0, 0.04)`
- 层级2: `0 2px 12px rgba(0, 0, 0, 0.08)`
- 层级3: `0 4px 16px rgba(0, 0, 0, 0.12)`

## 特殊效果

### 毛玻璃效果 (Frosted Glass)

导航栏使用毛玻璃效果，保持现代感：

```css
background-color: rgba(255, 255, 255, 0.72);
backdrop-filter: saturate(180%) blur(20px);
-webkit-backdrop-filter: saturate(180%) blur(20px);
```

### 渐变文字

首页标题使用渐变效果：

```css
background: linear-gradient(135deg, #1d1d1f 0%, #6e6e73 100%);
-webkit-background-clip: text;
-webkit-text-fill-color: transparent;
```

## 移动端优化

### 触摸目标

- 最小高度: 44px (符合 Apple 人机界面指南)
- 按钮内边距: 12px 24px

### 响应式断点

- 移动端: < 768px
- 桌面端: >= 768px

### 移动端特殊优化

1. **导航菜单**: 汉堡菜单，全屏展开
2. **字体缩放**: 适当减小字号
3. **间距调整**: 更紧凑的布局
4. **触摸优化**: 增大可点击区域

## 动画与过渡

### 过渡时长

- 快速: 0.2s (hover状态)
- 标准: 0.3s (背景切换、主题切换)

### 缓动函数

使用 `ease` 缓动，提供自然的动画效果

### 常见动画

- 按钮hover: `translateY(-1px)` + 阴影变化
- 卡片hover: `translateY(-2px)` + 阴影加深
- 链接hover: `opacity: 0.7`

## 组件设计规范

### 按钮

**主按钮 (Primary)**
- 背景: 黑色 (浅色模式) / 白色 (暗色模式)
- 文字: 白色 / 黑色
- 圆角: 980px (胶囊形)
- 内边距: 12px 24px

**次按钮 (Secondary)**
- 背景: `rgba(0, 0, 0, 0.04)` / `rgba(255, 255, 255, 0.08)`
- 文字: 主文字色
- 圆角: 980px

### 卡片

- 背景: 次背景色
- 边框: 1px 实线
- 圆角: 12px
- 内边距: 24px
- Hover: 上移2px + 阴影加深

### 图片

- 圆角: 12px
- 阴影: 层级2
- 最大宽度: 100%
- 高度: 自适应

## 可访问性

- 文字对比度符合 WCAG AA 标准
- 支持键盘导航
- 语义化 HTML
- 适当的 ARIA 标签

## 浏览器兼容性

- Chrome/Edge (最新版本)
- Safari (最新版本)
- Firefox (最新版本)
- iOS Safari (iOS 12+)
- Android Chrome (最新版本)

## 性能优化

- CSS 使用变量减少重复
- 避免过度使用阴影和模糊效果
- 图片懒加载
- 平滑滚动

## 未来改进方向

1. 添加更多微交互
2. 优化暗色模式的对比度
3. 增加主题定制选项
4. 改进打印样式
5. 添加更多动画效果

---

*本设计系统遵循 Apple Human Interface Guidelines 的核心原则，同时针对中文内容和移动端场景进行了优化。*
