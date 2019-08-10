---
title: 设置 Microsoft Teams 的云视频互操作性
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: 本文介绍如何为组织中的用户规划和设置云视频互操作。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38a0368a2fb11fb1f6d1a37e5a7f53a1798733d7
ms.sourcegitcommit: 8a8c71aea5bd2420b110619607ef0715136578ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2019
ms.locfileid: "36286252"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>设置 Microsoft Teams 的云视频互操作性

[选择你的云视频互操作合作伙伴](cloud-video-interop.md)后, 你需要规划你的部署、使用预配详细信息和合作伙伴租户密钥进行设置, 并同意你的组织中的视频互操作应用。 下图概括介绍了该过程。 

![在组织中部署 CVI](media/deploying-cvi.png)

## <a name="plan"></a>规划

有关如何确定要在组织中使用的合作伙伴或合作伙伴的信息, 请参阅[Microsoft 团队的云视频互操作](cloud-video-interop.md)。 

规划基于用户的/并行/网站范围的支持: 

- 选择部署模型/托管模型供你使用
- 选择适用于你的组织的许可证计划。 
- 对虚拟机的容量进行规划是您托管的视频基础结构。

## <a name="configure"></a>配置 

若要配置云视频互操作, 请按照下列步骤操作。 

1. 从您选择的合作伙伴/合作伙伴获取配置信息 (租户密钥, appIds ...)。 你可以使用你的组织中的一个或多个视频互操作合作伙伴 

2. 确保您的网络配置正确。 为支持的外围网络遍历配置基于标准的视频防火墙。 例如： 
    - Cisco VCS-e                  
    - Polycom RPAD

3. 通过 exchange 和 OTD 配置集成会议室。 在大多数情况下, 需要在你的环境中设置和配置其他中继。


## <a name="provision"></a>提供
 
租户密钥将是向合作伙伴服务拨出的电话。 在以下示例中, 813878896@t.plcm.vc 是租户密钥。 

![租户密钥示例](media/tenant-key-example.png) 

你将需要执行以下 cmdlet 来设置租户密钥, 还可以启用选择用户或整个组织以使用视频互操作坐标创建会议。

 
- ** [CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft 为每个受支持的合作伙伴提供预构建的策略, 允许你指定要用于云视频互操作的合作伙伴。

    此 cmdlet 允许你标识可在你的组织中使用的预构建的策略。 你可以利用 CsTeamsVideoInteropServicePolicy cmdlet 将此策略分配给一个或多个用户。
 
- **[授权-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** CsTeamsVideoInteropServicePolicy cmdlet 允许你分配一个预构建的策略以供在你的组织中使用, 或将策略分配给特定用户。
 
- **[新-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** 使用 New-CsVideoInteropServiceProvider 指定你的组织要使用的受支持的 CVI 合作伙伴的相关信息。
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** 使用 CsVideoInteropServiceProvider 更新你的组织使用的受支持的 CVI 合作伙伴的相关信息。
 
- ** [CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** 获取已配置为在组织内使用的所有提供商。
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** 使用 Remove-CsVideoInteropServiceProvider 删除有关你的组织不再使用的提供程序的所有提供程序信息。  
 
## <a name="consent"></a>即

你将需要为视频 teleconferencing 设备 (VTCs) 提供权限同意, 以便通过合作伙伴服务加入你的组织会议。 您的合作伙伴也将提供此同意链接。  
 
完成这些步骤后, 通过上述授权 cmdlet 单独启用的用户或组织中的所有用户 (如果启用了租户) 将在其计划的所有团队会议中具有 VTC 坐标。 任何 VTC 都可以通过这些坐标加入这些会议。


|名称|应用程序权限简短说明| 说明|
|--|--|---|
|JoinGroupCall|将组呼叫和会议作为应用加入 (预览)|允许应用在你的组织中加入群组通话和计划会议, 无需登录用户。  应用将使用目录用户的权限加入租户中的会议。|
|JoinGroupCallasGuest|以来宾用户身份加入群组呼叫和会议 (预览)|允许应用在没有登录用户的情况下匿名加入组织中的群组通话和计划会议。  该应用将作为来宾加入到租户中的会议。|
|AccessMedia|在作为应用 (预览版) 的呼叫中访问媒体流|允许应用无需登录用户即可直接访问呼叫中的媒体流。|
|OnlineMeetings 已读。所有|阅读联机会议详细信息 (预览)|允许应用在没有登录用户的情况下阅读您的组织中的联机会议详细信息。|

## <a name="schedule"></a>安排

接下来, 用视频互操作坐标安排团队会议。 已启用的用户可以通过以下方式安排团队会议:
- [适用于 Outlook 的团队会议外接程序](teams-add-in-for-outlook.md)
- 团队客户端桌面和移动版


## <a name="join"></a>Join

你可以通过以下方式与你的 VTC 设备加入团队会议:
 
- IVR (交互式语音响应)
    - 您可以使用 tenantkey @ 域拨入合作伙伴的 IVR。 
    - 在合作伙伴 IVR 中, 系统将提示你输入 VTC conferenceId, 然后该将把你连接到团队会议。
- 直接拨号
    - 通过使用直接拨号功能 tenantkey 的完整字符串, 您可以直接拨入团队会议, 而无需使用直接拨号功能与合作伙伴的 IVR 进行交互。VTC ConferenceId @ domain。
- 单点触控拨号
    - 如果您有一个集成的团队聊天室, 则可以使用合作伙伴提供的一种触摸式拨号功能 (无需键入任何拨号字符串)。

最后, 在会议中使用音频、视频和内容共享与团队用户接洽。 
