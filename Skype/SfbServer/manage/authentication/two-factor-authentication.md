---
title: 在 Skype for Business 服务器中管理双因素身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 摘要：在 Skype for Business 服务器中管理双因素身份验证。
ms.openlocfilehash: 90dc286e247c0c6eeb75bb884071b85e57663278
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818714"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>在 Skype for Business 服务器中管理双因素身份验证
 
**摘要：** 在 Skype for Business 服务器中管理双因素身份验证。
  
双重身份验证要求用户提供两种形式的身份验证或身份识别，即用户名/密码组合以及令牌或证书，从而提供了更高的安全性。 这也称为 "你拥有的内容，你认识的内容"。 
  
使用证书进行双重身份验证的一个典型示例是使用智能卡。智能卡包含与用户帐户相关联的证书，可对照服务器上存储的用户和证书信息进行验证。通过将用户信息（用户名和密码）与提供的证书进行比较，服务器将验证凭据并验证用户身份。
  
配置 Skype for Business 服务器环境以支持双因素身份验证时，请考虑以下主题。
  
## <a name="client-support"></a>客户端支持

Lync Server 2013 的累积更新：7月2013桌面客户端和 Skype for Business 客户端是唯一支持双因素身份验证的客户端。
  
## <a name="topology-requirements"></a>拓扑要求

强烈建议客户使用专用的 Skype for Business 服务器（具有边缘、控制器和用户池）部署双因素身份验证。 要为用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：
  
|**配置类型**|**服务类型**|**服务器角色**|**要禁用的身份验证类型**|
|:-----|:-----|:-----|:-----|
|Web 服务  <br/> |Web 服务器  <br/> |控制器  <br/> |Kerberos、NTLM 和证书  <br/> |
|Web 服务  <br/> |Web 服务器  <br/> |前端  <br/> |Kerberos、NTLM 和证书  <br/> |
|代理  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos 和 NTLM  <br/> |
|代理  <br/> |注册器  <br/> |前端  <br/> |Kerberos 和 NTLM  <br/> |
   
除非在服务级别禁用这些身份验证类型，否则一旦在您的部署中启用双重身份验证，所有其他版本的客户端将无法成功登录。
  
## <a name="skype-for-business-service-discovery"></a>Skype for Business 服务发现

内部和/或外部客户端用于发现 Skype for Business 服务的 DNS 记录应配置为解析为未启用双因素身份验证的 Skype for business 服务器。 通过此配置，没有为两个因素身份验证启用的 Skype for business 池中的用户输入 PIN 进行身份验证时，将不需要输入 PIN 来进行身份验证，而启用了双因素身份验证的 Skype for business 池中的用户将需要输入其 PIN 才能进行身份验证。
  
## <a name="exchange-authentication"></a>Exchange 身份验证

已为 Microsoft Exchange 部署了双因素身份验证的客户可能会发现客户端中的某些功能不可用。 这是当前设计的，因为 Skype for Business 客户端不支持依赖于 Exchange 集成的功能的双因素身份验证。
  
## <a name="contacts"></a>联系人

配置为利用 "统一联系人存储" 功能的 Skype for business 用户将发现，使用双因素身份验证登录后，他们的联系人将不再可用。
  
你应该使用**CsUcsRollback** cmdlet 从 "统一联系人存储" 中删除现有用户联系人，并将其存储在 Skype For business 服务器中，然后再启用双重身份验证。
  
## <a name="skill-search"></a>技能搜索

在 Skype for business 环境中配置技能搜索功能的客户将发现，当启用了双因素身份验证的 Skype for business 时，此功能不起作用。 这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。
  
## <a name="credentials"></a>凭据

有许多部署注意事项涉及保存的 Skype for Business 凭据，这可能会影响配置为使用双因素身份验证的用户。
  
### <a name="deleting-saved-credentials"></a>删除保存的凭据

用户应在 Skype for Business 客户端中使用 "**删除我的登录信息**" 选项，然后在尝试使用双因素身份验证首次登录之前从%Localappdata%\Microsoft\Office\15.0\Skype for business 中删除其 SIP 配置文件文件夹。
  
### <a name="disablentcredentials"></a>DisableNTCredentials

通过 Kerberos 或 NTLM 身份验证方法，用户的 Windows 凭据会自动用于身份验证。 在支持 Kerberos 和/或 NTLM 进行身份验证的典型 Skype for Business 服务器部署中，用户每次登录时都不应输入其凭据。
  
如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。
  
若要阻止额外的凭据提示，请在本地工作站上创建以下注册表项，或使用 "Skype for Business 管理模板" 应用到使用组策略的给定池的所有用户：
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

当用户首次登录 Skype for Business 时，系统会提示用户保存其密码。 如果选中此选项，将允许用户的客户端证书存储在个人证书存储和用户的 Windows 凭据中，以便存储在本地计算机的凭据管理器中。
  
当 Skype for Business 配置为支持双因素身份验证时，应禁用**SavePassword**注册表设置。 若要防止用户保存其密码，请在本地工作站上更改以下注册表项，或使用 "Skype for Business 管理模板" 应用到使用组策略的给定池的所有用户：
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 令牌重播

AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。
  
在高度关注安全的环境（例如使用展台时）中，应启用此功能。 有关令牌重播检测的详细信息，请参阅[安全规划和部署 AD FS 2.0 的最佳做法](https://go.microsoft.com/fwlink/p/?LinkId=309215)。
  
## <a name="external-user-access"></a>外部用户访问

将 ADFS 代理或反向代理配置为支持 Skype for business 来自外部网络的双重身份验证不包括在这些主题中。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中配置双因素身份验证](configure-two-factor.md)
  
