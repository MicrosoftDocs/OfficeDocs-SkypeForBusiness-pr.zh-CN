---
title: 在团队中接收消息和旧式系统上的通话时出现问题
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
description: 解决在旧版系统上接收消息和呼叫相关的问题
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489155"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>在旧式系统上接收消息和通话时出现问题
==============================================================

如果用户使用较早版本的团队或已使用其他应用程序登录，则用户可能会遇到问题，即接收邮件或呼叫。

## <a name="legacy-adu-setups"></a>旧版 ADU 设置

 如果用户登录到了加入域的计算机，并且你**不希望他们的用户名预填充在 Teams 登录屏幕上**，则管理员可以设置以下 Windows 注册表来关闭用户名预填充 (UPN)：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> 默认情况下会跳过或忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。

有关详细信息，请参阅[使用新式身份验证登录 Microsoft 团队](sign-in-teams.md)。

## <a name="skype-token-revocation"></a>Skype 令牌吊销

更改/重置密码时，旧客户端将不会收到最长一小时的消息和呼叫。 若要解决此问题，请重新启动应用或移动到较新的客户端。
