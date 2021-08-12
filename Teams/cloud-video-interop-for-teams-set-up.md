---
title: 设置 Microsoft Teams 的云视频互操作性
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: 本文介绍如何为组织中用户计划和设置云视频互操作。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bea2f250e91b8a02cefea70db0b80fcd8cc35cce6ecb079c6417c0a6c31bc55c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322754"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>设置 Microsoft Teams 的云视频互操作性

选择云视频[](cloud-video-interop.md)互操作合作伙伴 () 后，需要规划部署、设置预配详细信息和合作伙伴租户密钥，并同意组织中视频互操作应用。 下图概述了该过程。 

![在组织中部署 CVI](media/deploying-cvi.png)

## <a name="plan"></a>规划

有关[确定组织Microsoft Teams](cloud-video-interop.md)合作伙伴的信息，请参阅 Cloud Video Interop for Microsoft Teams for your organization（云视频互操作）。 

规划基于用户/并发/站点范围的启用： 

- 选择一个部署模型/托管模型供你使用
- 选择最适合组织的许可证计划。 
- VM 容量规划是托管视频基础结构。

## <a name="configure"></a>配置 

若要配置云视频互操作，请执行以下步骤。 

1. 从所选合作伙伴/合作伙伴获取配置信息 (租户密钥 appIds...) 。 可以在组织中使用一个或多个视频互操作合作伙伴 

2. 确保网络配置正确。 为外围网络遍历配置基于标准的视频防火墙以支持。 例如： 
    - Cisco VCS-e                  
    - Polycom RPAD

3. 使用 Exchange 和 OTD 配置集成房间。 在大多数情况下，需要在环境中设置和配置其他中继。


## <a name="provision"></a>预配
 
租户密钥将是向合作伙伴服务拨出。 在下面的示例中，813878896@t.plcm.vc 租户密钥。 

![租户密钥示例](media/tenant-key-example.png) 

需要执行以下 cmdlet 来预配租户密钥，同时允许选择用户或整个组织使用视频互操作坐标创建会议。

 
- **[Get-CsTeamsVideoInteropServicepolicy：](/powershell/module/skype/get-csteamsvideointeropservicepolicy)** Microsoft 为每个支持的合作伙伴提供预构建的策略，允许指定 (合作伙伴) 云视频互操作。

    使用此 cmdlet 可以标识可在组织中使用的预构建策略。 可以将此策略分配给利用 Grant-CsTeamsVideoInteropServicePolicy cmdlet 的一个或多个用户。
 
- **[Grant-CsTeamsVideoInteropServicePolicy：](/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** 使用 Grant-CsTeamsVideoInteropServicePolicy cmdlet 可分配预构造的策略，以在组织中使用，或将策略分配给特定用户。
 
- **[New-CsVideoInteropServiceProvider：](/powershell/module/skype/new-csvideointeropserviceprovider)** 使用New-CsVideoInteropServiceProvider指定有关组织希望使用的受支持 CVI 合作伙伴的信息。
 
- **[Set-CsVideoInteropServiceProvider：](/powershell/module/skype/set-csvideointeropserviceprovider)** 使用Set-CsVideoInteropServiceProvider更新有关组织使用的受支持 CVI 合作伙伴的信息。
 
- **[Get-CsVideoInteropServiceProvider：](/powershell/module/skype/get-csvideointeropserviceprovider)** 获取已配置为在组织中使用的所有提供程序。
 
- **[Remove-CsVideoInteropServiceProvider：](/powershell/module/skype/remove-csvideointeropserviceprovider)** 使用Remove-CsVideoInteropServiceProvider删除有关组织不再使用的提供商的所有提供商信息。  
 
## <a name="consent"></a>同意

你需要向 VTC 发送视频电话会议设备 (许可) 合作伙伴服务加入组织会议。 此许可链接也将由合作伙伴提供。  
 
完成这些步骤后，通过上述 Grant cmdlet 单独启用的用户或组织中所有用户（如果已启用租户）将在他们安排的所有 Teams 会议中具有 VTC 坐标。 任何 VTC 都可以通过这些坐标加入这些会议。


|名称|应用程序权限简短说明| 说明|
|--|--|---|
|Calls.JoinGroupCall.All|将群组通话和会议作为应用加入 (预览版) |允许应用在组织中加入群组通话和计划会议，而无需登录用户。  应用将具有目录用户的权限加入租户中的会议。|
|Calls.JoinGroupCallasGuest.All|作为来宾用户加入群组通话和会议 (预览版) |允许应用在组织中匿名加入群组通话和安排的会议，而无需登录用户。  该应用将作为来宾加入租户中的会议。|
|Calls.AccessMedia.All|在通话中以应用或预览版 (媒体) |允许应用在通话中直接访问媒体流，而无需登录用户。|
|OnlineMeetings.Read.All|阅读联机会议详细信息 (预览) |允许应用在组织中阅读联机会议详细信息，而无需登录用户。|

## <a name="schedule"></a>计划

接下来，使用Teams互操作坐标安排会议。 启用的用户可以通过以下方式安排团队会议：
- [Teams适用于会议的会议Outlook](teams-add-in-for-outlook.md)
- Teams客户端桌面和移动版


## <a name="join"></a>Join

可以通过以下Teams与 VTC 设备一起加入会议：
 
- IVR (交互式语音响应) 
    - 可以使用设备拨入合作伙伴的 IVR tenantkey@domain。 
    - 进入合作伙伴 IVR 后，系统会提示输入 VTC conferenceId，然后它将你连接到 Teams 会议。
- 直接拨号
    - 通过使用 tenantkey 的完整Teams直接拨号功能，可以直接拨入 Teams 会议，而无需与合作伙伴的 IVR 交互。VTC ConferenceId@domain。
- 一键式拨号
    - 如果您有集成的Teams会议室，您可以使用合作伙伴合作伙伴提供的一键式拨号功能 (无需键入任何拨号字符串) 。

最后，使用Teams、视频和内容共享与会议中的用户互动。