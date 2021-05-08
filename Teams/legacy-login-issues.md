---
title: 在旧版系统上收到消息和调用时Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 排查与在旧系统上接收消息和调用相关的问题
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1c209d1acc83e63792722b00b63be5a6b9f3721a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120603"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>在旧系统上接收消息和调用时的问题
==============================================================

如果用户使用的是旧版应用程序，或者已使用其他应用程序登录，则Teams接收消息或呼叫时可能收到问题。

## <a name="legacy-adu-setups"></a>旧版 ADU 设置

 如果用户登录到了加入域的计算机，并且你 **不希望他们的用户名预填充在 Teams 登录屏幕上**，则管理员可以设置以下 Windows 注册表来关闭用户名预填充 (UPN)：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> 默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。

有关详细信息[，请参阅Microsoft Teams新式身份验证](sign-in-teams.md)登录。

## <a name="skype-token-revocation"></a>Skype令牌吊销

更改/重置密码时，较旧的客户端最多一小时不会收到消息和呼叫。 若要解决此问题，请重新启动应用或移动到较新的客户端。


## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)