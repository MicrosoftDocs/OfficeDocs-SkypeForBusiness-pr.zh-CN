---
title: 自动升级|Skype Business 到 Teams 升级
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 从 Skype for Business 到 Teams 的自动升级概述
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
ms.openlocfilehash: cb3fef455e4031c61b6769e114d9cbd1d8bd3805
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120535"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>从 Skype for Business Online 自动升级到 Microsoft Teams

Microsoft 为 Teams 提供自动升级，以帮助小型企业在 2021 年 7 月 31 日停用服务之前从 Skype for Business Online 成功过渡。 自动升级可减少客户所需的技术任务数量，并可以更专注于组织准备、用户意识和 Teams 培训。

从 Skype for Business 成功升级到 Microsoft Teams 需要规划技术和用户准备情况。 当你准备好开始操作时，Microsoft 会提供一个[](upgrade-basic.md)升级操作计划，该计划包括核心推荐活动和关联的资源，用于成功实现从 Skype for Business 到 Teams 的迁移。

## <a name="notifications-for-scheduled-customers"></a>计划客户的通知

有资格自动升级到 Teams 的 Skype for Business Online 客户将在计划升级日期之前的 30 天内收到一系列升级通知。 这些通知将作为管理消息中心中的"更改计划"帖子、向全局管理员升级电子邮件以及向最终用户发送的应用内标志传递。

这些通知将传达自动升级的计划日期，将链接到升级资源和培训，以帮助推动 Teams 的采用和使用，并为客户提供在未在计划日期之前准备好升级时再推迟 30 天的选项。

## <a name="the-automated-upgrade-experience"></a>自动升级体验

自动升级在计划升级日期执行，该升级在通知电子邮件、消息中心和 Teams 管理门户中传递。 升级大约需要 15 分钟，在此期间最终用户仍可访问 Skype for Business Online 功能。 完成升级并且用户注销 Skype for Business Online 后，用户只能使用 Teams 进行消息传递、会议和通话。

## <a name="the-post-upgrade-experience"></a>升级后体验

自动升级完成后，"共存模式"设置为"仅 Teams"，并且 Microsoft 只能更改为其他共存模式。 在升级之前，管理员 [应查看"仅](teams-only-mode-considerations.md) Teams 模式"注意事项。 下表提供了仅 Teams 用户体验的概要概述。


|  |  |
|---------|---------|
|**聊天和通话**     | <UL><LI>所有通话和聊天在 Teams 中发起和接收<LI>用户可以与 (Skype for Business 用户) 聊天/通话<LI>用户无法与使用 Skype for Consumer 的用户通信<LI>如果用户尝试登录 Skype for Business，则重定向到 Teams      </UL>  |
|**会议**     |  <UL><LI>用户在 Teams 中安排所有新会议， (插件)     </UL>   |
|**迁移的数据**     |<UL><LI>Skype for Business 中的现有联系人（包括联合 (但没有通讯组列表) <LI>现有的 Skype for Business (和在线会议) 转换为 Teams 会议</UL>         |

## <a name="postponing-your-automated-upgrade"></a>推迟自动升级

从 Skype for Business Online 成功过渡到 Microsoft Teams 需要进行技术规划和用户准备，以确保组织已准备好利用 Teams 的扩展功能和性能。 但是，在规划升级时，你可能会发现组织目前尚未准备好升级到 Teams。

如果收到有关计划自动升级到 Teams 的通知，并且希望推迟到以后，全局管理员可能会登录到 Teams 管理门户并单击"推迟 *"* 按钮。 这样做会将自动升级日期推出 30 天。 延迟后刷新 Teams 管理门户时，会看到一条通知，其中包含新的自动升级日期。

## <a name="requests-to-downgrade-to-skype-for-business"></a>降级到 Skype for Business 的请求

我们允许从 Teams 一次降级到 SfBO，使租户能够进一步准备升级到 Teams。 已降级的租户将在降级日期后 60 天内重新参与自动升级。

## <a name="related-content"></a>相关内容

- [开始 Microsoft Teams 升级](upgrade-start-here.md)
- [Skype for Business Online 停用](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [仅 Teams 模式注意事项](teams-only-mode-considerations.md)