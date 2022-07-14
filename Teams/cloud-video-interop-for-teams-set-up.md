---
title: 设置 Microsoft Teams 的云视频互操作性
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: 本文介绍如何为组织中的用户计划和设置云视频互操作。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9ae7d59a97989d7f0677bf56b46c0a3d51f3e49
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789327"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>设置 Microsoft Teams 的云视频互操作性

[选择云视频互操作合作伙伴 () ](cloud-video-interop.md)后，需要规划部署、设置预配详细信息和合作伙伴租户密钥，并同意组织中的视频互操作应用。 下图概述了该过程。

![在组织中部署 CVI。](media/deploying-cvi.png)

## <a name="plan"></a>规划

有关确定要在组织中使用的合作伙伴的信息，请参阅 [适用于 Microsoft Teams 的云视频互操作](cloud-video-interop.md) 。

若要规划基于用户/并发/站点范围的启用：

- 选择部署模型/托管模型供你使用
- 选择组织的理想许可证计划。
- 规划 VM 的容量是托管视频基础结构。

## <a name="configure"></a>配置

若要配置云视频互操作，请执行以下步骤。

1. 从 (租户密钥 appIds...) 中选择的合作伙伴/合作伙伴获取配置信息。可以在组织中使用一个或多个视频互操作合作伙伴

2. 确保网络配置正确。 为要支持的外围网络遍历配置基于标准的视频防火墙。 例如：
    - Cisco VCS-e
    - Polycom RPAD

3. 使用 Exchange 和 OTD 配置集成会议室。 在大多数情况下，需要在环境中设置和配置其他中继。

## <a name="provision"></a>提供

租户密钥将是合作伙伴服务的拨号。 在下面的示例中，813878896@t.plcm.vc 是租户密钥。

![租户密钥示例。](media/tenant-key-example.png)

需要执行以下 cmdlet 来预配租户密钥，并允许选择用户或整个组织创建具有视频互操作坐标的会议。

- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy)：** Microsoft 为每个受支持的合作伙伴提供预先构造的策略，允许你指定用于云视频互操作的合作伙伴 () 。

    使用此 cmdlet 可以标识可在组织中使用的预构造策略。 可以利用Grant-CsTeamsVideoInteropServicePolicy cmdlet 将此策略分配给一个或多个用户。

- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy)：** Grant-CsTeamsVideoInteropServicePolicy cmdlet 允许分配预构造的策略以供组织使用，或将策略分配给特定用户。

- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider)：** 使用New-CsVideoInteropServiceProvider指定有关组织想要使用的受支持的 CVI 合作伙伴的信息。

- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider)：** 使用Set-CsVideoInteropServiceProvider更新有关组织使用的受支持的 CVI 合作伙伴的信息。

- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider)：** 获取已配置为在组织内使用的所有提供程序。

- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider)：** 使用Remove-CsVideoInteropServiceProvider删除有关组织不再使用的提供程序的所有提供程序信息。

## <a name="consent"></a>同意

需要为视频电话会议设备提供权限许可 (VTC) 才能通过合作伙伴服务加入组织会议。 此同意链接也将由你的合作伙伴提供。

完成这些步骤后，通过上述 Grant cmdlet 单独启用的用户或组织中的所有用户（如果已启用租户）将在他们安排的所有 Teams 会议中具有 VTC 坐标。 任何 VTC 都可以通过这些坐标加入这些会议。

|名称|应用程序权限短说明| 说明|
|---|---|---|
|Calls.JoinGroupCall.All|将组呼叫和会议作为应用加入 (预览) |允许应用在没有登录用户的情况下加入组织中的组呼叫和计划会议。  应用将以目录用户的权限加入租户中的会议。|
|Calls.JoinGroupCallasGuest.All|以来宾用户身份加入组呼叫和会议 (预览) |允许应用在组织中匿名加入组呼叫和计划会议，而无需登录用户。  该应用将以来宾身份加入租户中的会议。|
|Calls.AccessMedia.All|以应用身份访问呼叫中的媒体流 (预览) |允许应用在没有登录用户的情况下直接访问呼叫中的媒体流。|
|OnlineMeetings.Read.All|阅读联机会议详细信息 (预览) |允许应用在没有登录用户的情况下阅读组织中的联机会议详细信息。|

## <a name="schedule"></a>附表

接下来，使用视频互操作坐标安排 Teams 会议。 已启用的用户可以通过以下方式安排团队会议：

- [适用于 Outlook 的 Teams 会议加载项](teams-add-in-for-outlook.md)
- Teams 客户端桌面和移动设备

## <a name="join"></a>Join

可以通过以下方式将 Teams 会议与 VTC 设备联接：

- IVR (交互式语音响应) 
  - 可以使用tenantkey@domain拨入合作伙伴的 IVR。
  - 加入合作伙伴 IVR 后，系统会提示输入 VTC conferenceId，然后将你连接到 Teams 会议。
- 直拨
  - 可以使用租户密钥的完整字符串使用直接拨号功能直接拨入 Teams 会议，而无需与合作伙伴的 IVR 进行交互。VTC ConferenceId@domain。
- 单击拨号
  - 如果你有一个集成的 Teams 会议室，则可以使用合作伙伴 (提供的一触式拨号功能，而无需键入任何拨号字符串) 。

最后，在会议中使用音频、视频和内容共享与 Teams 用户互动。
