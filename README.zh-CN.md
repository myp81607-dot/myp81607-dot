# 让日常业务更好处理的小工具

[English](README.md) · [简体中文](README.zh-CN.md)

我开发小型应用，帮助团队整理收到的工作、核对处理结果，并把异常交给人判断。

## 从你遇到的问题开始

| 你的团队需要…… | 对应项目 | 可以得到的结果 |
| --- | --- | --- |
| 整理咨询线索，避免重复创建联系人 | [线索到 CRM 自动化](https://github.com/myp81607-dot/lead-to-crm-automation) | 有负责人、可追踪的咨询和联系人更新 |
| 把 PDF 发票整理成经过核对的表格 | [发票提取与复核工作台](https://github.com/myp81607-dot/pdf-invoice-reviewer) | 附原文依据、经过复核的记录与 CSV |
| 找到客服政策，并检查资料依据 | [HarborDesk 客服知识工作台](https://github.com/myp81607-dot/support-assistant-with-citations) | 带版本的文档摘录，或可追踪的人工工单 |

**这些是使用合成业务数据的个人演示项目，并非付费客户案例。** 三个项目均可本地运行；各仓库提供中英文说明、真实截图、可复现验证、失败案例与参考来源。

## 线索到 CRM 自动化

**问题：** 咨询收到以后，联系人资料、分配结果和后续处理容易分散。

**流程：** 表单 → 校验 → 明确规则分配 → 联系人更新或人工复核。

实现区分“同一事件重复投递”和“同一联系人发来新咨询”。写入超时后，必须通过读回核对确认结果。Python、SQLite、英文复核界面与 n8n 工作流导出让每一步都可检查。

<a href="https://github.com/myp81607-dot/lead-to-crm-automation"><img src="assets/lead-to-crm.png" width="720" alt="真实本地运行：咨询队列、分配结果、联系人更新与通知草稿"></a>

**已验证范围：** 本地 CRM 与通知草稿。HubSpot 和真实 AI 尚未实连；n8n 导出完成结构检查，尚未在 n8n 中运行。

[运行项目，查看查重与失败恢复示例 →](https://github.com/myp81607-dot/lead-to-crm-automation#readme)

## 发票提取与复核工作台

**问题：** 从发票中读出文字，还不能证明字段与金额正确。

**流程：** 文本 PDF → 有原文依据的字段 → 十进制金额校验 → 人工复核 → CSV。

复核人员可以并排查看文档和可修改字段。缺失值、金额不符和重复单据需要处理后才能导出。Python、PDF 文字坐标、SQLite 与复核界面将提取过程连接到可使用的结果。

<a href="https://github.com/myp81607-dot/pdf-invoice-reviewer"><img src="assets/invoice-review.jpg" width="720" alt="真实本地运行：发票字段、PDF 原文与复核操作"></a>

**已验证范围：** 带文本的合成发票。陌生版式可能漏字段，需要人工补录；不支持扫描件，评测如实报告失败情况。

[查看提取、修改与导出流程 →](https://github.com/myp81607-dot/pdf-invoice-reviewer#readme)

## HarborDesk 客服知识工作台

**问题：** 客服人员需要找到相关政策，也需要在资料不足时有明确的下一步。

**流程：** 提问 → 词法检索 → 带版本的原文摘录 → 人工复核或本地工单。

工作台展示来源原文、带标签的政策冲突、文档版本和工单备注。FastAPI 与 SQLite 支撑完整流程；原仓库的 TF-IDF 学习基线和历史均被保留。

<a href="https://github.com/myp81607-dot/support-assistant-with-citations"><img src="assets/support-evidence.jpg" width="720" alt="真实本地运行：客服问题与带版本的文档依据"></a>

**已验证范围：** 检索、引文、文档更新与人工交接。默认模式不调用模型；可选本地模型适配器完成传输测试，真实生成尚未验证。

[核查资料依据与已知检索失败 →](https://github.com/myp81607-dot/support-assistant-with-citations#readme)

---

如果你有类似需求，**一份输入样例、期望输出和需要人工处理的例外情况**，就是有用的起点。
