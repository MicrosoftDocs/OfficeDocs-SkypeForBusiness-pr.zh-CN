---
title: 在 Microsoft Teams 中使用 NDI
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用 NDI。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598461"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>在 ® 中使用 NDI Microsoft Teams 技术

 NewTek NDI® (网络设备接口) 技术是一种现代解决方案，用于将媒体设备与 (例如工作室摄像头和混音器) 。 NDI-®技术无需使用物理连接，而是通过本地 Intranet（包括在本地计算机上）建立连接。

NDI® 技术已成为一种标准行业解决方案，用于为流生成实时内容，并获得了专业广播世界的重要认知和采用。

Skype 2018 年底® NDI Skype功能。 Microsoft Teams此功能来改善会议体验。

NDI®仅限本地网络，只应视为生产工作流的一部分，而不是广播解决方案。

## <a name="turn-on-ndi-technology"></a>启用 NDI®技术

NDI®技术要求为用户启用两个步骤。

1. 租户管理员必须在 CsTeamsMeetingPolicy 中启用"AllowNDIStreaming"属性。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 填充此更改后，最终用户必须从"权限"®**客户端启用** NDI设置  >  **技术**。

当用户加入会议时，他们将看到一条消息，通知他们正在直播会议。 如果用户不希望包含在直播中，则需要从会议删除。

下图显示了用户在会议或会议Teams消息。

![he NDI®技术横幅，显示在 Teams 会议。](media/NDI-disclosure.png)

横幅包含指向 [Microsoft 隐私策略 的链接](https://aka.ms/teamsprivacy)。

> [!NOTE]
> NDI®每个会话激活。 下次登录时，用户必须先激活它，然后才能使用 NDI®。

## <a name="supported-locales-and-user-types"></a>支持区域设置和用户类型

所有®都支持 NDI-®技术。 NDI 技术流中包含®用户，但并非所有用户都可以访问 NDI®流：

- 租户内 - 完全支持，基于由会议策略组控制的 ring/tenantId/userId (提供) 
- 联合 - 即使 (1 上具有 NDI®技术，也) <sup>流访问</sup>
- 高级版 - 无流访问
- 匿名 – 无流访问
- 来宾 – 无流访问  

<sup>1</sup> 设备具有默认® NDI 技术设置。 如果会议参与者使用的设备具有 NDI®技术，则需要启用 NDI®技术。
