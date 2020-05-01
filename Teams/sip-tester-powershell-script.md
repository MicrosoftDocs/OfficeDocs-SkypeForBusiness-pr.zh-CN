---
title: 用于测试直接路由会话边框控制器连接的 PowerShell 脚本
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本示例测试 Microsoft 团队中的直接路由会话边界控制器连接。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d1514eff811461ac8b6ad73f7c2a215205f4e3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951257"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>用于测试直接路由会话边框控制器连接的 PowerShell 脚本

SIP 测试客户端是一个示例 PowerShell 脚本，可用于测试 Microsoft 团队中的直接路由会话边界控制器（SBC）连接。 此脚本通过直接路由测试客户配对的会话初始协议（SIP）干线的基本功能。

该脚本将 SIP 测试提交给测试运行程序，等待结果，然后以可读的格式呈现。 你可以使用此脚本测试以下方案：

- 出站和入站呼叫
- 同时拨打
- 媒体升级
- 顾问式转移

## <a name="download-the-script-and-documentation"></a>下载脚本和文档

下载[SIP 测试器客户端脚本和文档](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP 测试客户端脚本仅支持 adal.ps 版本3.19.8.1。 如果使用 adal.ps 的更高版本，则会返回错误。
  
  
