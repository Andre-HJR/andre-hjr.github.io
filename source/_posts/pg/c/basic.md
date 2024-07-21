---
title: 基础C语言
date: 2024-06-25 20:52:07
lang: zh-CN
tags:
  - PG
  - C-Like
categories:
  - [PGER,LANG]
  - [PGER,BASIC]
---

{% blockquote %}
基础C语言
{% endblockquote %}

<!-- more -->

{% codeblock lang:c mark:3,8-10 %}
enum { FMTBUFFERSIZE = 1 << 8 };

WCHAR GLOBAL[FMTBUFFERSIZE];

INT wmain(CONST INT ARGC, CONST WCHAR** ARGV, CONST WCHAR** ENVP)
{
	INT RET_STATUS = 0;
	WCHAR M_HelloWorld[] = L"Hello World!\n";
	ZeroMemory(GLOBAL, sizeof(WCHAR) * FMTBUFFERSIZE);
	swprintf_s(GLOBAL, (size_t)FMTBUFFERSIZE, L"%ls", L"%%ls");
	fwprintf_s(stdout, GLOBAL, M_HelloWorld);
	return RET_STATUS;
}
{% endcodeblock %}

## 变量和常量


## 条件判断

## 循环

## 结构体

## IO的部分

## 奇技淫巧

### 宏编程的艺术

## 谈一下 Python

### 写个插件

> 以 Python2.7.18 和 vc10 为例

## 谈一下 C++


## 谈一下 Fortran

