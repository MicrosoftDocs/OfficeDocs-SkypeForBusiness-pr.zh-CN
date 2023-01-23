---
title: 需要敏感 Teams 会议的水印
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 了解如何在敏感 Teams 会议中对与会者视频和共享内容启用或要求水印。
ms.openlocfilehash: 6037bc6e9dbe79d9ecee10666f4c34e4e778216a
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950499"
---
# <a name="require-a-watermark-for-sensitive-teams-meetings"></a>需要敏感 Teams 会议的水印

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

你可以为屏幕上共享的内容和与会者视频启用在 Teams 会议中显示的水印。 水印显示会议参与者的电子邮件地址。 会议参与者无法关闭水印。

Teams 桌面版和移动设备支持水印。 人员从不受支持的平台加入会议将具有仅音频体验。

从 [云视频互操作 (CVI) ](cloud-video-interop.md)加入的参与者将能够查看没有水印的内容。

使用水印时，以下参与者将具有仅音频体验：

- 使用 Teams Web 客户端的参与者
- 虚拟桌面基础结构 (VDI) 参与者
- 匿名参与者
- 溢出参与者
- Windows 上的Microsoft Teams 会议室和 Surface Hub 上的 Microsoft Teams 会议室
- Android 上的Microsoft Teams 会议室
- 较旧的 Teams 客户端
- [Microsoft Teams 会议室设备上的直接来宾加入](/microsoftteams/rooms/third-party-join)

> [!Note]
> 敏感度标签、自定义会议模板和水印中的会议设置需要Teams 高级版。

Teams 管理中心中启用了会议水印。 然后，会议组织者可以添加它们，或者由模板或敏感度标签强制实施。

下表显示了配置水印的位置：

|设置|管理员策略|敏感度标签|模板|会议组织者|
|:------|:----------:|:---------------:|:------:|:---------------:|
|对共享内容应用水印|是|是|是|是|
|对每个人的视频源应用水印|是|是|是|是|

在会议中使用水印时，会关闭以下功能：

- 会议录制，包括自动录制

- 大型库

- 协同模式

- PowerPoint Live

- 白板

- 来自相机的内容

## <a name="watermarks-for-sensitive-and-highly-sensitive-meetings"></a>敏感和高度敏感会议的水印

水印可用于保护会议中共享的机密信息。 与通常无权访问信息的人员共享信息时，这非常有用。 例如，财务组织成员在与来自不同部门的经理共享季度估算时，可能会使用水印。

由于水印旨在降低机密信息外泄的可能性，因此在所有参与者都可直接访问共享内容的会议中使用水印可能不会增加安全性。

有关将水印与其他会议功能结合使用以帮助保护会议中的机密信息的信息，请参阅 [配置 Teams 会议，保护高度敏感数据](/microsoftteams/configure-meetings-highly-sensitive-protection)。

## <a name="enable-watermarks"></a>启用水印

若要在模板和敏感度标签中提供水印，以及会议组织者，必须在 Teams 管理中心启用水印。

为会议启用水印

1. 在 Teams 管理中心中，展开 **“会议** ”，然后选择“ **会议策略**”。

1. 选择要更新的策略。

1. 若要在与会者视频上启用水印，请将 **“水印视频”** 设置为“ **开**”。

1. 若要在会议中在屏幕上共享的内容启用水印，请将 **“水印共享内容** ”设置为“ **打开**”。

    ![水印的 Teams 管理策略的屏幕截图](media/watermark-admin-policy.png)

1. 若要查看水印在桌面和移动设备上的外观，请选择“ **预览**”。

1. 选择“**保存**”。

还可以使用 PowerShell 启用或禁用水印。 将 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 与 和 `-AllowWatermarkForScreenSharing` 参数一起使用`-AllowWatermarkForCameraVideo`。

例如：

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## <a name="related-topics"></a>相关主题

[使用三层保护配置 Teams 会议](configure-meetings-three-tiers-protection.md)

[将 Teams 会议模板、敏感度标签和管理策略用于敏感会议](meeting-templates-sensitivity-labels-policies.md)
