---
title: 管理 Skype 中的业务服务器的双重身份验证
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 摘要： 管理 Skype 中的业务服务器的双重身份验证。
ms.openlocfilehash: a9ebeaa5f8f012d66fb62357e8378010d0a74865
ms.sourcegitcommit: 6251a2c659909c3972ca2ea0a2bcdab4f334df34
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2018
ms.locfileid: "25692738"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>管理 Skype 中的业务服务器的双重身份验证
 
**摘要：** 管理业务服务器中 Skype 双重身份验证。
  
双重身份验证要求用户提供两种形式的身份验证或身份识别，即用户名/密码组合以及令牌或证书，从而提供了更高的安全性。 这是也称为"的内容，您知道。" 
  
使用证书进行双重身份验证的一个典型示例是使用智能卡。智能卡包含与用户帐户相关联的证书，可对照服务器上存储的用户和证书信息进行验证。通过将用户信息（用户名和密码）与提供的证书进行比较，服务器将验证凭据并验证用户身份。
  
配置业务服务器环境的 Skype 以支持双重身份验证时，请考虑以下主题。
  
## <a name="client-support"></a>客户端支持

Lync Server 2013 累积更新： 2013 年 7 月桌面客户端和业务客户端 Skype 是当前支持双重身份验证的唯一客户端。
  
## <a name="topology-requirements"></a>拓扑要求

强烈建议，部署使用专用的 Skype 业务服务器边缘、 控制器和用户池的双重身份验证的客户。 要为用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：
  
|**配置类型**|**服务类型**|**服务器角色**|**要禁用的身份验证类型**|
|:-----|:-----|:-----|:-----|
|Web 服务  <br/> |Web 服务器  <br/> |控制器  <br/> |Kerberos、NTLM 和证书  <br/> |
|Web 服务  <br/> |Web 服务器  <br/> |前端  <br/> |Kerberos、NTLM 和证书  <br/> |
|代理  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos 和 NTLM  <br/> |
|代理  <br/> |注册器  <br/> |前端  <br/> |Kerberos 和 NTLM  <br/> |
   
除非在服务级别禁用这些身份验证类型，否则一旦在您的部署中启用双重身份验证，所有其他版本的客户端将无法成功登录。
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business 服务发现

应配置内部和/或外部的客户端用于发现 Skype 业务服务的 DNS 记录，解析为未启用的双重身份验证的企业服务器 Skype。 使用此配置，Skype 未启用双重身份验证的业务池的用户将不需要输入 PIN 进行身份验证，将为用户启用了双重身份验证的业务池的 Skype 时要求输入 PIN，以便进行身份验证。
  
## <a name="exchange-authentication"></a>Exchange 身份验证

客户部署了 Microsoft Exchange 的双重身份验证可能会发现在客户端中的某些功能将不可用。 这是当前按照设计，如业务客户端 Skype 取决于 Exchange 集成的功能不支持双重身份验证。
  
## <a name="contacts"></a>联系人

Skype 的业务用户的配置，以便利用统一联系人存储功能会发现的联系人不再可用后登录时双重身份验证。
  
应使用**Invoke-csucsrollback** cmdlet 从统一联系人存储库中删除现有的用户联系人并将其存储在 Skype 业务服务器启用双重身份验证之前。
  
## <a name="skill-search"></a>技能搜索

在其 Skype 业务环境中配置的技能搜索功能的客户将发现 for Business 的 Skype 启用双重身份验证时，此功能不工作。 这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。
  
## <a name="credentials"></a>凭据

有大量涉及的业务凭据，这可能会影响配置为使用双重身份验证的用户的已保存的 Skype 的部署注意事项。
  
### <a name="deleting-saved-credentials"></a>删除保存的凭据

用户应使用**删除我登录信息**选项中 Skype for Business 客户端并删除其 SIP 配置文件文件夹从 %localappdata%\Microsoft\Office\15.0\Skype for Business 尝试使用双重首次登录之前身份验证。
  
### <a name="disablentcredentials"></a>DisableNTCredentials

采用 Kerberos 或 NTLM 身份验证方法时，身份验证可以自动使用用户的 Windows 凭据。 在启用了 Kerberos 和/或 NTLM 是身份验证的企业服务器部署典型 Skype，用户不必输入其凭据登录每次。
  
如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。
  
若要防止额外提示输入凭据，在本地工作站上创建以下注册表项，或者使用业务管理模板 Skype 于给定池使用组策略的所有用户：
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

当用户登录到 for Business 的 Skype 第一次时，提示用户保存他/她的密码。 如果选中，则此选项允许用户的客户端证书存储中的个人证书存储和用户的 Windows 凭据存储在凭据管理器中的本地计算机。
  
当 for Business 的 Skype 配置为支持双重身份验证时，应禁用**SavePassword**注册表设置。 若要禁止用户保存其密码，更改本地工作站上的以下注册表项或使用业务管理模板 Skype 于给定池使用组策略的所有用户：
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 令牌重播

AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。
  
在高度关注安全的环境（例如使用展台时）中，应启用此功能。 有关令牌重播检测的详细信息，请参阅 [AD FS 2.0 安全规划和部署的最佳做法](https://go.microsoft.com/fwlink/p/?LinkId=309215)。
  
## <a name="external-user-access"></a>外部用户访问

这些主题中没有介绍配置 ADFS 代理或反向代理以从外部网络业务双重身份验证支持 Skype。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中配置双重身份验证](configure-two-factor.md)
  