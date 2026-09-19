# Python 自动化与 API 集成

[English](README.md) · [简体中文](README.zh-CN.md)

我用 Python 为团队开发线索录入、发票处理和客服工具，也处理实际使用中需要的输入检查、复核界面和异常恢复。

下面三个项目均为使用合成业务数据的个人演示，并非付费客户案例。各项目可本地运行，附中英文说明、测试结果和已知限制。

## [线索到 CRM 自动化](https://github.com/myp81607-dot/lead-to-crm-automation)

适合仍在手工把网站咨询录入联系人列表的团队。提交表单后，可以查看咨询的负责人、联系人更新和通知草稿。重复投递会被识别，缺失信息和需要核实写入结果的记录会留在复核队列中。补完旧咨询不会覆盖较新的联系人资料。

[当前复核流程：20 秒](https://github.com/myp81607-dot/lead-to-crm-automation/blob/main/docs/review-update.webm) · [完整流程：58 秒](https://github.com/myp81607-dot/lead-to-crm-automation/blob/main/docs/demo.webm) · [截图](assets/lead-to-crm.png)。录像通过 GitHub 的 **View raw** 下载播放。

仓库中的工作流已在 n8n 2.39.8 中实际运行，连接本地 Python 服务与 SQLite CRM，包括定时重试。HubSpot 与真实 AI 尚未实连验证，通知保存为草稿。

## [PDF 发票复核工具](https://github.com/myp81607-dot/pdf-invoice-reviewer)

适合需要把供应商发票整理成表格的运营人员。上传文本 PDF，对照原文检查提取字段，修正或拒绝有问题的记录，再将已确认记录导出为 CSV。切换发票时会保留独立的字段与备注草稿；旧页签不能静默覆盖较新的已保存记录。

[60 秒操作步骤演示](https://github.com/myp81607-dot/pdf-invoice-reviewer/blob/main/docs/demo.mp4) · [复核界面](assets/invoice-review.jpg) · [试用样例发票](https://github.com/myp81607-dot/pdf-invoice-reviewer#readme)

已使用合成的英文文本 PDF 测试。陌生版式可能需要人工补录；不支持扫描件。仓库同时记录提取失败和修复后的测试结果。

## [带来源的客服知识工作台](https://github.com/myp81607-dot/support-assistant-with-citations)

适合需要先查产品政策、再回复客户的客服人员。可以搜索带版本的文档、打开支持原文，并在资料不足或冲突时留下人工工单。可选回答模式会生成简短草稿，需要操作者核对并批准后才能复制。自己的资料可通过一份简单的 JSON 文件导入。

[35 秒检索与交接演示](https://github.com/myp81607-dot/support-assistant-with-citations/blob/main/docs/demo.webm) · [资料依据界面](assets/support-evidence.jpg) · [问题示例](https://github.com/myp81607-dot/support-assistant-with-citations#readme)

检索、文档更新、人工交接与批准规则已经过测试。默认模式不调用模型；DeepSeek 适配器和草稿流程使用模拟响应验证，真实模型的回答质量尚未验证。

## 开始一个类似项目

| 可以讨论的工作范围 | 开始前准备的材料 |
| --- | --- |
| 表单到 CRM 的集成，或现有流程修复 | 样例输入、目标字段和获授权的测试环境 |
| 指定供应商 PDF 的复核与 CSV 导出 | 样例文档、必需字段和校验规则 |
| 为客服知识库补充来源与人工交接 | 可使用的资料、问题样例和转人工条件 |
