---
title: 在 Microsoft 365 和 Office 365 中预配 Skype 会议室系统帐户
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Microsoft 365 或 Office 365 中预配 Skype 会议室系统帐户。
ms.openlocfilehash: 8e44e648e12ec4db1e8acf9617c02937f9418c41
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569374"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>在 Microsoft 365 和 Office 365 中预配 Skype 会议室系统帐户
 
阅读本主题，了解如何在 Microsoft 365 或 Office 365 中预配 Skype 会议室系统帐户。
  
以下部分介绍了 Skype 会议室系统帐户设置。
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 和 Office 365 必备组件

联机租户必须满足以下要求：
  
- Microsoft 365 或 Office 365 计划必须包括 Skype for Business Online 计划 2 或 Office 365 E1、E3 或 E5。 <br/>有关 Skype for Business Online 计划的详细信息，请参阅 [Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。
    
- 你的租户必须启用 Skype for Business 的会议功能。
    
- 租户必须启用 Exchange Online。 
    
- 租户远程管理员必须具有以下 PowerShell 访问权限：
    
  - Exchange 远程 PowerShell 访问
    
  - Skype for Business Online 远程 PowerShell 访问
    
  - Windows Azure Active Directory 模块Windows PowerShell访问 Microsoft 365 或 Office 365 目录访问权限
    
对于 Skype 会议室帐户，需要以下许可：
  
- 需要 Skype for Business Online 计划 2 或 Office 365 E1 或 E3 许可证才能启用 Skype 会议。
    
- 若要使会议室具有 企业语音 功能，以便可以使用电话号码启用会议室，需要具有电话系统许可证或 Office 365 E5 的 Skype for Business Online 计划 2 (1) 。
    
- 如果需要来自会议的电话拨入功能，则需要音频会议和电话系统许可证。  如果需要会议拨出功能，则需要国内或国内和国际通话套餐。 
    
- Skype 会议室帐户不需要 Exchange Online 许可证，因为该帐户应配置为资源邮箱帐户。
    
## <a name="provisioning-overview"></a>预配概述

下图概述了 Skype 会议室系统帐户设置流。
  
![Skype 会议室系统预配步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>确定新的会议室

你可能已经在 Exchange 中拥有提供计划功能的资源会议室邮箱，或者你可能第一次创建资源邮箱来推动 Skype 会议室系统部署。 在任何情况下，都必须标识要用于租户的会议室帐户。 Exchange Online 预配和 Skype for Business 预配部分为这两种类型的帐户提供指导。 例如，假设你有以下两个会议室，并且你要为这两个会议室部署 Skype 会议室系统：
  
- 现有资源邮箱帐户：confrm1@contoso.onmicrosoft.com
    
- 新建资源邮箱帐户：confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 预配

首先，按照主题"连接到 Exchange Online PowerShell"中的说明连接到[Exchange Online PowerShell。](https://go.microsoft.com/fwlink/p/?LinkId=396554)
  
若要为 Skype 会议室系统设置现有资源会议室邮箱帐户，请运行 Exchange Online PowerShell 中的以下命令：
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

若要为 Skype 会议室系统创建新的 Exchange 资源邮箱帐户，请运行 Exchange Online PowerShell 中的以下命令：
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

前面的命令通过启用该帐户来设置或创建新的 Exchange 资源邮箱帐户以使用 Skype 会议室系统。
  
创建邮箱后，可以在 Exchange Online PowerShell Set-CalendarProcessing cmdlet 配置邮箱。 有关更多详细信息，请参阅单林本地部署下的步骤 3 到步骤 6

## <a name="assigning-a-skype-for-business-online-license"></a>分配 Skype for Business Online 许可证

现在，可以使用 Microsoft 365 管理门户分配 Skype for Business Online (计划 2) 或 Skype for Business Online (计划 3) 许可证，如分配或删除 [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) 商业版许可证或 [Skype for Business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)附加许可中所述。 
  
为 Skype for Business Online 分配许可证后，你将能够登录并验证该帐户是否在任何 Skype for Business 客户端上处于活动状态。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online 预配

按照前面所示创建和启用资源会议室邮箱帐户，并且你已许可 Skype For Business Online 帐户后，该帐户将通过使用 Windows Azure Active Directory 林从 Exchange Online 林同步到 Skype for Business Online 林。 若要在 Skype for Business Online 池中设置 Skype 会议室系统帐户，需要执行以下步骤。 对于现有资源邮箱帐户或新创建的帐户 (confrm1 或 confrm2) ，这些步骤是相同的，因为在 Exchange Online 中启用这些步骤后，这两个帐户都将以相同方式同步到 Skype for Business Online：
  
1. 创建远程 PowerShell 会话。 请注意，你将需要下载 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. 若要为 Skype for Business 启用 Skype 会议室系统帐户，请运行以下命令：
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    可以通过以下命令返回此属性，从你的现有帐户之一获取你的 Skype for Business 用户所拥有注册器池地址：
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Skype 会议室系统 (MFA) 不支持多重身份验证。 

## <a name="password-expiration"></a>密码有效期

在 Microsoft 365 或 Office 365 中，除非配置不同的密码过期策略，否则所有用户帐户的默认密码过期策略为 90 天。 对于 Skype 会议室系统帐户，可以通过以下步骤选择"密码永不过期"设置。
  
1. 使用Windows Azure全局管理员凭据创建 Active Directory 会话。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 使用以下命令为以前创建的 Skype 会议室系统会议室帐户设置"密码永不过期"设置：
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

有关详细信息，请参阅为[计算机设置Windows PowerShell。](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  
## <a name="validate"></a>验证

为了进行验证，你应该能够使用任意 Skype for Business 客户端登录到你创建的帐户。

