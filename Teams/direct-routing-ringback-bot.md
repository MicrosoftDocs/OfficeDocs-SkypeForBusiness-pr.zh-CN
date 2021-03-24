---
title: 为直接路由设置环回机器人
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 了解如何使用环回机器人进行直接路由，以防止建立呼叫时可能会发生意外的静音。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098418"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>为直接路由设置环回机器人

本文介绍环回机器人，可用于帮助避免在建立调用需要较长时间时可能会发生意外的静音。 环回机器人可用于非媒体旁路模式下的直接路由。

有时，从公共电话交换网 (PSTN) 到 Teams 客户端的入站呼叫的建立时间可能超过预期。 发生这种情况的原因有多种。 发生这种情况时，呼叫者可能不会听到任何内容，Teams 客户端不会响铃，并且某些电信提供商可能会取消呼叫。

环回机器人可帮助避免此方案中可能会发生意外的静音。 对于从 PSTN 到 Teams 客户端的入站呼叫，环回机器人向呼叫者播放独特的音频信号，以指示 Teams 正在建立呼叫。

> [!NOTE]
> 环回机器人从 Teams 后端生成早期媒体。 在某些国家和地区，当媒体开始流动时，可能会为呼叫付费。

## <a name="configure-the-ringback-bot"></a>配置环回机器人

使用 [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet 修改以前定义的会话边界控制器 (SBC) 配置，或使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet 创建新的 SBC 配置，以及 **GenerateRingingWhileLocatingUser** 参数来配置环回机器人：

- 若要打开环回机器人，将 **GenerateRingingWhileLocatingUser** 参数设置为 **$True。** 此值为默认值。 

- 若要关闭环回机器人，将 **GenerateRingingWhileLocatingUser** 参数设置为 **$False。** 

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)