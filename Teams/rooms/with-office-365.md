---
title: 使用 Office 365 部署 Microsoft Teams 会议室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读本主题，了解如何使用 Microsoft Teams 会议室 部署Office 365。
ms.openlocfilehash: d4c66fb863c5c41a717808ddca43002752510fb5
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056022"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>使用 Office 365 部署 Microsoft Teams 会议室

阅读本主题，了解如何使用 Microsoft Teams 会议室 部署Office 365。

## <a name="requirements"></a>要求

使用 Microsoft Teams 会议室部署Office 365，请确保已满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。

### <a name="add-a-resource-account"></a>添加资源帐户

1. 连接 PowerShell Exchange Online。 有关说明，请参阅 连接[Exchange Online PowerShell。](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. 在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有会议室邮箱。 默认情况下，会议室邮箱没有关联的帐户。 创建或修改允许其进行身份验证的会议室邮箱时，需要添加帐户。

   - 若要创建新的会议室邮箱，请使用以下语法：

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例使用以下设置创建新的会议室邮箱：

     - 名称：会议室 01

     - 别名：ConferenceRoom01

     - 帐户：ConferenceRoom01@contoso.com

     - 帐户密码：P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改现有会议室邮箱，请使用以下语法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例为别名为 ConferenceRoom02 的现有会议室邮箱启用帐户，将密码9898P@$$W 0rd。

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有关详细的语法和参数信息，请参阅[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)和[Set-Mailbox。](/powershell/module/exchange/mailboxes/set-mailbox)


3. 在 Exchange Online PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing：AutoAccept (邮箱自动直接做出会议室预订决策，无需人工干预。) 

   - AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) 

   - DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) 

   - DeleteSubject：$false (保留传入会议请求的主题。) 

   - RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持不变。) 

   - AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) 

   - AdditionalResponse："这是Microsoft Teams会议室！"  (要添加到会议请求的其他文本。) 

   此示例在名为 Project-Rigel-01 的会议室邮箱上配置这些设置。

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)
   
4. 连接运行"连接-MsolService -Credential $cred"powershell cmdlet，通过 MS Online PowerShell 设置 Active Directory 值。 有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

5. 强烈建议在帐户上禁用密码Teams 会议室过期。 下面是如何为帐户 ConferenceRoom01 禁用密码过期的示例：

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. 资源帐户需要具有有效的 Office 365 许可证才能连接到 Microsoft Teams。 还需要为设备帐户分配使用位置 ，这决定了帐户可以使用哪些许可证 SKUS。 可以使用 检索 `Get-MsolAccountSku` 租户的可用 SKUS Office 365列表。 可以使用 `Set-MsolUserLicense` cmdlet 添加许可证。

   此示例将会议室许可证分配给美国的用户。

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   有关详细说明，请参阅[使用 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)向用户帐户Office 365许可证。


## <a name="validate"></a>验证

若要进行验证，应该可以使用任何Microsoft Teams客户端登录到创建的帐户。

## <a name="see-also"></a>另请参阅
[使用其他元数据更新会议室邮箱，以提供更好的搜索和会议室建议体验](/powershell/module/exchange/set-place)

[配置帐户Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[配置 Microsoft Teams 会议室控制台](console.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft Teams 会议室许可](rooms-licensing.md)
