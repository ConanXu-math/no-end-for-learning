# no-end-for-learning

让知识停留在这。  
这是一个使用 LaTeX（XeLaTeX）整理的学习笔记项目，主要内容在 `note.tex`，编译后生成 `note.pdf`。

## 在线阅读

- GitHub Pages: <https://conanxu-math.github.io/no-end-for-learning/>
- PDF 直链: <https://conanxu-math.github.io/no-end-for-learning/note.pdf>

> 如果页面暂时打不开，请在仓库 `Settings -> Pages` 中确认已启用：
> - Source: `Deploy from a branch`
> - Branch: `main`
> - Folder: `/ (root)`

## 本地编译

建议使用 TeX Live 2023+，并使用 XeLaTeX 编译。

```bash
xelatex note.tex
xelatex note.tex
```

说明：
- 连续编译 2 次可以更新目录、交叉引用和超链接。
- 项目使用了中文相关宏包，建议保持 XeLaTeX 编译链。

## 项目结构

- `note.tex`：主文档源码
- `note.pdf`：编译生成的 PDF
- `fig/`：图片资源目录
- `index.html`：GitHub Pages 在线预览入口

## 常见问题

### 1) 图片找不到导致编译失败

请确认 `\includegraphics{...}` 中的路径与 `fig/` 目录下文件名一致（包括大小写与扩展名）。

### 2) `xelatex: unrecognized option '-pdf'`

这是编辑器（如 LaTeX Workshop）给 `xelatex` 传了不支持参数。  
请在编译工具配置中移除 `-pdf`，保留标准 `xelatex` 命令即可。

## License

当前仓库未声明开源许可证。如需开源，建议补充 `LICENSE` 文件。
