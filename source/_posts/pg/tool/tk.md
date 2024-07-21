---
title: 关于电脑工具的使用帮助
date: 2024-06-25 22:09:29
tags:
  - tool
  - cmake
  - tex
  - git
  - vs2010
  - hexo
categories:
  - TOOL
---

{% blockquote %}
一些工具的使用
{% endblockquote %}

<!-- more -->

## CMAKE

### 简单的 CMAKE

{% codeblock 简单的CMakeLists.txt示例 line_number:false %}
CMAKE_MINIMUM_REQUIRED(VERSION 3.0.0 FATAL_ERROR)

;; 如果需要使用Fortran来进行开发则
;; SET(CMAKE_Fortran_COMPILER ifort)
;; SET(PROJECT_NAME xx)
;; PROJECT(${PROJECT_NAME} Fortran)
SET(PROJECT_NAME xx)
PROJECT(${PROJECT_NAME})


;; 查找需要的模块
;; FIND_PACKAGE(Qt5 COMPONENTS Widgets REQUIRED)

;; 需要程序开启资源编译
SET(CMAKE_RC_COMPILER_INIT windres)
ENABLE_LANGUAGE(RC)

;; 如果需要编译 Qt 的 UI 文件
;; LIST(APPEND CMAKE_AUTOUIC_SEARCH_PATHS ${PROJECT_SOURCE_DIR}/UI)
ADD_EXECUTABLE(${PROJECT_NAME} 
	; Win32 ; 非控制台程序
	*.rc
	*.c[pp,c]
	*.f[90,or]
	*.ui
	...
)

;; 链接其它需要的库
;; TARGET_LINK_LIBRARIES(${TARGET_NAME} Qt5::Widgets Qt5::Core)
{% endcodeblock %}

## Hexo 的使用

### 环境的安装

{% codeblock lang:shell line_number:false %}
nvm install 20.10.0
nvm use 20.10.0
npm install hexo
{% endcodeblock %}

### 基础使用

{% codeblock 初始化博文 lang:shell line_number:false %}
npx hexo init <blog-name>
{% endcodeblock %}

{% codeblock 初始化博文 lang:shell line_number:false %}
npx hexo new --path path/to/<blog-name> # create in _post as root.
{% endcodeblock %}


{% codeblock 初始化页面 lang:shell line_number:false %}
npx hexo page categories # need `layout: "categories" type: "categories"`
npx hexo page about # need `layout: "about" type: "about"`
npx hexo page tag # need `layout: "tag" type: "tag"`
{% endcodeblock %}
