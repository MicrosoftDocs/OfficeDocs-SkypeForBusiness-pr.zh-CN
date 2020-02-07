---
title: 自动升级 |将 Skype 企业升级到团队
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 从 Skype for Business 自动升级到团队的概述
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ed959f74be1074ab8ed60b3fe54f06384b7990a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836164"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>从 Skype for Business Online 到 Microsoft 团队的自动升级

Microsoft 向团队提供自动升级，以帮助小型企业在2021年7月31日之前通过 Skype for Business Online 成功地进行切换。 自动升级减少了客户所需的技术任务的数量，并可更好地关注组织的准备、用户意识和团队培训。

从 Skype for Business 成功升级到 Microsoft 团队需要针对技术和用户准备情况进行规划。 准备好开始使用时，Microsoft 会提供一个[升级操作计划](upgrade-basic.md)，其中介绍了实施成功从 Skype for business 迁移到团队的核心推荐活动和相关资源。

## <a name="notifications-for-scheduled-customers"></a>计划客户的通知

有资格自动升级到团队的 Skype for Business Online 客户将在其计划升级日期之前的30天内收到一系列升级通知。 这些通知将作为 "管理员" 消息中心中的 "更改" 发布的*计划*交付，将电子邮件升级到全局管理员，并将应用内的标记升级到最终用户。

这些通知将传达自动升级的计划日期，将链接到升级资源和培训，以帮助推动团队的采纳和使用，并让客户选择将其自动升级推迟到最新的30天内活动他们的计划日期尚未准备好升级。

## <a name="the-automated-upgrade-experience"></a>自动升级体验

自动升级将按计划的升级日期执行，该日期在通知电子邮件、消息中心以及团队管理门户中进行通信。 升级将大约需要15分钟，最终用户仍将有权访问 Skype for Business Online 功能。 升级完成后，用户注销 Skype for Business Online 后，用户将只能使用团队进行消息传递、会议和通话。

## <a name="the-post-upgrade-experience"></a>升级后体验

自动升级完成后，"**共存" 模式**将设置为 "仅限团队"，并且只能通过 Microsoft 将其更改为其他共存模式。 在升级之前，管理员应[仅查看团队的模式注意事项](teams-only-mode-considerations.md)。 下表提供了仅限团队用户体验的高级别概述。


|  |  |
|---------|---------|
|**聊天和通话**     | <UL><LI>在团队中启动和接收所有通话和聊天<LI>用户可以与任何 Skype for Business 用户互操作（聊天/通话）<LI>用户无法与使用 Skype for 消费者的用户进行通信<LI>如果用户尝试登录到 Skype for Business，他们将被重定向到团队      </UL>  |
|**会议**     |  <UL><LI>用户计划团队中的所有新会议（已替换插件）    </UL>   |
|**迁移的数据**     |<UL><LI>Skype for Business 中的现有联系人，包括联盟（但不是通讯组列表）<LI>现有 Skype for Business 会议（本地和 online）转换为团队会议</UL>         |

## <a name="postponing-your-automated-upgrade"></a>推迟自动升级

从 Skype for Business Online 到 Microsoft 团队的成功转换需要技术规划和用户准备工作，以确保你的组织做好充分利用扩展功能和团队性能的准备。 但是，当你规划升级时，你可能会发现你的组织尚未准备好升级到团队。

如果收到有关计划自动升级到团队并希望推迟到更晚日期的通知，则 Office 365 全局管理员可能会登录到团队管理门户，然后单击 "*推迟*" 按钮。 这样做会将自动升级日期推送30天。 在延迟后刷新团队管理门户时，你将看到一个通知，其中包含你的新自动升级日期。

## <a name="requests-to-downgrade-to-skype-for-business"></a>降级到 Skype for business 的请求

我们允许租户进一步对 SfBO 进行一次降级，以允许租户进一步准备他们升级到团队。 已降级的租户将在其降级日期重新参与自动升级60天。

## <a name="related-content"></a>相关内容

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [Skype for Business Online 停用](skype-for-business-online-retirement.md)
- [CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [仅 Teams 模式注意事项](teams-only-mode-considerations.md)

