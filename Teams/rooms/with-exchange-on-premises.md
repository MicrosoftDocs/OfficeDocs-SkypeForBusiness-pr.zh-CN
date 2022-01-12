---
title: '在本地Microsoft Teams 会议室混合Exchange部署 () '
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 请阅读本主题，了解如何在本地Microsoft Teams 会议室混合环境中部署Exchange部署。
ms.openlocfilehash: ea05ef6b6bf6e13ee907d84d1d48200c0cea5a09
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767225"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>在本地Microsoft Teams 会议室混合Exchange部署 () 

阅读本主题，了解如何在本地和 Microsoft Teams 会议室 混合环境中Exchange部署Microsoft Teams。
  
如果组织混合了一些服务，其中一些托管在本地，一些托管联机，则配置将取决于每个服务的托管位置。 本主题介绍在本地托管Microsoft Teams 会议室Exchange的混合部署。 由于这种类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。 以下过程适用于许多配置。 如果该过程不适用于你的设置，我们建议使用 Windows PowerShell实现此处介绍的相同最终结果，并用于其他部署选项。
  
## <a name="requirements"></a>要求

在本地Microsoft Teams 会议室 Exchange之前，请确保已满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>启用远程邮箱并设置属性

1. [打开 Exchange 命令行管理程序](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或者[使用远程 PowerShell Exchange服务器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. 在 Exchange PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。 默认情况下，会议室邮箱没有关联的帐户，因此创建或修改会议室邮箱时需要添加帐户，以便使用 Microsoft Teams。

   - 若要创建新的会议室邮箱，请使用以下语法：

     ``` PowerShell
     New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     
     此示例使用以下设置创建新的会议室邮箱：

     - 帐户：ConferenceRoom01@contoso.com
  
     - 名称：ConferenceRoom01

     - 别名：ConferenceRoom01

     - 帐户密码：P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改现有会议室邮箱，请使用以下语法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例为别名为 ConferenceRoom02 的现有会议室邮箱启用帐户，将密码9898P@$$W 0rd。 请注意，帐户 ConferenceRoom02@contoso.com 现有别名值。

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有关详细的语法和参数信息，请参阅[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)和[Set-Mailbox。](/powershell/module/exchange/mailboxes/set-mailbox)

3. 在 Exchange PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing：会议组织者 (自动接收会议室预订决策，无需人工干预。) 

   - AddOrganizerToSubject：$false (会议组织者不会添加到会议请求的主题。) 

   - DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) 

   - DeleteSubject：$false (保留传入会议请求的主题。) 

   - RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持不变。) 

   - AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) 

   - AdditionalResponse："这是Microsoft Teams会议室！"  (要添加到会议请求的其他文本.) 

   此示例在名为 ConferenceRoom01 的会议室邮箱上配置这些设置。

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="set-password-to-never-expire"></a>将密码设置为永不过期

1. 在 **"Active Directory 用户和** 计算机"工具中，Microsoft Teams 会议室帐户，右键单击并选择"属性 **"。**

2. 选中"**密码永不过期"** 复选框，然后单击"确定 **"。**

   > [!NOTE]
   > 选择 **"密码永不过期**"是Microsoft Teams 会议室。 你的域规则可能禁止使用不过期的密码。 如果是这样，则需要为每个帐户创建Microsoft Teams 会议室异常。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>分配Microsoft 365或Office 365许可证

1. 连接Azure Active Directory。 有关此Azure Active Directory的详细信息，请参阅 Azure [ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. 资源帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange Microsoft Teams无效。 如果拥有许可证，则需要向资源帐户分配使用位置，这决定了可用于帐户的许可证 SKUS。 可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以检索可用 SKUS 的列表。

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

3. 接下来，可以使用 `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet。 此示例将会议室许可证添加到帐户：

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   有关详细说明，请参阅[使用 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)向用户帐户Office 365许可证。

若要进行验证，应该可以使用任何客户端登录到此帐户。
  
## <a name="related-topics"></a>相关主题

[为帐户配置Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
