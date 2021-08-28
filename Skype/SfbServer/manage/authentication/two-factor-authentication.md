---
title: 在客户端中管理双重Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 摘要：在 Skype for Business Server 中管理双重Skype for Business Server。
ms.openlocfilehash: 2b354c99b4e02536ff3db2043ec18fcd092d766e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621098"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>在客户端中管理双重Skype for Business Server
 
**摘要：** 在客户端中管理双重Skype for Business Server。
  
双重身份验证要求用户提供两种形式的身份验证或标识（即用户名/密码组合和令牌或证书）来提高安全性。 这也称为"你拥有的事情，你了解的一些内容"。 
  
使用证书进行双重身份验证的一个典型示例是使用智能卡。 智能卡包含与用户帐户关联的证书，可以针对服务器上存储的用户和证书信息进行验证。 通过将用户信息和用户名和密码 (与提供的证书) ，服务器将验证凭据并验证用户身份。
  
在配置支持双重身份验证的 Skype for Business Server环境时，请考虑以下主题。
  
## <a name="client-support"></a>客户端支持

Lync Server 2013 累积更新：2013 年 7 月桌面客户端和 Skype for Business 客户端是当前唯一支持双重身份验证的客户端。
  
## <a name="topology-requirements"></a>拓扑要求

建议客户通过边缘、控制器和用户池的专用Skype for Business Server部署双重身份验证。 若要为用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括：
  
|**配置类型**|**服务类型**|**服务器角色**|**要禁用的身份验证类型**|
|:-----|:-----|:-----|:-----|
|Web 服务  <br/> |WebServer  <br/> |主管  <br/> |Kerberos、NTLM 和证书  <br/> |
|Web 服务  <br/> |WebServer  <br/> |前端  <br/> |Kerberos、NTLM 和证书  <br/> |
|代理  <br/> |EdgeServer  <br/> |Microsoft Edge  <br/> |Kerberos 和 NTLM  <br/> |
|代理  <br/> |注册器  <br/> |前端  <br/> |Kerberos 和 NTLM  <br/> |
   
除非在服务级别禁用这些身份验证类型，否则在部署中启用双重身份验证后，所有其他版本的客户端将无法成功登录。
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business服务发现

内部和/或外部客户端用于发现 Skype for Business 服务的 DNS 记录应配置为解析为未启用双重身份验证的 Skype for Business 服务器。 通过此配置，Skype for Business 池中未启用双重身份验证的用户无需输入 PIN 进行身份验证，而 Skype for Business 池中启用了双重身份验证的用户需要输入其 PIN 进行身份验证。
  
## <a name="exchange-authentication"></a>Exchange身份验证

为 Microsoft 部署双重身份验证Exchange可能会发现客户端中的某些功能不可用。 此行为是设计使Skype for Business，因为客户端不支持对依赖于集成功能的功能进行双重Exchange身份验证。
  
## <a name="contacts"></a>联系人

Skype for Business统一联系人存储功能的用户将在使用双重身份验证登录后发现其联系人不再可用。
  
在启用双重身份验证之前，应该使用 **Invoke-CsUcsRollback** cmdlet 从统一联系人存储中删除现有用户联系人，并存储在 Skype for Business Server 中。
  
## <a name="skill-search"></a>技能搜索

在用户环境中配置了技能搜索Skype for Business客户会发现，当启用双重Skype for Business时，此功能不起作用。 这是设计使SharePoint，因为 Microsoft SharePoint目前不支持双重身份验证。
  
## <a name="credentials"></a>凭据

有许多部署注意事项涉及已保存Skype for Business凭据，这可能会影响配置为使用双重身份验证的用户。
  
### <a name="deleting-saved-credentials"></a>删除保存的凭据

用户应先使用Skype for Business 客户端中的"删除我的登录信息"选项，然后从 %localappdata%\Microsoft\Office\15.0\Skype for Business 中删除其 SIP 配置文件文件夹，然后再尝试使用双重身份验证首次登录。
  
### <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 身份验证方法，将自动Windows用户凭据进行身份验证。 在启用了 kerberos Skype for Business Server/或 NTLM 进行身份验证的典型部署中，用户每次登录时都不应输入其凭据。
  
如果在提示用户输入 PIN 之前无意中提示用户输入凭据，则可能会无意中在客户端计算机上配置 **DisableNTCredentials** 注册表项，这可能是通过组策略配置的。
  
若要阻止额外提示输入凭据，请在本地工作站上创建以下注册表项或使用 Skype for Business 管理模板，以使用组策略应用于给定池的所有用户：
  
HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
REG_DWORD：DisableNTCredentials

值：0x0
  
### <a name="savepassword"></a>SavePassword

当用户首次Skype for Business登录时，系统会提示用户保存其密码。 如果选中此选项，则允许用户的客户端证书存储在个人证书存储中，并且用户的 Windows 凭据将存储在本地计算机的凭据管理器中。
  
将 SavePassword 注册表设置配置为支持双重身份验证Skype for Business应禁用 **SavePassword** 注册表设置。 若要防止用户保存其密码，请在本地工作站上更改以下注册表项或使用 Skype for Business 管理模板，以使用组策略应用于给定池的所有用户：
  
HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
REG_DWORD：SavePassword
  
值：0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 令牌重播

AD FS 2.0 提供了一种称为令牌重播检测的功能，通过该功能，可以检测并丢弃使用同一令牌的多个令牌请求。 启用此功能后，令牌重播检测通过确保从不多次使用同一令牌来保护 WS-Federation 被动配置文件和 SAML WebSSO 配置文件中的身份验证请求的完整性。
  
在高度关注安全性的情况下（例如使用展台时）应启用此功能。 有关令牌重播检测详细信息，请参阅[Best Practices for Secure Planning and Deployment of AD FS 2.0。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10))
  
## <a name="guest-user-access"></a>来宾用户访问

这些主题中未Skype for Business配置 ADFS 代理或反向代理以支持来自外部网络的双因素身份验证。
  
## <a name="see-also"></a>另请参阅

[在客户端中配置双重Skype for Business Server](configure-two-factor.md)
