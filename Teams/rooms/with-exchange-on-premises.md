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
ms.openlocfilehash: 15936a805e45ce17ec35822bb02980b4d47499b8
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355611"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises-hybrid"></a>在本地Microsoft Teams 会议室混合Exchange部署 () 

阅读本主题，了解如何在本地和 Microsoft Teams 会议室 混合环境中Exchange部署Microsoft Teams。
  
如果组织混合了一些服务，其中一些托管在本地，一些托管联机，则配置将取决于每个服务的托管位置。 本主题介绍在本地托管Microsoft Teams 会议室Exchange的混合部署。 由于这种类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。 以下过程适用于许多配置。 如果该过程不适用于你的设置，我们建议使用 Windows PowerShell 实现此处介绍的相同最终结果，并用于其他部署选项。
  
## <a name="requirements"></a>要求

在本地使用 Microsoft Teams 会议室部署Exchange之前，请确保已满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。
  
如果要在本地使用 Microsoft Teams 会议室部署Exchange，则使用 Active Directory 管理工具为本地域帐户添加电子邮件地址。 此帐户将同步到 Microsoft 365 或 Office 365。 你将需要执行以下操作：
  
- 创建一个帐户，将该帐户与 Azure Active Directory。

- 启用远程邮箱并设置属性。

- 分配Microsoft 365或Office 365许可证。

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>创建帐户并Azure Active Directory

1. 在 **"Active Directory** 用户和计算机"工具中，右键单击要创建 Microsoft Teams 会议室 帐户的文件夹或组织单位，单击"新建"，然后单击"用户 **"。**

2. 在"显示名称" **框中键入** 名称，在"用户登录名" **框中键入别名** 。 单击" **下一步**"。

3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 **"密码永不过期**"是Microsoft Teams 会议室。 你的域规则可能禁止使用不过期的密码。 如果是这样，则需要为每个帐户创建Microsoft Teams 会议室异常。
  
4. 创建该帐户后，运行目录同步。 完成后，转到用户页Microsoft 365 管理中心验证在之前步骤中创建的帐户已同步到联机状态。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>启用远程邮箱并设置属性

1. [打开 Exchange 命令行管理程序](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或者[使用远程 PowerShell Exchange服务器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. 在 Exchange PowerShell 中，通过运行以下 (为帐户创建邮箱，) 启用该帐户：

   ```PowerShell
   Enable-Mailbox ConferenceRoom01@contoso.com -Room
   ```

   有关详细的语法和参数信息，请参阅[Enable-Mailbox。](/powershell/module/exchange/mailboxes/enable-mailbox)

3. 在 Exchange PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing：自动 (会议组织者直接接收会议室预订决策，无需人工干预。) 

   - AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) 

   - DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) 

   - DeleteSubject：$false (保留传入会议请求的主题。) 

   - RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持不变。) 

   - AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) 

   - AdditionalResponse："这是Microsoft Teams会议室！"  (要添加到会议请求的其他文本。) 

   此示例在名为 ConferenceRoom01 的会议室邮箱上配置这些设置。

   ```PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>分配Microsoft 365或Office 365许可证

1. 连接Azure Active Directory。 有关此Azure Active Directory的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. 资源帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange Microsoft Teams无效。 如果拥有许可证，则需要向资源帐户分配使用位置，这决定了可用于帐户的许可证 SKUS。 可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以检索可用 SKUS 的列表。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 接下来，可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet。 在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   有关详细说明，请参阅[使用 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)向用户帐户Office 365许可证。

若要进行验证，应该可以使用任何客户端登录到此帐户。
  
## <a name="related-topics"></a>相关主题

[配置帐户Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
