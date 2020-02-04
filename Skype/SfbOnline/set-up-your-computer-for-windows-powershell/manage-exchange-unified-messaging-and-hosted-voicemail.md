---
title: 管理 Exchange 统一消息和托管语音邮件
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 在 Skype for business Online 中使用 PowerShell 管理 Exchange 统一消息功能，例如自动助理和订阅者访问以及托管语音邮件。
ms.openlocfilehash: d0c2ff8cad705a2d00685e2c6935616ab8d64ac9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692677"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>管理 Exchange 统一消息和托管语音邮件

通过使用一组 cmdlet，可以在 Skype for business Online 中管理 Exchange 统一消息和托管语音邮件。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>管理 Exchange 统一消息和托管语音邮件

以下 cmdlet 可用于管理 Exchange 统一消息（UM）和托管语音邮件策略：
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **说明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | 当 Exchange UM 是托管服务时，创建和管理用于自动助理和订阅者访问服务的联系人对象。  <br/><br/> Skype for business Online 适用于 Exchange UM，可提供多个与语音相关的功能，包括自动助理和订阅者访问。 自动助理提供了一种自动应答和路由到正确人员的通话方式。 订阅者访问使用户能够连接到 Exchange UM 并检索电子邮件、语音消息、联系人和日历信息。  <br/><br/> 当 Exchange UM 作为托管服务提供时，必须使用 Microsoft PowerShell 创建用于自动助理和订阅者访问服务的联系人对象。 通过使用**CsExUmContact** cmdlet 创建和管理这些对象。 <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | 管理组织中使用的托管语音邮件策略。 托管语音邮件策略指定如何将未应答的呼叫路由到 Exchange UM 服务。 这些策略仅影响已启用 Exchange UM 托管语音邮件的用户。  <br/><br/> 若要验证用户是否已启用托管语音邮件，请从 PowerShell 提示符运行类似以下内容的命令。  <br/> \`CsOnlineUser-Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>相关主题
[使用 Windows PowerShell 为 skype for business online 管理设置计算机](set-up-your-computer-for-windows-powershell.md)

  
 
