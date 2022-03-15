---
title: 使用 Exchange Online 部署 Microsoft Teams Rooms
ms.author: czawideh
author: cazawideh
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读本主题，了解如何使用 Microsoft Teams 会议室 部署Exchange Online。
ms.openlocfilehash: ad3b621ef541fcec471e329d1696e4f7000f4cb5
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503739"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>使用 Exchange Online 部署 Microsoft Teams Rooms

阅读本主题，了解如何使用 Microsoft Teams 会议室 部署Exchange Online。
  
如果组织混合了一些服务，其中一些托管在本地，一些托管联机，则配置将取决于每个服务的托管位置。 本主题介绍使用联机托管Microsoft Teams 会议室的Exchange混合部署。 由于这种类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。 以下过程适用于许多配置。 如果该过程不适用于你的设置，我们建议使用 Windows PowerShell 实现此处介绍的相同最终结果，并用于其他部署选项。

## <a name="requirements"></a>要求

使用 Microsoft Teams 会议室部署Exchange Online，请确保已满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。
  
若要使用 Microsoft Teams 会议室 部署Exchange Online，请执行以下步骤。 请确保拥有运行 cmdlet 所需的正确权限。 

   > [!NOTE]
   >  本部分[Azure Active Directory cmdlet 的 Windows PowerShell](/powershell/azure/active-directory/overview?view=azureadps-1.0) 模块 (例如，Set-MsolUser) 已在为 Microsoft Teams 会议室 设置帐户中进行测试。 其他 cmdlet 可能正常工作，但是，它们尚未在此特定方案中进行测试。

如果部署了 Active Directory 联合身份验证服务 (AD FS) ，则执行这些步骤之前，可能需要将用户帐户转换为托管用户，然后在完成这些步骤后将用户转换回联合用户。
  
### <a name="create-an-account-and-set-exchange-properties"></a>创建帐户并设置 Exchange 属性

1. 在电脑上Windows PowerShell远程连接会话并连接到Exchange Online，如下所示：

    ``` Powershell
   Connect-ExchangeOnline
    ```

2. 建立会话后，将创建新邮箱并启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许帐户通过 Microsoft Teams 会议室。

   如果要更改现有的资源邮箱：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果要创建新的资源邮箱：

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name 'ConferenceRoom01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 若要改善会议体验，需要在用户帐户上设置Exchange属性，如下所示：

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Rooms enabled  room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>为你的本地域帐户添加电子邮件地址

1. 在 **"Active Directory** 用户和计算机 AD"工具中，右键单击要创建 Microsoft Teams 会议室 帐户的容器或组织单位，单击"新建"，并单击"用户 **"**。
2. 将显示名称 ( - ) cmdlet (Set-Mailbox 或 New-Mailbox) 键入到"全名"框中，将别名键入到"用户 **登录** 名称"框中。 单击" **下一步**"。
3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 **"密码永不过期**"是Microsoft Teams 会议室。 你的域规则可能禁止使用不过期的密码。 如果是这样，则需要为每个用户帐户创建Microsoft Teams 会议室异常。
  
4. 单击“**完成**”创建帐户。
5. 创建帐户后，运行目录同步。 这可以通过在 PowerShell 中使用 [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 实现。 完成后，转到用户页面，验证在之前步骤中创建的两个帐户已合并。

### <a name="assign-an-office-365-license"></a>分配一个 Office 365 许可证

1. 首先，连接到Azure AD应用某些帐户设置。 你可以通过运行此 cmdlet 来进行连接。 有关 Active Directory 的详细信息，请参阅 [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)。

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)。

    ``` PowerShell
   Connect-MsolService
    ```

2. 用户帐户需要具有有效的 Office 365 许可证才能连接到 Microsoft Teams。 如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。
3. 使用"Get-MsolAccountSku"检索租户的可用 SKU Office 365列表。
4. 列出 SKUS 后，可以使用"Set-MsolUserLicense"添加许可证 <!-- Set-AzureADUserLicense--> cmdlet。 

    ```PowerShell
     Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM
    ```

## <a name="validate"></a>验证

若要进行验证，应该可以使用任何Microsoft Teams客户端登录到创建的帐户。
  
## <a name="see-also"></a>另请参阅

[使用其他元数据更新会议室邮箱，以提供更好的搜索和会议室建议体验](/powershell/module/exchange/set-place)

[为帐户配置Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
