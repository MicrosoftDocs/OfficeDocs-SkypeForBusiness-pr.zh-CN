---
title: 不支持的浏览器上的 Microsoft Teams 会议
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: nakulm
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 了解 Teams 如何在不受支持的浏览器中支持音频和视频。
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 71fb02fae88f2f61d2d6435e126e20093a5a3baf
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267817"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a>不支持的浏览器上的 Microsoft Teams 会议

某些浏览器（如 Internet Explorer 11、Safari 和 Firefox）支持 Microsoft Teams Web 应用，但不支持某些 Teams 通话和会议功能。 为了解决此限制，Teams Web 应用允许用户通过 PSTN 连接接收音频，并允许用户以更低的显示速率查看显示 (屏幕共享) 显示的内容。

> [!Note]
> 从 2021 年 8 月 17 日开始，Microsoft 365 应用和服务将不支持 Internet Explorer 11， (Microsoft Teams 将不支持 Internet Explorer 11，从 2020 年 11 月 30 日开始) 。 [了解详细信息](https://aka.ms/AA97tsw)。 请注意，Internet Explorer 11 将保留为受支持的浏览器。 Internet Explorer 11 是 Windows 操作系统的一个组件，遵循其安装产品 [的生命周期策略](/lifecycle/faq/internet-explorer-microsoft-edge) 。

当 Teams 检测到不受支持的浏览器时，它会自动显示一条消息，说明问题和会话限制。 该消息提供有关访问会议音频的进一步说明，例如建议用户留下回电号码，以便 Teams 可以呼叫用户，或指示用户拨打会议邀请中包含的会议号码。 该消息还鼓励用户下载和使用 [Teams 桌面客户端](https://teams.microsoft.com/downloads) 以获得完整的 Teams 体验。

如果 PSTN 不可用，用户将看不到访问会议的说明，也无法加入会议。

## <a name="browser-limitations"></a>浏览器限制

在不受支持的浏览器上使用 Teams Web 应用的用户将遇到以下限制：

- 音频仅通过 PSTN 连接提供。 用户无法使用其麦克风。
- 用户无法共享其相机或查看其他参与者的视频，但可以通过基于图像的屏幕共享查看显示的内容。
- 用户无法共享其屏幕，尽管他们可以看到另一个会议参与者共享的屏幕。
- 用户无法在屏幕共享会话期间控制。
- 用户不会收到传入呼叫通知。
- 如果呼叫中断，则会议不会自动重新连接。
- 用户无法启动会议。

有关 Teams 中的浏览器支持的详细信息，请参阅 [Teams 的限制和规范](./limits-specifications-teams.md#browsers)。

## <a name="related-topics"></a>相关主题

- [在不受支持的浏览器上加入 Teams 会议](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)