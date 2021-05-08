---
title: 使用 PowerShell Microsoft Teams协作栏创建Microsoft Teams资源帐户
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 请阅读本主题，了解如何为用户部署协作Microsoft Teams。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115600"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>使用 PowerShell Microsoft 365资源帐户

请阅读本主题，了解如何使用 PowerShell 为协作栏创建Microsoft Teams帐户。

创建资源帐户的最简单方法是使用 Microsoft 365 管理中心。 [请参阅此文章了解如何执行此操作](resource-account-ui.md)。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>要求

使用 Microsoft Teams 会议室 部署Office 365，请确保满足要求。 有关详细信息，请参阅为用户[部署协作Microsoft Teams。](collab-bar-deploy.md)

- 如果需要协作栏的 PSTN 功能，则需要电话系统许可证。

- 你的资源帐户必须具有Exchange邮箱。 由于这些是资源帐户，Exchange许可证。 我们建议对资源帐户使用会议室许可证。


### <a name="add-a-resource-account"></a>添加资源帐户

1. 连接 PowerShell Exchange Online。 有关说明，请参阅 连接[Exchange Online PowerShell。](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)

2. 在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。

   - 若要创建新的会议室邮箱，请使用以下语法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例使用以下设置创建新的会议室邮箱：

     - 名称：Huddle-Room-01

     - 别名：HuddleRoom01

     - 帐户：huddleroom01@contoso.onmicrosoft.com

     - 帐户密码：P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - 若要修改现有会议室邮箱，请使用以下语法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例为别名为 HuddleRoom02 的现有会议室邮箱启用帐户，将密码808P@$$W 0rd。 请注意，帐户 HuddleRoom02@contoso.onmicrosoft.com 现有别名值。

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   有关详细的语法和参数信息，请参阅[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)和[Set-Mailbox。](/powershell/module/exchange/mailboxes/set-mailbox)


3. 在 Exchange Online PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing：自动 (会议组织者直接接收会议室预订决策，无需人工干预：free = accept;busy = decline.) 

   - AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) 

   - DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) 

   - DeleteSubject：$false (保留传入会议请求的主题。) 

   - RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持指定。) 

   - AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) 

   - AdditionalResponse："此聊天室有一个协作栏用于Microsoft Teams！"  (要添加到会议请求的其他文本。) 

   此示例在名为 Huddle-Room-01 的会议室邮箱上配置这些设置。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. 连接运行 powershell cmdlet，通过 MS Online PowerShell 创建 Active `Connect-MsolService -Credential $cred` Directory 设置。   有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

5. 使用以下语法 huddleroom01@contoso.onmicrosoft.com 密码，使密码永不过期：

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. 资源帐户需要具有有效的 Office 365 许可证，最好是 会议室 SKU。 还需要为设备帐户分配使用位置 ，这决定了帐户可以使用哪些许可证 SKUS。 可以使用 检索 `Get-MsolAccountSku` 租户的可用 SKUS Office 365列表。

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    可以使用 Set-MsolUserLicense 分配许可证。 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   有关详细说明，请参阅[使用 PowerShell 向用户帐户Office 365许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。




[使用 PowerShell 为Microsoft Teams栏配置帐户](resource-account-ps.md)

[为 Microsoft Teams](collab-bar-deploy.md)

[适用于 Microsoft Teams 许可的协作栏](../rooms/rooms-licensing.md)