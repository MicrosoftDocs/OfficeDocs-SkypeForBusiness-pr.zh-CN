---
title: Teams 的浏览器日志和跟踪
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 了解 Microsoft Teams 生成的浏览器和 WebRTC 日志、可在其中找到日志、如何使用Microsoft 支持部门收集日志，以及它们如何帮助进行监视和故障排除。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005455"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Teams 的浏览器日志和跟踪

对于某些类别的错误，Microsoft 支持部门可能需要收集浏览器跟踪。 此信息可以提供有关发生错误时 Teams 客户端状态的重要详细信息。 本文介绍如何为 Teams 收集浏览器和 WebRTC 日志。

## <a name="browser-logs"></a>浏览器日志

在启动浏览器跟踪之前，请确保已登录到 Teams。 请务必在启动跟踪之前执行此操作，以便跟踪不包含敏感登录信息。

登录后，根据你的浏览器选择以下链接之一，然后按照提供的步骤操作。 

-   [Chrome & Edge (Chromium) ](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [火狐](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 在步骤中，将对Azure 门户的所有引用替换为 Teams 客户端。
  
## <a name="webrtc-logs-in-browsers"></a>浏览器中的 WebRTC 日志

WebRTC 日志可以通过提供音频和视频呼叫的连接详细信息来帮助Microsoft 支持部门。 按照以下步骤访问 Edge (Chromium) 或 Chrome 中的 WebRTC 日志：
  
1. 打开新选项卡并转到以下 URL 之一：
    - 边缘 (Chromium) ：`edge://webrtc-internals/`
    - 铬： `chrome://webrtc-internals/`
  
2. 打开 Teams Web 应用程序并重现问题。
  
3. 返回到步骤 1 中访问的选项卡，你将看到至少两个选项卡：
    - GetUserMedia 请求
    - `https://teams.microsoft.com/url`

4. 选择具有 Teams 应用程序名称的选项卡并保存页面内容。

## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)

[在 Teams 中配置日志文件以进行监视和故障排除](/MicrosoftTeams/log-files)
