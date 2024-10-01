# cursor

## shortcut key

- `command + \`: open new window

## plugins

### vim

#### setting

### formatter

设置

```json
    "editor.formatOnSave": true, 
    "editor.formatOnPaste": true,
    "[html]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode" 
    },
```

### python

[ms-python.black-formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter)

### markDown

VSCode 支持安装多种扩展插件来增强 Markdown 的编辑体验。常见的插件包括：

- Markdown All in One：提供自动补全、实时预览、格式化等功能。
  
- Markdown Preview Enhanced：增加了更丰富的预览功能，支持图表、流程图、数学公式等。
- MarkdownLint：提供 Markdown 语法提示和修正建议，帮助你保持 Markdown 语法的整洁。

```json
    // markdownlint 配置
    "markdownlint.config": {
        "MD007": {
            "indent": 4
        }
    }
```

### React 开发插件

为了提升 React 开发体验，VSCode 提供了多种有用的插件。以下是一些推荐的 React 开发插件：

1. **ES7+ React/Redux/React-Native snippets**：
   提供 React、Redux 和 React Native 的代码片段，大大提高编码效率。

2. **ESLint**：
   JavaScript 和 JSX 的静态代码分析工具，帮助你发现并修复代码中的问题。

3. **Prettier - Code formatter**：
   自动格式化你的 JavaScript/React/JSX 代码，保持代码风格一致。

4. **Auto Import**：
   自动查找、解析并提供代码操作和代码完成。

5. **React Developer Tools**：
   React 调试工具的 VSCode 集成，方便在编辑器中调试 React 应用。

6. **vscode-styled-components**：
   为 styled-components 提供语法高亮和 IntelliSense。

7. **Debugger for Chrome**：
   在 VSCode 中直接调试运行在 Chrome 中的 JavaScript 代码。

8. **Jest**：
   如果你使用 Jest 进行测试，这个插件可以在 VSCode 中运行和调试测试。

### Theme

 • vscode-icons: 一个高度可定制的图标主题，支持文件和文件夹图标。
 • Material Icon Theme: 一个广泛使用的图标主题，支持 Material Design 风格的图标。
 • Ayu Icons: 提供简洁风格的文件和目录图标。
