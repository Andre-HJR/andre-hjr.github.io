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