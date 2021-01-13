---
title: 不支持的浏览器上的 Microsoft Teams 会议
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解 Teams 如何在不支持的浏览器中支持音频和视频。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4aca1592a89e36e7a26a9a22b111968e4b44a302
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804522"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>不支持的浏览器上的 Microsoft Teams 会议

某些浏览器（如 Internet Explorer 11、Safari 和 Firefox）支持 Microsoft Teams Web 应用，但不支持某些 Teams 呼叫和会议功能。 为了解决此限制，Teams Web 应用允许用户通过 PSTN 连接接收音频，并允许用户以降低的显示速率 (屏幕共享) 呈现的内容。

> [!Note]
> 自 2021 年 8 月 17 日起，Microsoft 365 应用和服务将不支持 Internet Explorer 11 (从 2020 年 11 月 30 日至 2020 年 11 月 30 日Internet Explorer 11) 。 [了解详细信息](https://aka.ms/AA97tsw)。 请注意，Internet Explorer 11 将保留为受支持的浏览器。 Internet Explorer 11 是 Windows 操作系统的一个组件，[](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge)它遵循安装它的产品的生命周期策略。

当 Teams 检测到不受支持的浏览器时，它会自动显示一条消息，说明问题以及会话限制。 该消息提供有关访问会议音频的更多说明，例如建议用户留下回叫号码以便 Teams 可以呼叫用户，或指示用户呼叫会议邀请中包含的会议号码。 该消息还鼓励用户下载并使用 [Teams 桌面客户端](https://teams.microsoft.com/downloads) 获得完整的 Teams 体验。

如果 PSTN 不可用，用户将看不到有关访问会议的说明，并且无法加入会议。

## <a name="browser-limitations"></a>浏览器限制

在不支持的浏览器上使用 Teams Web 应用的人将遇到以下限制：

- 音频仅通过 PSTN 连接提供。 用户不能使用其麦克风。
- 用户无法共享其摄像头或查看其他参与者的视频，但可以通过基于图像的屏幕共享来查看展示的内容。
- 用户无法共享其屏幕，尽管他们可以看到另一个会议参与者共享屏幕。
- 用户在屏幕共享会话期间无法控制。
- 用户不会收到传入呼叫通知。
- 如果呼叫中断，会议不会自动重新连接。
- 用户无法启动会议。

有关 Teams 中的浏览器支持详细信息，请参阅 Teams [的限制和规范](/microsoftteams/limits-specifications-teams#browsers)。

## <a name="related-topics"></a>相关主题

- [在不支持的浏览器上加入 Teams 会议](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
