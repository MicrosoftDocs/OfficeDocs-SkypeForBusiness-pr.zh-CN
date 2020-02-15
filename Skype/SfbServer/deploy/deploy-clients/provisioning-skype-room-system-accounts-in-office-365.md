---
title: 在 Office 365 中预配 Skype 会议室系统帐户
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
ms.openlocfilehash: 141c833bcbdd744a7577c0762cb8ba55dd3d5c54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037722"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>在 Office 365 中预配 Skype 会议室系统帐户
 
阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
  
以下部分介绍了 Office 365 租户的 Skype 会议室系统帐户设置。
  
## <a name="office-365-prerequisites"></a>Office 365 先决条件

您的联机租户必须满足以下要求：
  
- Office 365 计划必须包括 Skype for Business Online 计划2或 Office 365 E1、E3 或 E5。 <br/>有关 Skype for business Online 计划的详细信息，请参阅[skype For Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。
    
- 你的租户必须启用 Skype for Business 的会议功能。
    
- 你的租户必须启用了 Exchange Online。 
    
- 您的租户远程管理员必须具有以下 PowerShell 访问权限：
    
  - Exchange 远程 PowerShell 访问
    
  - Skype for Business Online 远程 PowerShell 访问
    
  - 用于 Windows PowerShell 的 windows Azure Active Directory 模块以访问 Office 365 目录访问
    
对于 Skype 会议室帐户，需要以下许可：
  
- 启用 Skype 会议需要 Skype for Business Online 计划2或 Office 365 E1 或 E3 许可证。
    
- 若要使用企业语音功能为会议室 entitle，以便可以使用电话号码启用会议室，则需要具有电话系统许可证或 Office 365 E5 的 Skype for Business Online 计划2（1）。
    
- 如果需要来自会议的电话拨入功能，则需要音频会议和电话系统许可证。  如果需要来自会议的拨出功能，则需要国内或国内和国际通话套餐。 
    
- Skype 会议室帐户不需要 Exchange Online 许可证，因为应将该帐户配置为资源邮箱帐户。
    
## <a name="provisioning-overview"></a>预配概述

下图概述了 Office 365 中的 Skype 会议室系统帐户预配流。
  
![O365 的 Skype 会议室系统预配步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>标识新的会议室

您可能已经在 Exchange 中有一个资源室邮箱提供了计划功能，或者您可能第一次创建了资源邮箱以促进 Skype 会议室系统部署。 在任何情况下，都必须标识要在租户中使用的会议室帐户。 Exchange Online 设置和 Skype for Business 设置部分提供了这两种帐户的指南。 例如，假设你有以下两个聊天室，并且想要为这两个聊天室部署 Skype 会议室系统：
  
- 现有资源邮箱帐户： confrm1@contoso.onmicrosoft.com
    
- 新资源邮箱帐户： confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 设置

首先，按照主题 "[连接到 Exchange Online powershell](https://go.microsoft.com/fwlink/p/?LinkId=396554)" 中的说明操作，连接到 Exchange online powershell。
  
若要为 Skype 会议室系统设置现有的资源室邮箱帐户，请在 Exchange Online PowerShell 中运行以下命令：
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

若要为 Skype 会议室系统创建新的 Exchange 资源邮箱帐户，请在 Exchange Online PowerShell 中运行以下命令：
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

通过启用此帐户，以前的命令为 Skype 会议室系统的使用设置或创建新的 Exchange 资源邮箱帐户。
  
创建邮箱后，您可以使用 Exchange Online PowerShell 中的 Set-calendarprocessing cmdlet 来配置邮箱。 有关更多详细信息，请参阅单林本地部署下的步骤3至6

## <a name="assigning-a-skype-for-business-online-license"></a>分配 Skype for Business Online 许可证

现在，您可以使用 Office 365 管理门户（如在 Office 365 for business 或[Skype For business 附加许可](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)中[分配或删除许可证](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)中所述），分配 skype For business online （计划2）或 skype For business online （计划3）许可证。 
  
为 Skype for business Online 分配许可证后，你将能够使用任何 Skype for business 客户端登录并验证帐户是否处于活动状态。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online 设置

在创建并按之前显示的那样启用了 resource 会议室邮箱帐户之后，并且已为 Skype For business Online 授权帐户，该帐户将使用从 Exchange Online 林同步到 Skype for business Online 林，具体方法是使用Windows Azure Active Directory 林。 若要在 Skype for business Online 池中预配 Skype 会议室系统帐户，需要执行以下步骤。 对于现有资源邮箱帐户或新创建的帐户（confrm1 或 confrm2），这些步骤都相同，因为它们在 Exchange Online 中启用后，这两个帐户将以相同的方式同步到 Skype for business Online：
  
1. 创建远程 PowerShell 会话。 请注意，你将需要下载 Skype for Business Online 连接器模块和 Microsoft Online Services 登录助手，并确保已配置你的计算机。 有关详细信息，请参阅[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. 若要为 Skype for business 启用 Skype 会议室系统帐户，请运行以下命令：
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    您可以通过使用以下命令返回此属性，获取您的 Skype for business 用户驻留在现有帐户之一中的 RegistrarPool 地址：
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Skype 会议室系统帐户不支持多重身份验证（MFA）。 

## <a name="password-expiration"></a>密码有效期

在 Office 365 中，除非您配置不同的密码过期策略，否则所有用户帐户的默认密码过期策略都是90天。 对于 Skype 会议室系统帐户，你可以使用以下步骤选择 "密码永不过期" 设置。
  
1. 使用租户全局管理员凭据创建 Windows Azure Active Directory 会话。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 为先前使用以下命令创建的 Skype 会议室系统室帐户设置 "密码永不过期" 设置：
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

有关详细信息，请参阅[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  
## <a name="validate"></a>验证

若要进行验证，你应该能够使用任何 Skype for Business 客户端登录到你创建的帐户。

