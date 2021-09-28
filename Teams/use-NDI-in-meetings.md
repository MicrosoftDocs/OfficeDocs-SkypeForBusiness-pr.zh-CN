---
title: 广播会议内容
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何使用 NDI 和 SDI 在 Microsoft Teams 中广播会议内容。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941877"
---
# <a name="broadcast-meeting-content"></a>广播会议内容 



Teams两个选项用于广播Teams内容：网络设备接口 (NewTek NDI®) 和串行数字接口 (SDI) ：

- NewTek NDI® 技术是一种现代解决方案，用于将媒体设备与 (例如工作室相机和混音器) 。 NDI-®技术无需使用物理连接，而是通过本地 Intranet（包括本地计算机）建立连接。

  NDI®技术已成为一种标准行业解决方案，用于为流生成实时内容，并获得了专业广播世界的重要认知和采用。

- 自 1989 年起，SDI 已用于广播生产，并且在大多数旧版工作室硬件设备上受支持。 来自 AJA 视频系统和 Blackmagic 设计的硬件设备提供与使用 SDI 的旧广播设备的连接。

> [!NOTE]
> 支持 SDI 的视频硬件 Out 功能目前以预览版提供。

所有®都支持 NDI 和 SDI 技术。

尝试使用 NDI 和 SDI 的访问权限取决于尝试激活该功能的用户的会议策略。 对于最安全的解决方案，请不要将本地流式处理参数作为全局设置打开。


## <a name="enable-broadcast-features"></a>启用广播功能

若要为用户® NDI 广播和 SDI 广播功能，

1. 租户管理员必须允许最终用户打开其会议策略的本地流式处理。 

2. 最终用户必须打开其特定客户端的本地流式处理。


若要启用最终用户，可以使用管理中心Teams PowerShell Teams，如下所示。

在Teams管理中心，转到"音频>会议&选择"允许 NDI **流****式处理"。**

若要使用 PowerShell，请使用 Set-CsTeamsMeetingPolicy cmdlet，如下所示：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

填充此更改后，最终用户必须从"权限"打开其特定客户端 **设置**  >  **流式处理**。 有关详细信息，请参阅广播[来自 Teams 的音频和视频](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)。





