---
title: 在 Microsoft 团队预览中的信息障碍
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: 了解信息障碍及其如何影响团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71c547ac13f63c9357dfb6e8a0cbe34d748646d3
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827785"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a>在 Microsoft 团队预览中的信息障碍

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

信息的障碍是管理员可以配置为阻止个人或组进行相互进行通信的策略。 如果，例如，一个部门处理不应与其他部门共享信息或一组需要被阻止与任何外部的联系人进行通信，这很有用。

> [!NOTE]
> - 不能跨租户创建信息障碍组。
> - 版本 1 不支持使用自动程序添加用户。

信息障碍策略也阻止查找和发现。 这意味着，如果您尝试与某人不应与通信您进行通信，您将找不到该用户在人员选取器。

## <a name="background"></a>背景

信息的障碍的主驱动程序来自金融服务行业。 金融行业监管机构 ([FINRA]( http://www.finra.org/)) 介绍信息障碍和利益冲突成员公司内，并提供了有关如何管理 （FINRA 2241，[偿还研究法规通知 15 31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)此类冲突指南。  

## <a name="when-should-i-use-information-barriers"></a>何时应使用信息障碍？

您可能需要在以下情况下使用信息障碍：

- 团队必须防止通信或与某个特定共享数据其他团队。
- 团队必须不进行通信，或与团队之外的任何人共享数据。

信息障碍策略评估服务确定通信是否符合信息限制策略。 

## <a name="managing-information-barrier-policies"></a>管理信息限制策略

使用安全 & 合规性中心 (SCC) PowerShell cmdlet 管理信息限制策略。 有关使用这些 cmdlet，[此处注册](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u)的详细信息。

> [!IMPORTANT]
> 在设置或定义策略，**您必须启用的 Microsoft 团队中的作用域的目录搜索**。 等待至少 24 小时后启用作用域的目录搜索之前设置或定义信息障碍的策略。

## <a name="information-barriers-administrator-role"></a>信息的障碍管理员角色

信息的障碍管理员角色负责管理信息限制策略。 有关此角色以及参与预览，[此处注册](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u)的详细信息。

## <a name="when-are-information-barrier-policies-checked"></a>何时检查信息障碍策略？

以下团队事件发生时，会检查信息障碍策略：

- 必须根据其他小组成员的信息限制策略来计算**成员添加到团队**-每当将用户添加到团队，用户的策略。 成功添加用户后，用户可以执行无进一步的检查团队中的所有功能。 如果用户的策略阻止它们的添加到团队，用户不将会在搜索中显示。
- **请求新的聊天**-每次新的聊天请求两个或多个用户之间聊天进行评估，以确保其不违反信息障碍的任何策略。 如果对话违反信息障碍策略，然后对话未启动，并出现错误消息。
- **邀请用户加入会议**的邀请用户加入会议、 计算用户的策略所依据的策略的其他小组成员，以及如果没有冲突，用户将不允许加入会议，并将看到一条错误消息时。
- **两个或多个用户之间共享屏幕**的任何时间屏幕共享两个或多个用户之间，必须计算的屏幕共享以确保其不违反信息限制策略的其他用户。 如果违反了信息障碍策略，将不允许的屏幕共享，并显示一条错误消息。
- **团队中的用户发出电话呼叫 (VOIP)** -语音呼叫由另一个用户或用户组，呼叫用户启动的任何时间计算以确保其不违反 oher 小组成员的信息限制策略。 如果没有任何冲突，语音呼叫被阻止。

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>如果更改策略到现有聊天线程的怎么办？

当信息障碍策略管理对该策略进行更改或策略更改用于启动生效由于更改用户的作业或类似的原因，信息障碍策略评估服务自动搜索确保的成员团队成员没有违反的任何策略。 

如果没有现有聊天或其他用户之间的通信和新的策略设置或更改现有策略，该服务将评估现有的通信，以确保，它们不"感染保留"（不再允许）： 

- **1:1 聊天**-如果 （如果阻止通信的策略应用于一个或两个用户） 不再允许两个用户之间的通信、 进一步通信将被阻止和聊天会话将变为只读。
- **群聊**-如果 （例如，如果用户更改作业） 不再允许向组从一个用户的通信、 可能从群聊中删除违反策略的其他用户以及用户和组与进一步通信不会允许。 用户仍可以看到旧对话 （这将为只读），但不是能以查看或参与与组的任何新的对话。 如果阻止了通信的新的或更改策略应用于多个用户，可能会影响该策略的用户删除从群聊。 他们仍可以看到旧的对话。 
- **团队**-已从组中删除任何用户删除来自团队，并将不能查看或参与现有或新的对话。

## <a name="required-licenses-and-permissions"></a>必需的许可证和权限

目前，信息障碍功能处于公共预览。 这些功能通常可用时，它们将包含在订阅，例如：

- Microsoft 365 E5
- Office 365 E5
- Office 365 高级合规性
- Microsoft 365 E5 合规性

有关详细信息，包括计划和定价，请参阅[法规遵从性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1)。
