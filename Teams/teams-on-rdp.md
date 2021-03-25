---
title: 将 Teams 与远程桌面服务一同使用
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何将 Microsoft Teams 与远程桌面服务一同使用。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119091"
---
# <a name="teams-in-remote-desktop-services"></a>远程桌面服务中的 Teams

本文介绍在 RDS 环境远程桌面服务 (Microsoft Teams) 限制。

## <a name="what-is-rds"></a>什么是 RDS？

远程桌面 (RDS) 是构建虚拟化解决方案，满足每个最终客户需求的首选平台。 RDS 允许交付单个虚拟化应用程序、提供安全的移动和远程桌面访问，以及使最终用户能够从云中运行其应用程序和桌面。

RDS 提供部署灵活性、成本效益和可扩展性。 RDS 通过各种部署选项提供，包括适用于本地部署的 Windows Server 2016、用于云部署的 Microsoft Azure，以及一系列可靠的合作伙伴解决方案。
根据环境和首选项，可以将 RDS 解决方案设置为基于会话的虚拟化，作为 VDI (虚拟) 

目前，远程桌面服务环境中 Teams 支持协作和聊天功能。 若要确保获得最佳用户体验，请遵循本文中的指导。

## <a name="teams-on-rds-with-chat-and-collaboration"></a>RDS 上的 Teams 与聊天和协作

如果你的组织只想使用 Teams 中的聊天和协作功能，你可以设置用户级策略以关闭 Teams 中的呼叫和会议功能。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>设置策略以关闭呼叫和会议功能

可以使用 Microsoft Teams 管理中心或 PowerShell 设置策略。 传播策略更改 (可能需要) 几个小时。 如果未立即看到给定帐户的更改，请在几小时后重试。

[**调用策略**](teams-calling-policy.md)：Teams 包括内置的 DisallowCalling 调用策略，其中所有调用功能都已关闭。 将 DisallowCalling 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。

[**会议策略**](meeting-policies-in-teams.md)：Teams 包括内置的 AllOff 会议策略，其中所有会议功能都已关闭。 将 AllOff 策略分配给组织中在虚拟化环境中使用 Teams 的所有用户。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心分配策略

将 DisallowCalling 调用策略和 AllOff 会议策略分配给用户：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到"用户 **"。**
2. 通过选择用户名左侧选择用户，然后选择"编辑 **设置"。**
3. 执行以下步骤：

    a.  在 **"调用策略"** 下，选择 **"DisallowCalling"。**

    b.  在"**会议策略"** 下，选择 **"AllOff"。**

4. 选择"**应用"。**

若要一次向多个用户分配策略，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。
2. 在 **&#x2713;**（复选标记）列，选择用户。 若要选择所有用户，请选择&#x2713; (顶部的) "复选框。
3. 选择 **"编辑** 设置"，进行您需要的更改，然后选择"应用 **"。**

或者，也可以执行以下步骤：

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到要分配的策略。 例如：

    - 转到 **"语音**  >  **呼叫策略"，** 然后选择 **"DisallowCalling"。**
    - 转到"**会议**  >  **会议策略"，** 然后选择 **"AllOff"。**

2. 选择“管理用户”。
3. 在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。 对想要添加的每一个用户重复此步骤。
4. 添加完用户后，选择"保存 **"。**

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 分配策略

以下示例演示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 将 DisallowCalling 调用策略分配给用户。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要详细了解使用 PowerShell 管理调用策略，请参阅[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy)

以下示例演示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 将 AllOff 会议策略分配给用户。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要详细了解使用 PowerShell 管理会议策略，请参阅[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)