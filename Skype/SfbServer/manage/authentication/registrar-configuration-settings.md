---
title: 管理 Skype for Business 服务器中的注册机构配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '摘要: 管理 Skype for business 服务器的注册机构配置设置。'
ms.openlocfilehash: 4ad7815da0744a78cd72208ef390362bff26c2ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291170"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>管理 Skype for Business 服务器中的注册机构配置设置
 
**摘要:** 管理 Skype for business 服务器的注册机构配置设置。
  
可以使用注册器配置代理服务器身份验证方法。指定的身份验证协议确定池中的服务器向客户端发出的质询类型。可以选择以下协议：
  
- **Kerberos**这是可供客户端使用的最强大的基于密码的身份验证方案, 但通常仅适用于企业客户端, 因为它需要与密钥分发中心 (Kerberos 域控制器) 的客户端连接。 如果服务器仅验证企业客户端的身份，则此设置适用。
    
- **NTLM**这是基于密码的身份验证, 可供对密码使用挑战响应哈希方案的客户端使用。 对于无法连接到密钥发行中心（Kerberos 域控制器）的客户端（例如，远程用户），这是唯一可用的身份验证方案。 如果服务器仅验证远程用户的身份，则应选择 NTLM。
    
- **证书身份验证**当服务器需要从 Lync Phone Edition 客户端、公共区域电话、Skype for business 和 Lync Windows 应用商店应用获取证书时, 这是新的身份验证方法。 在 Lync Phone 版客户端上, 用户登录并通过提供个人识别码 (PIN) 成功进行身份验证后, Skype for Business 服务器将 SIP URI 设置到手机并设置 Skype for business 服务器签名用于向手机标识 Joe (如: SN=joe@contoso.com) 的证书或用户证书。 此证书用于使用注册器和 Web 服务进行身份验证。
    
> [!NOTE]
> 如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。 
  
如果你要使用 Lync Windows 应用商店应用客户端, 则必须启用证书身份验证。
  
### <a name="to-create-new-registrar-configuration-settings"></a>创建新的注册器配置设置

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。
    
4. 在“注册器”**** 页上，单击“新建”****。
    
5. 在“选择服务”**** 中，单击将应用此注册器的服务，然后单击“确定”****。
    
6. 在“新建注册器设置”**** 中，根据客户端的功能和环境支持，选择下列一项或多项：
    
   - **启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。
    
   - **启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
7. 单击“**提交**”。
    
## <a name="modify-existing-registrar-configuration-settings"></a>修改现有的注册器配置设置

可以使用注册器配置代理服务器身份验证协议。 
  
> [!NOTE]
> 如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。 
  
按照以下步骤修改现有的注册器。 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>修改现有的注册器配置设置

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。
    
4. 在“注册器”**** 页上，单击某个服务，再单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在“编辑注册器设置”**** 中，根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
   - **启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。
    
   - **启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
6. 单击“**提交**”。
    
### <a name="to-delete-registrar-configuration-settings"></a>删除现有注册器配置设置

1. 从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。
    
4. 在“注册器”**** 页上的搜索字段中，键入要删除的注册器的全部或部分名称。
    
5. 在列表中，单击所需的注册器，再单击“编辑”****，然后单击“删除”****。
    
6. 单击“**确定**”。
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除注册机构配置设置

你可以使用 Windows PowerShell 和**CsProxyConfiguration** Cmdlet 删除注册机构配置设置。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅博客文章["快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 在 Skype for Business 服务器中, 此过程是相同的。
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>删除一组特定的注册器安全设置

- 以下命令会删除应用到边缘服务器 atl-edge-011.litwareinc.com 的注册器安全设置：
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>删除应用到站点范围的所有注册器安全设置

- 以下命令会删除应用到注册器服务的所有注册器安全设置：
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>删除允许 NTLM 身份验证的所有注册器安全设置

- 以下命令会删除允许使用 NTLM 进行客户端身份验证的所有注册器安全设置：
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

有关详细信息, 请参阅[Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。
  

