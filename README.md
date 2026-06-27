# PolicySearch — 政策文件搜索

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-2.1.0-brightgreen)](https://github.com/kaXianc2-gom/policy-search/releases)
[![Pages](https://img.shields.io/badge/demo-online-0078D4)](https://kaXianc2-gom.github.io/policy-search/)

> 输入关键词，从 gov.cn 实时抓取政策全文，本地缓存供检索。同义词自动扩展。

单文件 HTML，双击即用。不是 AI 搜索，是本地 TF 词频匹配 + 政府官网直抓 + 粘贴文本导入。

## 怎么用

1. 下载 index.html，双击打开
2. 点"从政策目录抓取"，选一篇（如 2025 年政府工作报告）
3. 等待抓取完成（3 路 CORS 代理竞速，最快 2-3 秒）
4. 输入关键词搜索，同义词自动扩展
5. 点击结果查看全文高亮片段

抓取失败时，点目录里的原文链接 → 新标签打开 → Ctrl+A 全选 → 回到工具点"粘贴文本" → 导入。

## 工作原理

**抓取**：3 路 CORS 代理并行请求 gov.cn，最快响应胜出。HTML → 纯文本提取（优先匹配 article/main 等正文容器）。

**缓存**：抓过的文档存 localStorage，下次打开直接搜，离线可用。缓存满时自动清理旧文档。

**搜索**：TF 词频评分 + 20 组同义词扩展（搜"乡村振兴"自动扩展为"三农工作""千万工程"等）。

**目录**：内置 20 篇常用政策 URL，也可以自己输入 gov.cn 链接抓取。

## 🌐 在线体验

无需下载，直接使用：**[🔗 在线 Demo](https://kaXianc2-gom.github.io/policy-search/)**

## 🔐 隐私声明

- **搜索完全本地**：TF 词频匹配在浏览器中完成，关键词不上传
- **缓存本地存储**：抓取的文档存 localStorage，离线可用
- **CORS 代理仅转发**：抓取 gov.cn 时使用公共 CORS 代理，代理不记录请求内容（仅做 HTTP 转发）

> ⚠️ **免责声明**：抓取内容来自 gov.cn 等政府网站。搜索结果仅供参考，以原始政策文件为准。

## 技术

纯 HTML + JS，无外部依赖，单文件约 41KB。文档缓存上限约 5MB（localStorage 限制）。

MIT License
