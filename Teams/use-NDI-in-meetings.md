---
title: 在 Microsoft 团队中使用 NDI
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Microsoft 团队中使用 NDI。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308165"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>在 Microsoft 团队中使用 NDI®技术

 NewTek NDI® (网络设备接口) 技术是用于连接媒体设备 (（如 studio 相机和混音器) ）的新式解决方案。 除了使用物理连接之外，NDI®技术可以通过本地 intranet （包括在本地计算机上）实现连接。

NDI®技术已经成为一种标准的行业解决方案，可用于为流制作实时内容，并在专业直播领域获得重要意识和采纳。

Skype 以前在2018中向 Skype 添加了 NDI®功能。 Microsoft 团队使用此功能改善会议体验。

NDI®技术限制为本地网络，只能被视为生产工作流的一部分，而不是广播解决方案。

## <a name="turn-on-ndi-technology"></a>打开 NDI®技术

NDI®技术要求为用户打开两个步骤。

1. 租户管理员必须在 CsTeamsMeetingPolicy 中启用 "AllowNDIStreaming" 属性。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 填充此更改后，最终用户必须从 "**设置**" 权限为其特定客户端打开 NDI®技术  >  **Permissions**。

当用户加入会议时，他们将看到一条消息，通知他们正在广播会议。 如果用户不希望包含在广播中，则需要将其从会议中删除。

下图显示了用户在团队会议中看到的标题消息。

![在团队会议中显示的 NDI®技术横幅的图像。](media/NDI-disclosure.png)

横幅有一个指向 [Microsoft 隐私声明策略](https://aka.ms/teamsprivacy)的链接。

## <a name="supported-locales-and-user-types"></a>支持的区域设置和用户类型

NDI®技术在所有区域设置中均受支持。 以下用户包括在 NDI®技术流中，但并非所有用户都可以访问 NDI®技术流：

- 租户内-完全支持，根据 "震铃/tenantId/userId" (提供，由会议策略控制) 
- 联合-即使他们在) <sup>1</sup>上有 NDI®技术，也不能 (流访问
- Freemium-无流访问
- 匿名–无流访问
- 来宾-无流访问  

<sup>1</sup> 台设备的 NDI®技术设置，默认情况下处于打开状态。 如果会议参与者使用的设备的 NDI®技术关闭，他们需要打开 NDI®技术。
