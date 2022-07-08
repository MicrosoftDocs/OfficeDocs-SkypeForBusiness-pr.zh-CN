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
ms.openlocfilehash: 5d048063f7b8efa6b853aa7273e0bcefaeb41b1f
ms.sourcegitcommit: 9175c6d542dd825ce965d0cb7c67264f22315202
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2022
ms.locfileid: "66687818"
---
# <a name="broadcast-meeting-content"></a>广播会议内容 



Teams 提供了两个用于广播 Teams 会议内容的选项：网络设备接口 (NewTek NDI®) 和串行数字接口 (SDI) ：

- NewTek NDI® 技术是一种新式解决方案，用于连接媒体设备 (，如工作室相机和混合器) 。 NDI® 技术可通过本地 Intranet（包括本地计算机）建立连接，而不是使用物理连接。

  NDI® 技术已成为为流制作实时内容的标准行业解决方案，并在专业广播界获得了显著的认知和采用。

- 自 1989 年以来，SDI 一直用于广播制作，并且在大多数旧版工作室硬件设备上受支持。 AJA 视频系统和 Blackmagic Design 中的硬件设备提供与使用 SDI 的旧版广播设备的连接。

> [!NOTE]
> 支持 SDI 的视频硬件 Out 功能目前处于预览版中。

所有区域设置都支持 NDI® 和 SDI 技术。

使用 NDI 和 SDI 的访问权限由尝试激活该功能的用户的会议策略决定。 对于最安全的解决方案，请勿将本地流式处理参数作为全局设置打开。


## <a name="enable-broadcast-features"></a>启用广播功能

为用户启用 NDI® 和 SDI 广播功能：

1. 租户管理员必须使最终用户能够为其会议策略启用本地流式处理。 

2. 最终用户必须为其特定客户端启用本地流式处理。


若要启用最终用户，可以使用 Teams 管理员中心或 Teams PowerShell，如下所示。

在 Teams 管理中心，转到 **会议策略>音频&视频** ，然后选择 **“本地广播**”。

若要使用 PowerShell，请使用Set-CsTeamsMeetingPolicy cmdlet，如下所示：

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

填充此更改后，最终用户必须从 **“设置** 权限” > 为其特定客户端启用本地流 **式** 处理。 有关详细信息，请参阅 [Teams 中的广播音频和视频](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)。





