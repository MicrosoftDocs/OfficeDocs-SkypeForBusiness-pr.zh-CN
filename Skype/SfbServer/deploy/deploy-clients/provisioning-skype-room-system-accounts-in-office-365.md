---
title: 在 Office 365 中设置 Skype 会议室系统帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
ms.openlocfilehash: a1b24e25236f221d280631efd83c0e83b7ae44f2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219472"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>在 Office 365 中设置 Skype 会议室系统帐户
 
阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
  
以下各节介绍设置 Office 365 租户的 Skype 会议室系统帐户。
  
## <a name="office-365-prerequisites"></a>Office 365 先决条件

你的联机租户必须满足以下要求：
  
- Office 365 计划必须包括 Skype 业务 Online 计划 2，或 Office 365 E1、 E3 或 E5。 <br/>Skype 的业务 Online 计划的详细信息，请参阅[Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。
    
- Skype for Business 启用会议功能，必须拥有您的租户。
    
- 你的租户必须启用 Exchange Online。 
    
- 你的租户远程管理员必须具有以下 PowerShell 访问：
    
  - Exchange 远程 PowerShell 访问
    
  - Skype 业务 Online Remote PowerShell 访问
    
  - Windows Azure Active Directory 模块用于 Windows PowerShell 访问 Office 365 目录访问
    
对于 Skype 会议室帐户，需要以下许可：
  
- 启用 Skype 会议需要 Skype 业务 Online 计划 2 或 Office 365 E1 或 E3 许可证。
    
- 以允许与企业语音功能的聊天室，以便可以与一个电话号码启用会议室，业务 Online 计划 2 的电话系统许可证或 Office 365 E5 Skype 是需要 (1)。
    
- 如果您需要电话拨入式会议的功能，您将需要的音频会议和电话系统许可证。  如果您需要从会议拨出功能，您将需要国内或国内和国际呼叫规划。 
    
- Skype 会议室帐户不需要 Exchange Online 许可证，因为应将该帐户配置为资源邮箱帐户。
    
## <a name="provisioning-overview"></a>设置概述

下图概述了设置 Office 365 中的流的 Skype 会议室系统帐户。
  
![O365 的 Skype 会议室系统设置步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>识别新的会议室

您可能已经资源会议室邮箱在 Exchange 提供计划功能，或您可能会创建第一次为了方便 Skype 会议室系统部署的资源邮箱。 在任何情况下，你必须识别要在你的租户中使用的会议室帐户。 Exchange Online 设置和 Skype 业务设置部分提供的这两种帐户的指导。 例如，假设您具有以下两个聊天室，并且您希望为这两个部署 Skype 会议室系统：
  
- 现有资源邮箱帐户：confrm1@contoso.onmicrosoft.com
    
- 新的资源邮箱帐户：confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 设置

首先，连接到 Exchange Online PowerShell 中的主题，[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)中的说明。
  
若要设置 Skype 会议室系统现有资源会议室邮箱帐户，请在 Exchange Online PowerShell 中运行以下命令：
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

要为 Skype 会议室系统中创建新的 Exchange 资源邮箱帐户，请在 Exchange Online PowerShell 中运行以下命令：
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

上面的命令设置，或通过启用的帐户创建新 Exchange 资源邮箱帐户 Skype 会议室系统使用情况。
  
创建邮箱之后, 可用于 Exchange Online PowerShell 中的 Set-calendarprocessing cmdlet 配置邮箱。 有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。

## <a name="assigning-a-skype-for-business-online-license"></a>分配 Skype for Business Online 许可证

现在您可以分配 Skype 业务 Online (计划 2) 或 Skype 业务 Online (计划 3) 许可证[分配](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)或删除业务的 Office 365 的许可证或[Skype 对业务的加载项中所述使用 Office 365 管理门户许可](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。 
  
分配许可证的 Skype 业务 online 后，您将能够登录并验证该帐户是活动的业务客户端使用任何 Skype。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online 设置

和之后资源会议室邮箱帐户已创建并启用前面所示的 Skype 的业务 Online 帐户将同步从 Exchange Online 林中到 Skype 的业务联机林使用，您具有许可帐户Windows Azure Active Directory 林。 以下步骤所需设置中为业务联机池 Skype 的 Skype 会议室系统帐户。 这些步骤是相同的现有资源邮箱帐户或新创建的帐户 （confrm1 或 confrm2），因为后启用它们在 Exchange Online，这两个这些帐户将同步到 Skype 业务 online 相同的方式：
  
1. 创建远程 PowerShell 会话。 请注意，您将需要下载 Skype 业务 Online 连接器模块和 Microsoft Online Services 登录助手，并确保您的计算机配置。 有关详细信息，请参阅[Windows PowerShell 将计算机设置](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. 若要启用 for Business 的 Skype Skype 会议室系统帐户，运行以下命令：
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    您可以获取的 RegistrarPool 地址其中业务用户您 Skype 位于从您的现有帐户之一使用以下命令以返回该属性：
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>密码过期

在 Office 365 中，所有用户帐户的默认密码过期策略是 90 天，除非你配置不同的密码过期策略。 对于 Skype 会议室系统帐户时，您可以选择密码永不过期设置以下步骤。
  
1. 使用你的租户全局管理员凭据创建 Windows Azure Active Directory 会话。
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 设置密码永不过期之前使用以下命令创建的 Skype 会议室系统会议室帐户的设置：
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

有关详细信息，请参阅[Windows PowerShell 将计算机设置](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  
## <a name="validate"></a>验证

进行验证，您应该能够使用任何 Skype 业务客户端登录到您创建的帐户。

