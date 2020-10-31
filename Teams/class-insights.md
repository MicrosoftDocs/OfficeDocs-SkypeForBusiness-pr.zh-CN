---
title: Teams 教育版见解 IT 管理员指南
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
ms.openlocfilehash: b63ea1a1a09a55d9a51fb2a110c024960f23f6f4
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803520"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a>Teams 教育版见解 IT 管理员指南

借助 Microsoft Teams 教育版见解，教师和主管可以获取与数字化互动、评估工作量、分数以及沟通等方面相关的分析数据。 见解是由道德原则驱动的，它将教师和学生放在首位，可满足隐私标准，并确保你所在机构的持续合规性。

见解目前可在 Office 365 教育版 SKU A1、A3 和 A5 中使用。

> [!NOTE]
> 对于教师，可从此处了解如何使用见解：[Microsoft Teams 中的见解教师指南](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181)。

## <a name="use-insights"></a>使用见解

### <a name="user-types"></a>用户类型
- **学生** 由其许可证标识，并且  _无权_ 访问“见解”选项卡（即使他们是团队的所有者）。 
- **教师** 由教职员工许可证标识。 教师必须拥有教职员工许可证，并且是课堂团队所有者，以便添加和查看“见解”选项卡中显示的数据。 
- **主管** 也由教职员工许可证标识，但是此外，他们需要从 IT 全局管理员获取显式权限，才能在“见解”应用中查看报告。
- 来宾账户 _无权_ 访问见解。

### <a name="entry-points"></a>入口点
教师和主管具有不同的入口点，他们可以从中发现和使用见解。

**教师** 可以使用以下两个入口点：
- [选项卡](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181) - 在顶部导航菜单中添加的选项卡提供了有关他们拥有的每个课堂的见解。 见解将显示课堂团队中所有频道的活动数据，但只能将其作为选项卡添加到公共频道。 此选项卡反映了课堂团队中所有者以外的所有人（包括不是团队所有者的教师）的活动。
- [个人应用](https://support.microsoft.com/article/747fd8d9-00b0-43e6-bacc-a1bf030b1867) - 左侧 Teams 应用栏提供了所有活动课堂的概述。

**主管** 可以将见解用作[个人应用](https://support.microsoft.com/article/8738d1b1-4e1c-49bd-9e8d-b5292474c347)。

### <a name="manage-setup-policy"></a>管理设置策略
作为管理员，你可以使用[应用设置策略](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies)在教师和主管启动 Teams 时为其默认安装见解。
使用该策略，你可以自定义 Teams 以突出显示见解，并将其固定在应用栏中。

> [!TIP]
> 有关面向教育的 Teams 策略和策略包，请阅读[面向教育的 Teams 策略和策略包](https://docs.microsoft.com/microsoftteams/policy-packages-edu)。



## <a name="compliance"></a>合规性

见解具有业界领先的合规性承诺，并且在 Office 365 合规性框架内被归类为 C 层服务。

> [!NOTE]
> 访问 [Microsoft 信任中心](https://www.microsoft.com/trust-center)，以深入了解有关 Microsoft 如何保护您的数据。

## <a name="privacy"></a>隐私

通过见解收集和显示的信息确实符合 90 多个法规和行业标准，包括 GDPR 和关于学生和儿童安全的《家庭教育权利和隐私法案》(FERPA)，以及其他类似的面向隐私的法规。 对于 IT 管理员来说，了解对每个学生收集的信息仅可用于课堂环境非常重要，以便教师和主管确定学生的行为。 收集这些信息是为了进行有意义的学习活动，例如参加课堂会议、发布消息、回复同学的帖子、处理作业、编辑文件等。 例如，我们不显示有关私人聊天或 Teams 登录的信息。

我们的目标是帮助教师了解参与度、专注于学生的学习。 虽然这些课堂活动可以集中在学生级别的行动上，但是 Microsoft Teams 没有为这些行动分配正面或负面的价值，也没有基于标准对每个学生进行判断性识别。 见解中的信息通知教师，例如，某个学生在特定时期内未使用该工具，或者上周准时完成了所有作业。 教师有责任与学生以及学生的家人或监护人互动，以确定所发现的任何活动或非活动的根本原因。

## <a name="data-collection"></a>数据收集

- 当为租户启用教育版分析时，我们会收集见解的数据。 数据收集自 Teams 活动，目的为教学和学习提供可操作的见解。
- 来宾数据 _不是_ 为了见解而收集的。
- 默认情况下， **开启** 教育版分析。

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
> 有关在低带宽情况下使用 Teams 教育版的信息，请阅读[有关在低带宽情况下使用 Teams 教育版的帮助](edu-remote-low-bandwidth.md)。

## <a name="how-to-delete-your-data"></a>如何删除数据

教育服务存储学生和教师在课堂团队中进行的操作。 此数据被视为混合数据集，因此一旦从组织中删除学生或教育者用户帐户，就不会自动将其从服务中删除。

> [!NOTE]
> 删除数据会对见解分析课堂团队参与度的能力产生负面影响。

- 在 [https://edusupport.microsoft.com/support](https://edusupport.microsoft.com/support) 上打开支持票证。 支持票证必须清楚说明对 GDPR Delete DSR 操作的请求，并包含要删除的用户对象ID。 无法限制删除的数据集或时间范围。
- 存档后，支持票证将在队列中等待一周，以便达到合规性最低保留策略。 您有机会在这段时间内取消操作。
- 一周后，教育分析小组将采取措施，确保从服务中删除所有与用户 ID 相关的数据。 Microsoft 支持人员将监视 ICM 票证，并在不超过 28 天的删除过程完成后通知您。

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>使用学校数据同步（SDS）关闭见解

学校数据同步(SDS)有助于自动执行将学生信息系统 (SIS) 数据导入和同步到 Office 365 的过程。

使用见解不需要使用 SDS。 但是可以随时在“ **设置** ” > “ **管理教育版分析** ”下，选择在 SDS 管理中心中关闭切换来退出教育版分析。

:::image type="content" source="media/class-insights-on-off.png" alt-text="启用或禁用见解的开关。":::

默认情况下，启用教育版分析和见解。 选择退出 Google Analytics 时，我们会删除为“见解”标签收集的所有数据。重新启用 Google Analytics，我们从重新启用之时开始收集数据。

## <a name="additional-resources"></a>其他资源
- [见解教师指南](https://support.microsoft.com/office/27b56255-90c0-47aa-bac3-1c9f50157181)
