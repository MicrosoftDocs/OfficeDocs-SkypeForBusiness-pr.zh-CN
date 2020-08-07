---
title: 面向 IT 管理员的 Microsoft Teams 教育版见解
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版见解 IT 管理员指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75d9396bf5f537f965493bb0db317a1286b2f950
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572367"
---
# <a name="insights-in-teams-for-education-for-it-admins"></a>面向 IT 管理员的 Microsoft Teams 教育版见解

借助 Microsoft Teams 教育版见解，教师和主管可以获取与数字化互动、评估工作量、分数以及沟通等方面相关的分析数据。

见解目前可在 Office 365 教育版 SKUs A1、A3 和 A5 中使用。

> [!NOTE]
> 教师，[点击此处](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)了解如何使用见解。

## <a name="permissions"></a>权限

- 学生由其许可证标识，并且 **无权访问“见解”选项卡** （即使他们是团队的所有者）。
- 教师由教职员工许可证定义。 教师必须拥有教职员工许可证，并成为课堂团队所有者，才能添加和查看“见解”选项卡。该选项卡反映来自课堂团队中的所有人（非团队所有者）的活动（包括不是团队所有者的教师）。
- 主管的基本定义由教职员工许可证定义。 IT 全局管理员由其角色标识。 主管必须拥有教职员工许可证，并且从 IT 全局管理员获取显式权限，才能在“见解”应用中查看报告。

我们提供两种形式的见解：
- 选项卡 - 教师可以通过导航到 Microsoft Teams 应用栏中的“应用”并搜索“见解”，将“见解”添加到课堂团队的公共频道中。
- 个人应用 - 主管可将“见解”应用添加为个人应用（出现在 Microsoft Teams 菜单上），方法是在 Microsoft Teams 应用栏中导航到“应用”并搜索“见解”。

## <a name="compliance"></a>合规性

见解具有业界领先的合规性承诺，并且在 Office 365 合规性框架内被归类为 C 层服务。

> [!NOTE]
> 访问 [Microsoft 信任中心](https://www.microsoft.com/trust-center)，以深入了解有关 Microsoft 如何保护您的数据。

## <a name="privacy"></a>隐私

通过见解收集和显示的信息确实符合 90 多个法规和行业标准，包括 GDPR 和关于学生和儿童安全的《家庭教育权利和隐私法案》 (FERPA)，以及其他类似的面向隐私的法规。 对于 IT 管理员和主管来说，了解每个学生收集的信息仅可用于课堂环境非常重要，以便教师确定课堂行为。 收集这些信息是为了进行有意义的学习活动，例如参加课堂会议、发布消息、回复同学的帖子、处理作业、编辑文件等。 例如，我们不显示有关私人聊天或 Teams 登录的信息。

我们的目标是帮助教师了解参与度、专注于学生的学习。 虽然这些课堂活动可以集中在学生级别的行动上，但是 Microsoft Teams 没有为这些行动分配正面或负面的价值，也没有基于标准对每个学生进行判断性识别。 见解中的信息通知教师，例如，某个学生在特定时期内未使用该工具，或者上周准时完成了所有作业。 教师有责任与学生以及学生的家人或监护人互动，以确定所发现的任何活动或非活动的根本原因。

## <a name="data-collection"></a>数据收集

当为租户启用教育版分析时，我们会收集见解的数据。 数据收集自 Teams 活动，目的为教学和学习提供可操作的见解。

默认情况下，**开启**教育版分析。

目前，此数据从课堂团队的学生和教师活动的以下区域提取：

|Teams 组件  |收集的数据  |
|-----------------|------------------------|------------------------|
|作业 |打开、上交作业并评分。 |
|频道参与 |访问频道、创建帖子、回复和赞帖子（不包括聊天内容）。 |
|文件 |上传、下载、访问、修改、批注和共享文件（不包括文件内容）。 |
|会议 |出席（不包括会议内容）。 |

## <a name="data-location"></a>数据位置

位于欧洲的租户见解数据存储在欧洲服务器上。 位于美国的租户数据存储在美国服务器上。 如果您使用见解，并且 Office 365 租户位于欧洲或美国以外地区，则您的数据将存储在相应的地理区域。

## <a name="performance-and-reliability"></a>性能和可靠性

见解旨在以最佳性能和可靠性处理从 Microsoft Teams 活动收集的大量数据。

无论 Microsoft Teams 中的“见解”选项卡如何安装，均会在单独服务器上进行数据收集过程。 “见解”选项卡或个人应用不影响使用 Microsoft Teams 其他功能的教师和学生应用程序的性能或网络带宽。

> [!TIP]
> 阅读[此处](edu-remote-low-bandwidth.md)，了解有关在带宽不足时使用 Teams 教育版的信息。

## <a name="how-to-delete-your-data"></a>如何删除数据

教育服务存储学生和教师在课堂团队中进行的操作。 此数据被视为混合数据集，因此一旦从组织中删除学生或教育者用户帐户，就不会自动将其从服务中删除。

> [!NOTE]
> 删除数据会对见解分析课堂团队参与度的能力产生负面影响。

- [点击这里](https://edusupport.microsoft.com/support)打开支持票证。 支持票证必须清楚说明对 GDPR Delete DSR 操作的请求，并包含要删除的用户对象ID。 无法限制删除的数据集或时间范围。
- 存档后，支持票证将在队列中等待一周，以便达到合规性最低保留策略。 您有机会在这段时间内取消操作。
- 一周后，教育分析小组将采取措施，确保从服务中删除所有与用户 ID 相关的数据。 Microsoft 支持人员将监视 ICM 票证，并在不超过 28 天的删除过程完成后通知您。

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>使用学校数据同步（SDS）关闭见解

学校数据同步(SDS)有助于自动执行将学生信息系统 (SIS) 数据导入和同步到 Office 365 的过程。

使用见解不需要使用 SDS。 但是可以随时在“**设置**” > “**管理教育版分析**”下，选择在 SDS 管理中心中关闭切换来退出教育版分析。

:::image type="content" source="media/class-insights-on-off.png" alt-text="启用或禁用见解的开关。":::

默认情况下，启用教育版分析和见解。 选择退出 Google Analytics 时，我们会删除为“见解”标签收集的所有数据。重新启用 Google Analytics，我们从重新启用之时开始收集数据。

了解详细信息：[适用于教师的见解](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)
