---
title: 在 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中使用 NDI。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a82174fd09106f623bcf0f9a03a99c2978253ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615108"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>在 Microsoft Teams 中® NDI Microsoft Teams

 NewTek NDI® (网络设备接口) 技术是一种现代解决方案，用于将媒体设备与 (例如工作室相机和混音器) 。 NDI-®技术无需使用物理连接，而是通过本地 Intranet（包括本地计算机）建立连接。

NDI® 技术已成为一种标准行业解决方案，用于为流生成实时内容，并获得了专业广播世界的重要认知和采用。

Skype 2018 年底® NDI Skype功能。 Microsoft Teams此功能来改善会议体验。

NDI®仅限本地网络，只应视为生产工作流的一部分，而不是广播解决方案。

## <a name="turn-on-ndi-technology"></a>启用 NDI®技术

NDI®技术要求为用户启用两个步骤。

1. 租户管理员必须允许最终用户为会议策略启用 NDI。 可以在管理门户中单独完成此操作，Teams CsTeamsMeetingPolicy 中的 _AllowNDIStreaming_ 属性通过 Teams PowerShell 完成此操作。

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. 填充此更改后，最终用户必须从"权限"中®特定客户端 **启用** NDI设置  >  **技术**。

为用户及其特定客户端启用后，用户可以通过溢出菜单并选择"通过 NDI 广播"来启用 NDI。

启动 NDI 并让终结点订阅 NDI 源后，他们将看到一条消息，通知他们会议正在直播。 如果用户不希望包含在直播中，则需要从会议删除。

下图显示了用户在会议结束后看到的横幅Teams消息。

![he NDI®技术横幅，显示在 Teams 会议。](media/NDI-disclosure.png)

横幅包含指向 [Microsoft 隐私策略 的链接](https://aka.ms/teamsprivacy)。

> [!NOTE]
> NDI®仅按会话激活。 下一次会议中，用户必须先激活它，然后才能使用 NDI®。

## <a name="supported-locales-and-user-types"></a>支持区域设置和用户类型

所有®都支持 NDI-®技术。

使用 NDI 的访问权限由尝试激活该功能的用户的会议策略确定。 对于最安全的解决方案，请不要将 NDI 策略作为全局设置打开。
