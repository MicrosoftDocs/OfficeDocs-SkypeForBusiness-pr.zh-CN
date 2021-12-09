---
title: 使用 Exchange Online 部署 Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读本主题，了解如何使用本地Microsoft Teams 会议室Exchange Online Skype for Business Server部署资源。
ms.openlocfilehash: 8f8511f4dd05b6d2eb073aaab0a14305c9d67831
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355631"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>使用 Exchange Online 部署 Microsoft Teams Rooms

阅读本主题，了解如何使用 Microsoft Teams 会议室 部署Exchange Online。
  
如果组织混合了一些服务，其中一些托管在本地，一些托管联机，则配置将取决于每个服务的托管位置。 本主题介绍使用联机托管Microsoft Teams 会议室的Exchange混合部署。 由于这种类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。 以下过程适用于许多配置。 如果该过程不适用于你的设置，我们建议使用 Windows PowerShell 实现此处介绍的相同最终结果，并用于其他部署选项。

## <a name="requirements"></a>要求

使用 Microsoft Teams 会议室部署Exchange Online，请确保满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。
  
若要使用 Microsoft Teams 会议室 部署Exchange Online，请执行以下步骤。 确保你有合适的权限来运行相关 cmdlet。 

   > [!NOTE]
   >  本部分[Azure Active Directory cmdlet](/powershell/azure/active-directory/overview)的 Azure Active Directory Windows PowerShell 模块 (例如，Set-MsolUser) 已在为 Microsoft Teams 会议室 设备设置帐户中进行测试。 其他 cmdlet 可能正常工作，但是，它们尚未在此特定方案中进行测试。

如果部署了 Active Directory 联合身份验证服务 (AD FS) ，则执行这些步骤之前，可能需要将用户帐户转换为托管用户，然后在完成这些步骤后将用户转换回联合用户。
  
### <a name="create-an-account-and-set-exchange-properties"></a>创建帐户并设置 Exchange 属性

1. 在电脑上Windows PowerShell远程连接会话并连接到Exchange Online，如下所示：

    ``` Powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline
    ```

2. 建立会话后，将创建新邮箱并启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许帐户在 Microsoft Teams 会议室 中进行身份验证。

   如果要更改现有的资源邮箱：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果要创建新的资源邮箱：

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 若要改善会议体验，需要在用户帐户上设置Exchange属性，如下所示：

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>为你的本地域帐户添加电子邮件地址

1. 在 **"Active Directory** 用户和计算机 AD"工具中，右键单击要创建 Microsoft Teams 会议室 帐户的容器或组织单位，单击"新建"，然后单击"用户 **"。**
2. 将显示名称 ( - ) cmdlet (Set-Mailbox 或 New-Mailbox) 中的) 标识名称键入到"全名"框中，将别名键入到"用户 **登录** 名称"框中。 单击" **下一步**"。
3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 **"密码永不过期**"是Skype for Business Server密码Microsoft Teams 会议室。 你的域规则可能禁止使用不过期的密码。 如果是这样，则需要为每个用户帐户创建Microsoft Teams 会议室异常。
  
4. 单击“**完成**”创建帐户。
5. 创建帐户后，运行目录同步。 这可以通过在 PowerShell 中使用 [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) 实现。 完成后，转到"用户"页，验证在之前步骤中创建的两个帐户已合并。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>分配Microsoft 365或Office 365许可证

1. 首先，连接到Azure AD应用某些帐户设置。 你可以通过运行此 cmdlet 来进行连接。 有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview)

    ``` PowerShell
   Connect-MsolService
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. 用户帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange正常工作。 如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 您将在以下步骤中完成分配。
3. 接下来，使用 `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> 检索组织或组织的可用 SKUS Microsoft 365 Office 365列表。
4. 可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet。 在这种情况下，应用Microsoft Teams 会议室标准版许可证。 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses "contoso:MEETING_ROOM"
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

## <a name="related-topics"></a>相关主题

[配置帐户Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
