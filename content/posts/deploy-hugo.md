+++
title = '安装部署Hugo静态站（MemE主题）'
date = 2025-05-01T12:00:53+08:00
draft = false
+++

## 1. 安装 Hugo

```bash
sudo apt install hugo
```

## 2. 创建新项目

```bash
hugo new site blog
```

## 3. 安装 MemE 主题

```bash
cd blog
git init
git submodule add --depth 1 https://github.com/reuixiy/hugo-theme-meme.git themes/meme
```

使用 MemE 主题的配置文件

```bash
rm hugo.toml
cp themes/meme/config-examples/zh-cn/config.toml hugo.toml
```

## 4. 启动站点并测试

开发时执行如下命令。

```bash
hugo server --bind=0.0.0.0
```

部署时执行如下命令。

```bash
hugo build --environment production --theme meme --cleanDestinationDir --baseURL https://xxx.xxx/
```

## 5. 发布新博文

```bash
hugo new post/hugo安装和部署.md
```
