---
title: 管理 Skype for Business Server 2015 中的双重身份验证
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 摘要： 管理在 Skype 的业务服务器 2015年的双因素身份验证。
ms.openlocfilehash: 5933afc311514e841d7fb96f41988d8f495d0bee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server-2015"></a>管理 Skype for Business Server 2015 中的双重身份验证
 
**摘要：**管理在 Skype 的业务服务器 2015年的双因素身份验证。
  
双重身份验证要求用户提供两种形式的身份验证或身份识别，即用户名/密码组合以及令牌或证书，从而提供了更高的安全性。 这正是所谓"，您知道的某种信息。" 
  
使用证书进行双重身份验证的一个典型示例是使用智能卡。智能卡包含与用户帐户相关联的证书，可对照服务器上存储的用户和证书信息进行验证。通过将用户信息（用户名和密码）与提供的证书进行比较，服务器将验证凭据并验证用户身份。
  
配置业务服务器 2015年环境 Skype 来支持两因素身份验证时，应考虑以下主题。
  
## <a name="client-support"></a>客户端支持

Lync Server 2013 累积更新： 2013 年 7 月的桌面客户端和 Skype 业务客户机是目前支持两因素身份验证的唯一客户端。
  
## <a name="topology-requirements"></a>拓扑要求

强烈建议使用专用的 Skype 业务服务器 2015年的边缘、 部门主任和用户池的双因子验证部署的客户。 要为用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：
  
|**配置类型**|**服务类型**|**服务器角色**|**身份验证类型设置为禁用**|
|:-----|:-----|:-----|:-----|
|Web 服务  <br/> |Web 服务器  <br/> |控制器  <br/> |Kerberos、NTLM 和证书  <br/> |
|Web 服务  <br/> |Web 服务器  <br/> |前端  <br/> |Kerberos、NTLM 和证书  <br/> |
|代理  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos 和 NTLM  <br/> |
|代理  <br/> |注册器  <br/> |前端  <br/> |Kerberos 和 NTLM  <br/> |
   
除非在服务级别禁用这些身份验证类型，否则一旦在您的部署中启用双重身份验证，所有其他版本的客户端将无法成功登录。
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business 服务发现

应该配置 DNS 记录内部和/或外部客户端用来发现 Skype 业务服务解析为 Skype 业务服务器未启用双因素身份验证。 使用此配置，Skype 业务池未启用双因素身份验证的用户不需要输入 pin 码以进行身份验证，而 Skype 业务池启用的双因素身份验证的用户将成为要求输入他们的 PIN 进行身份验证。
  
## <a name="exchange-authentication"></a>Exchange 身份验证

已部署 Microsoft Exchange 的双因素身份验证的用户可能会发现客户端中的某些功能将不可用。 这是当前设计中，通过 Skype 业务客户端不支持双因素身份验证依赖于交换集成的功能。
  
## <a name="contacts"></a>联系人

配置以利用统一联系人存储功能的业务用户的 Skype 会发现其联系人不再可用后登录两因素身份验证。
  
您应该使用**调用 CsUcsRollback** cmdlet 从统一联系人存储库中删除现有用户的联系人并将其存储在 Skype 的业务服务器 2015年启用双因素身份验证之前。
  
## <a name="skill-search"></a>技能搜索

客户在其 Skype 的业务环境中配置了技能搜索功能将 Skype 业务两因素身份验证为启用时，此功能不能发现。 这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。
  
## <a name="credentials"></a>凭据

有大量涉及业务可能影响配置为使用双因素身份验证的用户的凭据保存的 Skype 的部署注意事项。
  
### <a name="deleting-saved-credentials"></a>删除保存的凭据

用户应该用于企业客户端**删除我的登录信息**选项在 Skype 和删除其 SIP 配置文件文件夹从 %localappdata%\Microsoft\Office\15.0\Skype 业务为使用双因素在第一次登录前身份验证。
  
### <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 身份验证方法，身份验证可以自动使用用户的 Windows 凭据。 在启用了 Kerberos 和/或 NTLM 是用于身份验证的业务服务器 2015年部署典型 Skype，用户应该不需要输入其凭据登录每次。
  
如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。
  
若要防止其他提示输入凭据，在本地工作站上创建下面的注册表项或使用 Skype 业务管理模板将应用于所有用户的使用组策略指定的池：
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

当用户登录 Skype 业务的第一次时，提示用户要保存他或她的密码。 如果选中此项，此选项将允许用户的 Windows 凭据存储在凭据管理器中的本地计算机的个人证书存储区中存储的用户的客户端证书。
  
在 Skype 业务配置为支持双因素身份验证时，应禁用**SavePassword**注册表设置。 若要禁止用户保存他们的密码，更改下面的注册表项在本地工作站上或使用 Skype 业务管理模板将应用于所有用户的使用组策略指定的池：
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 令牌重播

AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。
  
在高度关注安全的环境（例如使用展台时）中，应启用此功能。 有关标记重做检测的详细信息，请参阅[安全规划和 AD FS 2.0 部署的最佳做法](https://go.microsoft.com/fwlink/p/?LinkId=309215)。
  
## <a name="external-user-access"></a>外部用户访问

这些主题不介绍配置为从外部网络业务双因素身份验证支持 Skype ADFS 代理或反向代理服务器。
  
## <a name="see-also"></a>另请参阅

#### 

[在 Skype 为业务服务器 2015年配置两因素身份验证](configure.md)
  
[在 Skype 为业务服务器 2015年配置两因素身份验证](configure.md)

