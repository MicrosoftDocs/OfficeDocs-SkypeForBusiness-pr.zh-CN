---
title: 用于测试直接路由会话边界控制器连接的 PowerShell 脚本
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本示例测试会话中的直接路由会话边界控制器Microsoft Teams。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1258f85219e5ce6c00f8db5dac3a5233ce2c0717
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627094"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>用于测试直接路由会话边界控制器连接的 PowerShell 脚本

SIP 测试器客户端是一个示例 PowerShell 脚本，可用于测试直接路由会话边界控制器 (SBC) 连接Microsoft Teams。 此脚本使用直接路由测试客户配对会话启动协议 (SIP) 的基本功能。

该脚本将 SIP 测试提交到测试运行程序，等待结果，然后以人工可读的格式显示它。 可以使用此脚本测试以下方案：

- 出站和入站呼叫
- 同时响铃
- 媒体升级
- 咨询转移

## <a name="download-the-script-and-documentation"></a>下载脚本和文档

下载 [SIP Tester 客户端脚本和文档](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP Tester 客户端脚本仅 adal.ps 3.19.8.1 版。 如果使用了更高版本的 adal.ps 将返回错误。
  
  
