## **环境说明**

---

- python: 3.7.9

- 依赖的python包:

	| 包名 | 模块名 | 版本 |
	| :-- | :---- | :--  |
	| mkdocs | mkdocs | 1.2.3 |
	| mkdocs-material | material | 7.3.5 |
	| Markdown | markdown | 3.3.4 |
	| pymdown-extensions | pymdownx | 9.0 |

#### **依赖包安装**

```text
pip install mkdocs

pip install Markdown

pip install pymdown-extensions
```

#### **查看安装包版本**
```text
pip list
```

## **mkdocs-material部署**

---

### **安装**

```text
pip install mkdocs mkdocs-material
```

??? note "若下载慢，可更换安装源为豆瓣"
	```text
	pip install --trusted-host pypi.douban.com -i http://pypi.douban.com/simple/ mkdocs mkdocs-material
	```

### **初始化项目**

```text
mkdocs new my-project
```

会生成my-project目录，进入该目录里，可以看到默认放置了一些文件，包括mkdocs.yml，这是主配置文件

### **修改主题**

mkdocs.yml里添加:

```text
theme:
  name: material
  features:  # 开启Table功能
    - navigation.tabs
    - navigation.tabs.sticky
```



### **添加页面**

mkdocs.yml里添加:

```text
nav:
  - 介绍: index.md
  - 安装:
      - 本地环境搭建: install/local.md
      - 发布至GitHub Pages: install/github-pages.md
      - 发布至自己的HTTP Server: install/http-server.md
  - 语法:
      - 语法总览: syntax/main.md
      - 标题: syntax/headline.md
      - 段落: syntax/paragraph.md
```

### **添加扩展**

mkdocs.yml里添加:

```text
markdown_extensions:
  - admonition
  - codehilite:
      guess_lang: false
      linenums: false
  - toc:
      permalink: true
  - footnotes
  - meta
  - def_list
  - pymdownx.arithmatex
  - pymdownx.betterem:
      smart_enable: all
  - pymdownx.caret
  - pymdownx.critic
  - pymdownx.details
  - pymdownx.emoji:
      emoji_generator: !!python/name:pymdownx.emoji.to_png
  - pymdownx.inlinehilite
  - pymdownx.magiclink
  - pymdownx.mark
  - pymdownx.smartsymbols
  - pymdownx.superfences
  - pymdownx.tasklist
  - pymdownx.tilde
```
### **路由跳转**

- [可选][添加百度统计](./../../appendix/baidu_tongji/)

- [可选][改变页面配色](./../../appendix/color/)

- [推荐][支持中文搜索](./../../appendix/search/)

可以查看我的mkdocs.yml范例，详见[mkdocs.yml范例](./../../appendix/yml/)

### **mkdocs服务启动**

```text
# 在my-project目录里执行
mkdocs serve
```

通过浏览器打开 http://127.0.0.1:8000/ 查看效果
