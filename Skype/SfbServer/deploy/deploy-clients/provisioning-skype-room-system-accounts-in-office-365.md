---
title: 在Skype和Microsoft 365中预配Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在Skype或Microsoft 365会议室Office 365。
ms.openlocfilehash: 77416d34c3b478f0013cf41c63dcebd52e52f3ce
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853766"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>在Skype和Microsoft 365中预配Office 365
 
阅读本主题，了解如何在Skype或Microsoft 365会议室Office 365。
  
以下部分介绍了Skype系统帐户预配。
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365和Office 365先决条件

联机租户必须满足以下要求：
  
- 计划Microsoft 365或Office 365必须包括 Skype for Business Online 计划 2、Office 365 E1、E3 或 E5。 <br/>有关 Skype for Business Online 计划的详细信息，请参阅[Skype for Business Online 服务说明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。
    
- 租户必须启用会议Skype for Business功能。
    
- 租户必须已启用Exchange Online。 
    
- 租户远程管理员必须具有以下 PowerShell 访问权限：
    
  - Exchange远程 PowerShell 访问
    
  - Skype for Business联机远程 PowerShell 访问
    
  - Windows Azure Active Directory模块Windows PowerShell访问Microsoft 365或Office 365访问
    
对于 Skype 会议室帐户，需要以下许可：
  
- 需要Skype for Business Online 计划 2 或 Office 365 E1 或 E3 许可证才能启用Skype会议。
    
- 若要使会议室具有 企业语音 功能，以便可以使用电话号码启用会议室，需要具有 电话系统 许可证或 Office 365 E5 的 Skype for Business Online 计划 2 (1) 。
    
- 如果需要会议拨入功能，则需要音频会议和电话系统许可证。  如果你需要会议拨出功能，你将需要国内或国内和国际通话套餐。 
    
- Exchange Online会议室帐户不需要Skype许可证，因为该帐户应配置为资源邮箱帐户。
    
## <a name="provisioning-overview"></a>预配概述

下图概述了会议室系统Skype设置流。
  
![Skype会议室系统预配步骤。](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>确定新的会议室

您可能已在提供计划功能Exchange资源会议室邮箱，或者您可能第一次创建资源邮箱以促进Skype部署。 在任何情况下，都必须标识要用于租户的会议室帐户。 "Exchange Online预配Skype for Business预配"部分提供了这两种帐户的指南。 例如，假设你拥有以下两个会议室，并且你要为这两Skype会议室系统部署一个会议室系统：
  
- 现有资源邮箱帐户：confrm1@contoso.onmicrosoft.com
    
- 新建资源邮箱帐户：confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online预配

首先，按照Exchange Online PowerShell 中的说明连接到 连接 PowerShell Exchange Online [PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)
  
若要为会议室系统设置现有资源会议室邮箱Skype，请运行 PowerShell 中的以下Exchange Online命令：
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

若要为会议室系统Exchange资源邮箱帐户Skype，请运行 PowerShell 中的以下Exchange Online命令：
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

前面的命令通过启用帐户Exchange设置或创建新的会议室Skype邮箱帐户。
  
创建邮箱后，可以在 PowerShell Set-CalendarProcessing cmdlet Exchange Online配置邮箱。 有关更多详细信息，请参阅单林本地部署下的步骤 3 至 6

## <a name="assigning-a-skype-for-business-online-license"></a>分配 Skype for Business Online 许可证

现在，可以使用 Microsoft 365 管理门户分配 Skype for Business Online (计划 2) 或 Skype for Business Online (计划 3) 许可证，如为[Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)企业版或[Skype for Business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)附加许可分配或删除许可证中所述。 
  
为 Skype for Business Online 分配许可证后，您将能够使用任意客户端登录并验证该帐户Skype for Business活动。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business联机预配

按照前面所示创建并启用资源会议室邮箱帐户，并且你已许可 Skype For Business Online 的帐户后，该帐户将通过使用 Windows Azure Active Directory 林从 Exchange Online 林同步到 Skype for Business Online 林。 若要在联机池中设置Skype会议室系统帐户，需要Skype for Business步骤。 对于现有资源邮箱帐户或新创建的帐户 (confrm1 或 confrm2) ，这些步骤是相同的，因为在 Exchange Online 中启用后，这两个帐户将按照相同的方式同步到 Skype for Business Online：
  
1. 创建远程 PowerShell 会话。 请注意，你将需要下载Teams [PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. 若要为Skype会议室系统帐户Skype for Business，请运行以下命令：
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    可以使用以下命令返回此属性，获取 Skype for Business用户从现有帐户之一的 RegistrarPool 地址：
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>会议室系统 (不支持) 多重身份验证Skype MFA 身份验证。 

## <a name="password-expiration"></a>密码有效期

在 Microsoft 365 或 Office 365 中，除非您配置了不同的密码过期策略，否则所有用户帐户的默认密码过期策略为 90 天。 对于Skype系统帐户，可以通过以下步骤选择"密码永不过期"设置。
  
1. 使用Windows Azure Active Directory全局管理员凭据创建一个安全会话。
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 使用下列命令为以前创建的会议室Skype帐户设置"密码永不过期"设置：
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

有关详细信息，请参阅为[计算机设置Windows PowerShell。](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="validate"></a>验证

为了进行验证，您应该能够使用任意 Skype for Business 客户端登录您创建的帐户。