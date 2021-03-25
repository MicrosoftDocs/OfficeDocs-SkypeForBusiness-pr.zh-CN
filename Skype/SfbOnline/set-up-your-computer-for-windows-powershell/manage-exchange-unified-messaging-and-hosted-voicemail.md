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
description: 使用 PowerShell 管理 Exchange 统一消息传送功能，自动助理 Skype for Business Online 中的订阅者访问和托管语音邮件。
ms.openlocfilehash: 393b0a43cb55462006ef7701396a3b7840032fb4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113198"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>管理 Exchange 统一消息和托管语音邮件

可以使用一组 cmdlet 在 Skype for Business Online 中管理 Exchange 统一消息和托管语音邮件。
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>管理 Exchange 统一消息和托管语音邮件

以下 cmdlet 可用于管理 EXCHANGE 统一消息传送 (UM) 和托管语音邮件策略：
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **说明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | 当 Exchange UM 是托管服务时自动助理订阅者访问服务使用的联系人对象。  <br/><br/> Skype for Business Online 与 Exchange UM 一起提供多个语音相关功能，包括自动助理和订户访问。 自动助理提供了一种自动应答呼叫并路由到正确人员的方法。 订户访问使用户能够连接到 Exchange UM 并检索电子邮件、语音消息、联系人和日历信息。  <br/><br/> 将 Exchange UM 作为托管服务提供时，自动助理 Microsoft PowerShell 创建用于订阅服务器和订阅者访问服务的联系人对象。 这些对象是使用 **CsExUmContact** cmdlet 创建和管理的。 <br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | 管理组织中使用的托管语音邮件策略。 托管语音邮件策略指定如何将未接听的呼叫路由到 Exchange UM 服务。 这些策略仅影响已启用 Exchange UM 托管语音邮件的用户。  <br/><br/> 若要验证用户是否启用了托管语音邮件，请从 PowerShell 提示符运行如下所示的命令。  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>相关主题
[使用 skype for business Online 管理设置计算机Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
