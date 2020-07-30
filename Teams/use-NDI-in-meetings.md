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
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522892"
---
# <a name="use-ndi-in-microsoft-teams"></a>在 Microsoft 团队中使用 NDI

[!INCLUDE [template](includes/preview-feature.md)]

网络设备接口（NDI）是用于连接媒体设备（如画室式照相机和混音器）的新式解决方案。 NDI 通过本地 intranet （包括在本地计算机上）启用连接，而不是使用物理连接。

NewTek NDI®已成为为流制作实时内容的标准行业解决方案，并且在专业直播领域获得重要意识和采纳。

Skype 以前在2018中向 Skype 添加了 NDI 功能。 Microsoft 团队利用此功能改善会议体验。

NDI 限制为本地网络，只能被视为生产工作流的一部分，而不是广播解决方案。

## <a name="turn-on-ndi"></a>打开 NDI

NDI 需要为用户打开两个步骤。

1. 租户管理员必须启用功能标志 enableStreamingCallsOverNdi。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. 填充此更改后，最终用户必须从 "**设置**" 权限为其特定客户端打开 NDI  >  **Permissions**。

当用户加入会议时，他们将看到一条消息，通知他们正在广播会议。 如果用户不希望包含在广播中，则需要将其从会议中删除。

下图显示了用户在团队会议中看到的标题消息。

![团队会议中显示的 NDI 横幅的图像。](media/NDI-disclosure.png)

横幅有一个指向[Microsoft 隐私声明策略](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi)的链接。

## <a name="supported-locales-and-user-types"></a>支持的区域设置和用户类型

所有区域设置均支持 NDI。 在 NDI 会议中支持以下用户：

- 租户内-完全支持，基于震铃/tenantId/userId （由会议策略 + 功能标志控制）提供
- 联盟–否（即使他们有 NDI）<sup>1</sup>
- Freemium-否（默认值）
- 匿名–否（默认值）
- 来宾–否（默认值）

<sup>1</sup>台设备的 NDI 设置在默认情况下处于打开状态。 如果会议参与者使用 NDI 关闭的设备，则他们需要启用 NDI。
