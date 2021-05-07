# README

## セットアップ

サイト作成

```shell
hugo new site hugo-omega
```
hu
レポジトリ初期化

```shell
cd hugo-omega
git init
echo '*~' >> .gitignore
echo '*.bak' >> .gitignore
echo '*.orig' >> .gitignore
echo '.env' >> .gitignore
echo 'public' >> .gitignore
echo 'resources' >> .gitignore
```

テーマ設定

```shell
git submodule add https://github.com/gethugothemes/omega-hugo.git themes/omega
```

サイト設定

```shell
cp -pr themes/hugo-omega/exampleSite/{content,config.toml,static} .
```

config.toml

```toml
baseURL = "https://buta7.github.io/hugo-omega/"
languageCode = "ja"
title = "Hugo Omega"
#publishDir = "docs"
#themesDir = "../.."
paginate = 6
```

> github pagesやnetlifyで使う場合はbaseURLのプロトコルはhttpsにすること

Githubレポジトリ作成後

```shell
cp somplace/Makefile
git remote add origin git@github.com:buta7/hugo-omega.git
git add .
git commit -m 'init'
git push -u origin main
```

## Github Actionsの利用

* .github/workflows/gh-pages.yamlを作成
  * ソースはmainブランチ
  * 出力はpublicフォルダの内容をgh-pagesブランチ
    * Github>Settings>Gighub Pages>Source>gh-pages branch

## 既存のレポジトリからクローンする場合

```shell
git clone git@github.com:buta7/hugo-omega.git
cd hugo-omega
git submodule update --init --recursive
```

## 使い方

### 投稿

新規投稿

```shell
hugo new posts/hello.md
content/posts/hello.md created
```

編集

```shell
vi content/posts/hello.md
```

## Link

* [Omega Hugo Theme \| Hugo Themes](https://themes.gohugo.io/omega-hugo-theme/)
