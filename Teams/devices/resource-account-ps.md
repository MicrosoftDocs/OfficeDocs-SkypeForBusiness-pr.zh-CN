---
title: 为使用 PowerShell 的 Microsoft 团队创建协作栏的 Microsoft 团队资源帐户
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
description: 阅读本主题，了解有关如何为 Microsoft 团队部署协作栏的信息。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268015"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>使用 PowerShell 创建 Microsoft 365 资源帐户

阅读本主题，了解有关如何使用 PowerShell 为 Microsoft 团队创建协作栏的资源帐户的信息。

创建资源帐户最简单的方法是使用 Microsoft 365 管理中心。 [有关如何执行此操作的详情，请参阅这篇文章](resource-account-ui.md)。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>要求

在使用 Office 365 部署 Microsoft 团队聊天室之前，请确保满足这些要求。 有关详细信息，请参阅[为 Microsoft 团队部署协作栏](collab-bar-deploy.md)。

- 如果你需要协作栏的 PSTN 功能，您将需要电话系统许可证。

- 您的资源帐户必须具有 Exchange 邮箱。 由于这些资源帐户是资源帐户，因此不需要任何 Exchange 许可证。 我们建议为资源帐户使用会议室许可证。


### <a name="add-a-resource-account"></a>添加资源帐户

1. 连接到 Exchange Online PowerShell。 有关说明，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)。

2. 在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。

   - 若要创建新的会议室邮箱，请使用以下语法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例使用以下设置创建新的会议室邮箱：

     - 名称： Huddle-01

     - 别名： HuddleRoom01

     - 帐户： huddleroom01@contoso.onmicrosoft.com

     - 帐户密码： P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - 若要修改现有的会议室邮箱，请使用以下语法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例启用具有 alias 值 HuddleRoom02 的现有聊天室邮箱的帐户，并将密码设置为 808P@ $ $W 0rd。 请注意，由于现有的别名值，该帐户将 HuddleRoom02@contoso.onmicrosoft.com。

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   有关详细的语法和参数信息，请参阅[新邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。


3. 在 Exchange Online PowerShell 中，在聊天室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing： AutoAccept （会议组织者直接收到会议室保留决定，无需人工干预：闲 = 接受; 忙 = 拒绝。）

   - AddOrganizerToSubject： $false （会议组织者未添加到会议请求的主题。）

   - DeleteComments： $false （保留收到的会议请求的邮件正文中的任何文本。）

   - DeleteSubject： $false （请保留收到的会议请求的主题。）

   - RemovePrivateProperty： $false （确保由会议组织者在原始会议请求中发送的私人标志保持指定。）

   - AddAdditionalResponse： $true （由 AdditionalResponse 参数指定的文本将添加到会议请求。）

   - AdditionalResponse： "此聊天室有一个适用于 Microsoft 团队的协作栏！" （要添加到会议请求的其他文本。）

   此示例在名为 Huddle-01 的聊天室邮箱上配置这些设置。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。

4. 通过运行 PowerShell cmdlet 连接到 MS Online PowerShell 以进行 Active Directory 设置 `Connect-MsolService -Credential $cred` 。   有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支持。 

5. 使用以下语法将 huddleroom01@contoso.onmicrosoft.com 的密码设置为永不过期：

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. 资源帐户需要拥有有效的 Office 365 许可证，最好是会议室 SKU。 你还需要为设备帐户分配一个使用位置，这决定了你的帐户可以使用哪些许可证 Sku。 你可以使用 `Get-MsolAccountSku` 来检索 Office 365 租户的可用 sku 列表。

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    你可以使用 MsolUserLicense 分配许可证。 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   有关详细说明，请参阅[使用 Office 365 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。




[使用 PowerShell 为 Microsoft 团队配置协作栏的帐户](resource-account-ps.md)

[为 Microsoft 团队部署协作栏](collab-bar-deploy.md)

[Microsoft 团队许可的协作栏](../rooms/rooms-licensing.md)


