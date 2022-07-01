---
title: 用于测试直接路由会话边框控制器连接的 PowerShell 脚本
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本示例测试 Microsoft Teams 中的直接路由会话边框控制器连接。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 215edfed535352004c960182bd649721131aedb0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564130"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>用于测试直接路由会话边框控制器连接的 PowerShell 脚本

SIP 测试器客户端是一个示例 PowerShell 脚本，可用于在 Microsoft Teams 中测试直接路由会话边界控制器 (SBC) 连接。 此脚本测试客户配对会话启动协议 (SIP) 中继与直接路由的基本功能。

该脚本将 SIP 测试提交给测试运行程序，等待结果，然后以人为可读的格式显示它。 可以使用此脚本测试以下方案：

- 出站和入站调用
- 同时环
- 媒体升级
- 咨询转移

## <a name="download-the-script-and-documentation"></a>下载脚本和文档

下载 [SIP 测试程序客户端脚本和文档](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。

  > [!NOTE]
  > SIP Tester 客户端脚本仅支持 adal.ps 版本 3.19.8.1。 如果使用了更高版本的 adal.ps，则将返回错误。
  
  
