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
description: 了解如何使用环回机器人进行直接路由，以防止在建立呼叫时发生意外的静音。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827512"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>为直接路由设置环回机器人

本文介绍环回机器人，可用于帮助避免在建立调用需要更长时间时可能会发生意外的静音。 环回机器人可用于非媒体旁路模式下的直接路由。

有时，从公共电话交换网 (PSTN) 到 Teams 客户端的入站呼叫可能超过预期建立时间。 发生这种情况的原因有多种。 发生这种情况时，呼叫者可能听不到任何声音，Teams 客户端不会响铃，某些电信提供商可能会取消呼叫。

环回机器人可帮助避免此方案中可能会发生意外的静音。 对于从 PSTN 到 Teams 客户端的入站呼叫，环回机器人向呼叫者播放独特的音频信号，指示 Teams 正在建立呼叫。

> [!NOTE]
> 环回机器人从 Teams 后端生成早期媒体。 在一些国家和地区，当媒体开始流动时，你可能需要支付通话费用。

## <a name="configure-the-ringback-bot"></a>配置环回机器人

使用 [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet 修改以前定义的会话边界控制器 (SBC) 配置，或使用 [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet 创建新的 SBC 配置，以及 **GenerateRingingWhileLocatingUser** 参数配置环回机器人：

- 若要打开环回机器人，将 **GenerateRingingWhileLocatingUser** 参数设置为 **$True。** 此值为默认值。 

- 若要关闭环回机器人，请设置 **GenerateRingingWhileLocatingUser** 参数以 **$False。** 

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
