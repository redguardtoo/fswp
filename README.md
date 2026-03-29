# FSWP - 页面英文模糊搜索与拼音首字母搜索

一个轻量级的 JavaScript 工具库，支持在当前网页内同时进行英文模糊搜索和拼音首字母搜索，帮助用户快速定位页面中的文本内容。

---

## 功能特点

- **英文模糊搜索**：支持大小写不敏感的英文单词模糊匹配
- **拼音首字母搜索**：支持汉字拼音首字母搜索（例如输入 `hw` 可匹配“花纹”或“华为”）
- **快速跳转**：点击搜索结果自动滚动到匹配位置并高亮显示
- **优雅界面**：固定在页面右上角的搜索面板，带关闭按钮
- **轻量级**：原生 JavaScript 实现，无需依赖任何第三方库

---

## 快速开始

### 1. 引入脚本

在 HTML 文件的 `<head>` 中引入 `fswp.js`：

```html
<head>
    <script src="js/fswp.js" defer></script>
</head>
```

### 2. 添加触发按钮

在页面任意位置添加按钮，点击即可切换搜索界面：

```html
<button onclick="fswpToggleSearchInterface()">🔍 页面搜索</button>
```

### 3. 开始使用

点击按钮后，页面右上角会出现搜索面板。输入关键词即可实时搜索页面内容：

- 支持英文单词模糊搜索（如输入 `java` 可匹配 “JavaScript”）
- 支持拼音首字母搜索（如输入 `hw` 可匹配 “花纹” 或 “华为”）

点击搜索结果列表中的任意项，页面将自动滚动到匹配位置并高亮显示。

---

## API 文档

### `fswpToggleSearchInterface(parentElement)`

切换搜索界面的显示/隐藏状态。

**参数：**

- `parentElement`（可选，默认 `document.body`）：搜索界面挂载的父元素

**示例：**

```js
// 默认挂载到 body
fswpToggleSearchInterface();

// 挂载到指定容器
const container = document.getElementById('sidebar');
fswpToggleSearchInterface(container);
```

---

### `fswpCreateSearchInterface(parentElement)`

创建并显示搜索界面。

**参数：**

- `parentElement`（可选，默认 `document.body`）

---

### `fswpRemoveSearchInterface()`

移除搜索界面并清理事件监听。

---

## 使用示例

```html
<!DOCTYPE html>
<html>
<head>
    <title>搜索示例</title>
    <script src="js/fswp.js" defer></script>
</head>
<body>
    <button onclick="fswpToggleSearchInterface()">🔍 页面搜索</button>

    <div>
        <p>JavaScript 是一门强大的编程语言</p>
        <p>花纹设计非常精美</p>
        <p>华为是一家科技公司</p>
        <p>拼音首字母搜索测试（PinYin Search）</p>
    </div>
</body>
</html>
```

---

## 搜索规则说明

### 英文模糊搜索

- 输入 `java` 可以匹配 “JavaScript”
- 输入 `script` 可以匹配 “JavaScript”
- 输入 `regex` 可以匹配 “Regular Expression”

### 拼音首字母搜索

- 输入 `hw` 可以匹配 “花纹”（hua wen）或 “华为”（hua wei）
- 输入 `qd` 可以匹配 “前端”（qian duan）
- 输入 `py` 可以匹配 “拼音”（pin yin）

### 输入限制

- 搜索框仅接受英文字母（A–Z，a–z）
- 至少输入 2 个字符才会触发搜索

---

## 技术细节

- **文本节点遍历**：自动跳过隐藏元素和空文本节点
- **拼音映射库**：内置完整的汉字拼音首字母映射表（覆盖 GB2312 汉字集）
- **模糊匹配算法**：基于正则表达式的动态模式匹配
- **高亮效果**：匹配项点击后临时高亮显示并平滑滚动

---

## 浏览器兼容性

支持所有现代浏览器（Chrome、Firefox、Safari、Edge 等），要求 JavaScript ES6+ 环境。

---

## 开源协议

MIT License

```
Copyright (c) 2024

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
