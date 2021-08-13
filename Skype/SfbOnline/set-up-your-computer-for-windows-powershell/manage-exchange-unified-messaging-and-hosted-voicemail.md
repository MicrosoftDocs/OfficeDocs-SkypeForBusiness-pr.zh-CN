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
description: 使用 PowerShell 在 Exchange Online 中管理统一消息自动助理以及托管的语音邮件等Skype for Business功能。
ms.openlocfilehash: 88ee063b644a24dd2cc0922be5df049af4949699745bb2f6cb27f4d3c8203a57
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323554"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>管理 Exchange 统一消息和托管语音邮件

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

可以使用一Exchange cmdlet 在 Skype for Business Online 中管理统一消息和托管语音邮件。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>管理Exchange统一消息和托管语音邮件

以下 cmdlet 可用于管理统一消息Exchange UM (和) 策略：
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **说明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | 当 UM 是托管服务自动助理时，创建和管理用于 Exchange 和订阅者访问服务的联系人对象。  <br/><br/> Skype for BusinessOnline 与 Exchange UM 一起提供多个语音相关功能，包括自动助理和订户访问。 自动助理提供了一种自动应答呼叫并路由到正确人员的方法。 订户访问允许用户连接到 UM Exchange检索电子邮件、语音消息、联系人和日历信息。  <br/><br/> 当Exchange UM 作为托管服务提供时，必须使用 Microsoft PowerShell 创建用于 自动助理 和订阅者访问服务的联系人对象。 这些对象是使用 **CsExUmContact** cmdlet 创建和管理的。 <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | 管理组织中使用的托管语音邮件策略。 托管语音邮件策略指定如何将未接听的呼叫路由到Exchange UM 服务。 这些策略仅影响已启用 UM 托管语音邮件Exchange用户。  <br/><br/> 若要验证用户是否启用了托管语音邮件，请从 PowerShell 提示符运行如下所示的命令。  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>相关主题
[使用 Skype for business Online 管理设置计算机Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
