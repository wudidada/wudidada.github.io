---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

## 界面

[chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)

## 部署流程

1. 私有笔记仓库中进行记录，使用obsidian和logseq管理及浏览内容、typora编辑长文。
2. 笔记仓库commit后触发[github actions](https://github.com/features/actions)，根据`tag`等信息判断文本是否发表，若是则将待发表markdown文件转换为通用格式，并提交到[网站仓库](https://github.com/wudidada/wudidada.github.io)。
3. 提交触发网站仓库的[github actions](https://github.com/features/actions)，生成并部署更新后的内容到[github pages](https://pages.github.com/)。