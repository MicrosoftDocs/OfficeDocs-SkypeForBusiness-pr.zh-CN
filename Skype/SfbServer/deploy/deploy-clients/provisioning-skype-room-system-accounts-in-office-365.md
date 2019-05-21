---
title: 在 Office 365 中设置 Skype 会议室系统帐户
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
ms.openlocfilehash: 87643d04879888d59739c997e37108c6c7403101
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301538"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>在 Office 365 中设置 Skype 会议室系统帐户
 
阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
  
以下部分介绍 Office 365 租户的 Skype 会议室系统帐户预配。
  
## <a name="office-365-prerequisites"></a>Office 365 先决条件

你的联机租户必须满足以下要求：
  
- Office 365 计划必须包括 Skype for Business Online 计划2或 Office 365 E1、E3 或 E5。 <br/>有关 Skype for Business Online 计划的详细信息, 请参阅[skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。
    
- 你的租户必须具有启用 Skype for Business 的会议功能。
    
- 你的租户必须启用 Exchange Online。 
    
- 你的租户远程管理员必须具有以下 PowerShell 访问：
    
  - Exchange 远程 PowerShell 访问
    
  - Skype for Business Online 远程 PowerShell 访问
    
  - 用于 Windows PowerShell 的 windows Azure Active Directory 模块以访问 Office 365 目录访问
    
对于 Skype 会议室帐户，需要以下许可：
  
- 要启用 Skype 会议, 需要有 Skype for Business Online 计划2或 Office 365 E1 或 E3 许可证。
    
- 若要使用企业语音功能 entitle 房间, 以便可以使用电话号码启用会议室, 需要具有电话系统许可证或 Office 365 E5 的 Skype for business Online 计划 2 (1)。
    
- 如果需要来自会议的电话拨入式功能, 您需要音频会议和电话系统许可证。  如果需要来自会议的拨出功能, 您将需要国内或国内和国际通话计划。 
    
- Skype 会议室帐户不需要 Exchange Online 许可证，因为应将该帐户配置为资源邮箱帐户。
    
## <a name="provisioning-overview"></a>设置概述

下图概括介绍了 Office 365 中的 Skype 会议室系统帐户预配流。
  
![O365 的 Skype 会议室系统设置步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>识别新的会议室

您可能在 Exchange 中已经有一个资源室邮箱可提供日程安排功能, 或者你可能是第一次创建资源邮箱来促进 Skype 会议室系统部署。 在任何情况下，你必须识别要在你的租户中使用的会议室帐户。 Exchange Online 设置和 Skype for business 预配部分提供两种类型的帐户的指南。 例如, 假设你有以下两个会议室, 并且想要为两个会议室部署 Skype 会议室系统:
  
- 现有资源邮箱帐户：confrm1@contoso.onmicrosoft.com
    
- 新的资源邮箱帐户：confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 设置

首先, 按照主题中的 "[连接到 Exchange Online powershell](https://go.microsoft.com/fwlink/p/?LinkId=396554)" 中的说明连接到 Exchange online powershell。
  
若要为 Skype 会议室系统设置现有的资源室邮箱帐户, 请在 Exchange Online PowerShell 中运行以下命令:
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

若要为 Skype 会议室系统创建新的 Exchange 资源邮箱帐户, 请在 Exchange Online PowerShell 中运行以下命令:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

通过启用帐户, 以前的命令为 Skype 会议室系统使用设置或创建新的 Exchange 资源邮箱帐户。
  
创建邮箱后, 您可以使用 Exchange Online PowerShell 中的 CalendarProcessing cmdlet 配置邮箱。 有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。

## <a name="assigning-a-skype-for-business-online-license"></a>分配 Skype for Business Online 许可证

现在, 你可以使用 Office 365 管理门户分配 Skype for business Online (计划 2) 或 Skype for business Online (计划 3) 许可证, 如[分配或删除 office 365 for](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) Business 或[Skype for business 加载项的许可证中所述许可](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。 
  
为 Skype for business Online 分配许可证后, 你将能够登录并使用任何 Skype for Business 客户端验证帐户是否处于活动状态。
  
## <a name="skype-for-business-online-provisioning"></a>Skype for Business Online 设置

在创建并启用资源室邮箱帐户之前 (如上所示), 并且已授权 Skype For Business Online 帐户时, 该帐户将从 Exchange Online 林同步到 Skype for business Online 林, 方法是使用Windows Azure Active Directory 林。 在 Skype for business Online 池中预配 Skype 会议室系统帐户需要执行以下步骤。 对于现有资源邮箱帐户或新创建的帐户 (confrm1 或 confrm2), 这些步骤是相同的, 因为在 Exchange Online 中启用这些帐户后, 这两个帐户将以同样的方式同步到 Skype for Business Online:
  
1. 创建远程 PowerShell 会话。 请注意, 你将需要下载 Skype for Business Online 连接器模块和 Microsoft Online Services 登录助手, 并确保你的计算机已配置。 有关详细信息, 请参阅[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. 若要为 Skype for business 启用 Skype 会议室系统帐户, 请运行以下命令:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    你可以使用以下命令返回此属性, 获取你的 Skype for Business 用户从现有帐户之一驻留的 RegistrarPool 地址:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>密码过期

在 Office 365 中，所有用户帐户的默认密码过期策略是 90 天，除非你配置不同的密码过期策略。 对于 Skype 会议室系统帐户, 您可以通过以下步骤选择 "密码永不过期" 设置。
  
1. 使用你的租户全局管理员凭据创建 Windows Azure Active Directory 会话。
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 为以前使用以下命令创建的 Skype 聊天室系统帐户设置密码永不过期设置:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

有关详细信息, 请参阅[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  
## <a name="validate"></a>复核

对于验证, 你应该能够使用任何 Skype for Business 客户端登录到你创建的帐户。

