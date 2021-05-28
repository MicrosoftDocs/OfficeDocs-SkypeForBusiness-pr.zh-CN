---
title: '适用于 Teams 管理员的"患者"应用 '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解适用于 Teams 管理员的"患者"应用
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2302f117564e1dd00a6f238ca23a8e36c63ae554
ms.sourcegitcommit: e6e6a2a85ff376f97a3af3548e13d1273fa84a52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697839"
---
# <a name="patients-app-overview"></a>患者应用概述

> [!NOTE]
> 从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。 患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。 用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。
>
>借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。 查看列表的"患者"模板以开始使用。 若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。

"患者"应用程序是一款可用于所有 Teams 用户的 Microsoft Teams 应用商店应用。 通过该应用，由患者健康团队（如医师、医师、社保等）组成，他们可针对各种方案（从圆形和内联团队会议到常规患者监视）创建和审阅患者列表。

该应用有两种模式：

- 通过 FHIR 连接到 EMR 的 EMR 连接模式。 连接 EMR 模式的应用将保留在专用预览中，感兴趣的客户或管理员可能会通过退出 microsoft 电子邮件（包含其 Microsoft 365 组织相关信息） [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 来请求访问该应用。
- 使运行状况团队可以手动添加/引入患者信息的手动模式。 该应用程序可在 Teams 应用商店中供最终用户以专用预览版下载。 在 Teams 中，应用只能使用 [应用设置策略](../../teams-app-setup-policies.md) 特定分区的用户。 若要获取该应用，租户需成为技术采用计划 （TAP） 的一部分。 请在联系你 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 电子邮件，以开始请求访问的流程。

## <a name="usage-example"></a>用法示例

在每周值班期间，医师在医疗站集合，与患者讨论进度的最新更新。  他们着重强调关键关键指标（不一定是医疗指标，或者明确记录患者医疗记录），并确保患者按照患者患者护理，选择正确的方法。 为了四处环绕这些患者，收费中心在添加了所有医师的团队中设置患者应用并将患者添加到患者列表。 在检查期间，患者的患者和其他患者护理人员会通过自己的移动设备访问 Microsoft Teams 和患者应用，并更新其设备上相关的患者信息，这样运行状况团队中的其他人就可以查看这些更新和笔记，保持同步。一天两次，在轮班开始和结束时，他们还会举行多方团队会议来检查患者列表，使用"患者"应用自行为，并共享有关使用大型显示屏上的"患者"应用的每个患者的信息。 通常情况下，某些医师可能还远程拨入这些 Teams 会议，他们仍然参与讨论。

## <a name="configure-patients-app"></a>配置"患者"应用

请参阅[管理应用中的应用设置Microsoft Teams](../../teams-app-setup-policies.md)为组织启用患者应用。

有关你的最终用户如何访问这些应用程序并安装到他们拥有或管理的团队的信息，请参阅 [Microsoft Teams 患者信息](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)。

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>常见问题 (FAQ)

**"患者"应用数据存储在什么位置？**

最终用户在"患者"应用中输入的所有数据，包括列/字段架构，输入到列表和列表项（即患者）的实际数据，均存储在安全合规的 Exchange Online 基础结构中。 所有数据存储在与团队关联的组邮箱中。 此体系结构使 Patients 应用可以轻松满足数据驻留、政府云支持（即将将来提供）和其他合规性/信息保护功能（如电子数据展示支持）。 "患者"应用在团队范围内运行。 需要按团队安装应用程序实例。

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**我可以从哪里获取"患者"应用？**

如果管理员为组织启用了"患者"应用，任何最终用户都可以转到 Teams 应用商店，将"患者"应用添加到他们加入的团队。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](../../teams-app-setup-policies.md)。

**能否在团队中有多个"患者"应用实例，因为这两个组都进行操作？**

目前，你只能为给定团队安装一个"患者"应用实例，只能在常规频道中安装。 但在应用内，可创建多个列表以解决多频道或隔离/分隔方案。 默认情况下，团队的所有成员将有权访问常规频道中的"患者"选项卡。 

**我能否从"患者"应用导出所有数据？**
目前还不会，但即将推出此功能。 

**由于此应用容纳 PREVENT，因此是否有审核以防止未经授权的访问或遵守法规？**

是的，有。 安全与合规中心会审核 Microsoft Teams 用户对"患者"应用执行的每一个 UI 操作。 在"患者" [审核日志中介绍了详细信息](patients-audit.md)。

