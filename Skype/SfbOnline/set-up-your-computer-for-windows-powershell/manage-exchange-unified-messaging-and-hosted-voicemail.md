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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 使用 PowerShell 管理业务 online 的 Exchange 统一消息功能，如自动助理和订阅者访问和 Skype 中的托管语音邮件。
ms.openlocfilehash: 02fda8c315807899983741f94c1f825de1ebf1a9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873508"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>管理 Exchange 统一消息和托管语音邮件

您可以管理 Exchange 统一消息，并通过使用一组的 cmdlet 来业务 online 承载 Skype 中的语音邮件。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>管理 Exchange 统一消息和承载语音邮件

以下 cmdlet 可用于管理 Exchange 统一消息 (UM) 和托管语音邮件策略：
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **说明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | 创建和管理 Exchange UM 托管的服务时使用的自动助理和订阅者访问服务的联系对象。  <br/><br/> Skype 业务 online 适用于 Exchange UM 以提供多个语音相关的功能，包括自动助理和订阅者访问。 自动助理提供了一种呼叫自动回答和路由至正确的人的方法。 订阅者访问使用户能够连接到 Exchange UM 和检索电子邮件、 语音邮件、 联系人和日历信息。  <br/><br/> 如果 Exchange UM 作为承载的服务，则必须使用 Microsoft PowerShell 创建自动助理和订阅者访问服务中使用的联系对象。 创建和使用**CsExUmContact** cmdlet 管理这些对象。 <br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[Grant-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | 管理组织中使用的托管语音邮件策略。 托管语音邮件策略指定如何未应答的呼叫路由到 Exchange UM 服务。 这些策略影响已启用 Exchange UM 承载语音邮件的唯一用户。  <br/><br/> 若要验证是否为用户启用承载语音邮件，请运行从 PowerShell 提示符类似于下面的命令。  <br/> \`Get-csonlineuser-Identity"kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>相关主题
[设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype](set-up-your-computer-for-windows-powershell.md)

  
 
