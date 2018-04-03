---
title: 管理 Exchange 统一消息和承载语音邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 使用 PowerShell 的在线业务管理 Exchange 统一消息功能，如自动助理和订阅者访问并在 Skype 的承载语音邮件。
ms.openlocfilehash: 1ececaf2eaefa7373a6707dd4e81f0a3bcaa6d38
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>管理 Exchange 统一消息和承载语音邮件

您可以管理 Exchange 统一消息并使用 cmdlet 一套在线业务承载在 Skype 语音邮件。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>管理 Exchange 统一消息和承载语音邮件

以下 cmdlet 可以用于管理 Exchange 统一消息 (UM) 和承载语音邮件策略：
  
|**Cmdlet**|**说明**|
|:-----|:-----|
|[获得 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [新 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[删除 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[一组 CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |创建和管理用于自动助理和订阅服务器上访问服务时 UM Exchange 托管的服务的联系人对象。  <br/><br/> Skype 的在线业务工作与 UM Exchange 提供几个与语音相关的功能，包括自动助理和订阅者访问。 自动助理提供一种电话自动回答和传送给正确的人。 订阅服务器访问权限允许用户连接到 UM 交换和检索电子邮件、 语音邮件、 联系人和日历信息。  <br/><br/> UM Exchange 作为托管服务提供，必须通过使用 Microsoft PowerShell 创建联系人对象用于自动助理和订阅者访问服务。 这些对象的创建和管理使用**CsExUmContact** cmdlet。 <br/> |
|[获得 CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[授予 CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |管理在组织中使用的承载语音邮件策略。 承载语音邮件策略可以指定如何无人应答的呼叫被路由到交换 UM 服务。 这些策略会影响只有已启用 Exchange UM 承载语音邮件的用户。  <br/><br/> 要验证是否为用户启用了承载语音邮件，请运行与以下内容类似 PowerShell 提示符下的命令。  <br/> 获得 CsOnlineUser-标识"kenmyer@litwareinc.com" | 选择对象 HostedVoiceMail|
   

## <a name="related-topics"></a>相关主题
[设置计算机上的 Skype 业务在线管理使用 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 