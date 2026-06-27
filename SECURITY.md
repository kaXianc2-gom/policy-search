# 安全策略 / Security Policy

## 支持的版本

| 版本 | 支持状态 |
|------|----------|
| 最新版 | ✅ 活跃支持 |
| 旧版本 | ❌ 不支持 |

## 报告漏洞

如果你发现安全漏洞，**请勿公开提交 Issue**。

请通过 GitHub Security Advisory 私下报告：
1. 进入 [Security](https://github.com/kaXianc2-gom/policy-search/security) 标签
2. 点击 "Report a vulnerability"
3. 描述漏洞详情和复现步骤

我会在 48 小时内确认并给出处理方案。

## 隐私承诺

本项目所有数据处理均在浏览器本地完成：
- 不上传任何数据到服务器
- 不使用第三方遥测/分析
- CDN 依赖仅用于加载开源库（SheetJS / ECharts），不收集用户信息

## 依赖安全

| 依赖 | 用途 | 加载方式 |
|------|------|----------|
| SheetJS | Excel 解析 | CDN / 内联 |
| ECharts | 图表渲染 | CDN / 内联 |

如发现依赖库漏洞，请同样以上述方式报告。
