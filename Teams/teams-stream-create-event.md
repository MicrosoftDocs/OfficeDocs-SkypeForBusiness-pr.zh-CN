---
title: 在 Microsoft Teams 中创建流
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文将介绍如何为 Microsoft Teams 流式处理事件创建流。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7ff5d15a08f186ae59ccef65fcd8280d84237d1
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767931"
---
# <a name="create-a-live-event-in-microsoft-teams"></a>在 Microsoft Teams 中创建实时事件

> [!IMPORTANT]
> **中国**：目前，没有 IT 管理员帮助，位于中国的用户将无法设置或参加 Microsoft Teams 或 Yammer 实时活动或观看点播视频。
>
> 在开始之前，请与管理员联系，了解他们是否需要设置 VPN 来连接公司网络，以便这些应用可以在组织中无缝工作。

> [!IMPORTANT]
> 设置直播活动时，建议在活动开始前至少 24 小时配置视频、社区和用户权限，以获得最佳体验。 这包括添加用户、更新视频权限以及将社区从专用更改为公共等设置。 某些更改最多可能需要 2 (2) 小时才能跨 Microsoft Stream、Microsoft Teams 和 Microsoft Yammer 传播。 允许 24 小时或更多时间可以根据需要提供测试和进行调整的时间。

## <a name="schedule-the-live-event"></a>安排直播活动

1. 打开 Microsoft Teams 客户端并转到日历。
1. 使用 **“新建会议** ”下拉列表。
1. 选择 **“直播活动** ”选项。
1. 在 **“新建实时事件** ”弹出窗口中，在左侧输入事件详细信息， (**标题**、 **位置**、 **开始**、 **结束**、 **时区** 和 **详细信息**) 。
1. 在同一页上的右侧， **邀请演示者** 单独或通过组添加演示者和制作者。
1. 输入所有内容后，选择“ **下一步**”。
1. 在 **“直播活动权限**”下，选择 **“人员和组**”、“**组织范围**”或 **“公共”**，以指定谁可以观看直播活动。
1. 在“**如何生成实时事件**”下选择 **“Teams 编码器 (预览版”)**
1. 在 **“事件** 选项”下配置所需的选项，例如 **Q&A**、**Captions** 和其他选项。
1. 选择“ **计划** ”以完成直播活动的安排。

## <a name="stream-the-live-event"></a>流式传输直播活动

1. 安排直播活动后，可以在日历邀请的“RTMP 详细信息”部分下检索 **RTMP 服务器引入 URL** 和 **RTMP 密钥**，可以使用这些内容从编码器推送到 RTMP 引入。
1. 若要设置编码器，请将 RTMP 引入 URL 和 RTMP 密钥复制到编码器中，开始将实时编码器源发送到 Team。 在 Microsoft Teams 中使用编码器进行实时传送视频流的详细信息。
1. 使用 Microsoft Teams 客户端，以制作者身份加入直播活动。 还可以从更多 -> 会议选项中找到 RTMP 详细信息。
1. 开始将内容从编码器推送到服务器引入点时，应会看到生成者预览更新。
1. 对设置感到满意并可以在生成者 UI 中查看预览后，请从源选择 **RTMP 源** 并 **实时发送**。
1. 选择“ **开始事件”** 以启动直播活动，发布哪些受众成员可以看到该事件。
1. 完成事件后，在生成者 UI 上选择“ **结束事件** ”。 这将结束事件，并使内容立即可用于点播视频。

有关流式传输实时事件的详细信息，请查看 [使用 Teams 编码器生成实时事件](https://support.microsoft.com/office/produce-a-teams-live-event-using-teams-encoder-b0026c9d-fd37-4bb3-bffc-6961f221fbe9)。
