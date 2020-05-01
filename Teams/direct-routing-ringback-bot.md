---
title: 设置用于直接路由的 Ringback bot
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 了解如何使用 Ringback 机器人进行直接路由，以防止在建立通话时可能出现的意外 silences。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1db113a610c153f821a0d92187744e6ca34e3ce3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951187"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>设置用于直接路由的 Ringback bot

本文介绍了 Ringback 机器人，可用于帮助避免在通话时间较长时可能出现的意外 silences。 Ringback bot 可在非媒体旁路模式下直接路由使用。

有时，从公共交换电话网络（PSTN）到团队客户端的入站呼叫的时间可能比预期的要长。 出现这种情况的原因有多种。 发生这种情况时，呼叫者可能听不到任何声音，团队客户不会听到任何信号，并且呼叫可能被某些电信提供商取消。

Ringback bot 有助于避免在此方案中可能出现的意外 silences。 对于从 PSTN 到团队客户端的入站呼叫，Ringback bot 会向呼叫者播放独特的音频信号，以指示团队正在建立呼叫的过程。

> [!NOTE]
> Ringback 机器人从团队后端生成早期媒体。 在某些国家和地区，当媒体开始流动时，您可能需要支付通话费用。

## <a name="configure-the-ringback-bot"></a>配置 Ringback bot

将[CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway)和[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet 与**GenerateRingingWhileLocatingUser**参数结合使用，配置 Ringback bot。

若要打开 Ringback 机器人，请将**GenerateRingingWhileLocatingUser**参数设置为 " **$True**"。 此值为默认值。 

若要关闭 Ringback 机器人，请将**GenerateRingingWhileLocatingUser**参数设置为 " **$False**"。 

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)