---
title: 管理注册器配置设置Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 摘要：管理注册器配置Skype for Business Server。
ms.openlocfilehash: 78a9e2b7af9b01fb5094e6d4286742a4c3147cfb
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773732"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>管理注册器配置设置Skype for Business Server
 
**摘要：** 管理 Skype for Business Server 的注册器配置Skype for Business Server。
  
可以使用注册器配置代理服务器身份验证方法。指定的身份验证协议确定池中的服务器向客户端发出的质询类型。可以选择以下协议：
  
- **Kerberos** 这是可供客户端使用的最强基于密码的身份验证方案，但它通常仅适用于企业客户端，因为它需要客户端连接到密钥发行中心 (Kerberos 域控制器) 。 如果服务器仅对企业客户端进行身份验证，则此设置适用。
    
- **NTLM** 这是对密码使用质询响应哈希方案的客户可用的基于密码的身份验证。 这是没有连接到 Kerberos 域控制器上密钥发行中心 (客户端（如) ）的唯一身份验证形式。 如果服务器仅对远程用户进行身份验证，则应该选择"NTLM"。
    
- **证书身份验证** 当服务器需要从 Lync 电话 Edition 客户端、公用区域电话、Skype for Business和 Lync Windows Store 应用获取证书时，这是新的身份验证方法。 在 Lync 电话 Edition 客户端上，在用户登录并通过提供个人标识号 (PIN) 成功通过身份验证后，Skype for Business Server 然后将 SIP URI 设置到电话，并设置 Skype for Business Server 签名证书或标识 Joe (（例如：SN=joe@contoso.com） 的用户证书。A3 到电话。 此证书用于向注册器和 Web 服务进行身份验证。
    
> [!NOTE]
> 如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。 
  
如果要使用 Lync Windows Store 应用客户端，则必须启用证书身份验证。
  
### <a name="to-create-new-registrar-configuration-settings"></a>创建新的注册器配置设置

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“注册器”。
    
4. 在“注册器”页上，单击“新建”。
    
5. 在“选择服务”中，单击将应用此注册器的服务，然后单击“确定”。
    
6. 在“新建注册器设置”中，根据客户端的功能和环境支持，选择下列一项或多项：
    
   - **启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。
    
   - **启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
7. 单击“提交”。
    
## <a name="modify-existing-registrar-configuration-settings"></a>修改现有注册器配置设置

可以使用注册器配置代理服务器身份验证协议。 
  
> [!NOTE]
> 如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。 
  
按照以下步骤修改现有注册器。 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>修改现有注册器配置设置

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“注册器”。
    
4. 在"**注册器**"页上，单击某个服务，再单击"编辑"，然后单击"**显示详细信息"。**
    
5. 在 **"** 编辑注册器设置"中，根据客户端的功能和环境支持，选择以下一个或多个选项：
    
   - **启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。
    
   - **启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
6. 单击“提交”。
    
### <a name="to-delete-registrar-configuration-settings"></a>删除注册器配置设置

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击“安全性”，然后单击“注册器”。
    
4. 在 **"注册** 器"页上的搜索字段中，键入要删除的注册器的名称的一部分或全部。
    
5. 在列表中，单击您需要的注册器，再单击"编辑 **"，然后单击**"删除 **"。**
    
6. 单击“**确定**”。
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 设置注册器配置Windows PowerShell注册器配置

可以使用 Windows PowerShell **和 Remove-CsProxyConfiguration** cmdlet 删除注册器配置设置。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。 有关使用远程 powerShell Windows PowerShell连接到Skype for Business Server的详细信息，请参阅 Microsoft Lync [Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>删除一组特定的注册器安全设置

- 以下命令删除应用于边缘服务器服务器的注册器 atl-edge-011.litwareinc.com：
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>删除应用于站点范围的所有注册器安全设置

- 以下命令删除应用于注册器服务的所有注册器安全设置：
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>删除允许 NTLM 身份验证的所有注册器安全设置

- 以下命令删除允许将 NTLM 用于客户端身份验证的所有注册器安全设置：
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

有关详细信息，请参阅 [Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。
