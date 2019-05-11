---
title: 管理业务服务器的注册器配置设置中 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 摘要： 管理业务服务器的 Skype 的注册器配置设置。
ms.openlocfilehash: fdeca4389ffb64bd68cb3aee7ba6b28e979c5769
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901506"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>管理业务服务器的注册器配置设置中 Skype
 
**摘要：** 管理业务服务器的 Skype 的注册器配置设置。
  
可以使用注册器配置代理服务器身份验证方法。指定的身份验证协议确定池中的服务器向客户端发出的质询类型。可以选择以下协议：
  
- **Kerberos**这是最强大的基于密码的身份验证方案可用于客户端，但它并通常仅适用于企业客户端的因为它要求客户端连接到密钥发行中心 （Kerberos 域控制器）。 如果服务器仅验证企业客户端的身份，则此设置适用。
    
- **NTLM**这是基于密码的身份验证可用于对密码使用质询响应哈希方案的客户端。 对于无法连接到密钥发行中心（Kerberos 域控制器）的客户端（例如，远程用户），这是唯一可用的身份验证方案。 如果服务器仅验证远程用户的身份，则应选择 NTLM。
    
- **证书身份验证**当服务器需要从 Lync Phone Edition 客户端、 公用区域电话、 for Business 的 Skype 和 Lync Windows 应用商店应用程序获取证书，这是新的身份验证方法。 在 Lync Phone Edition 客户端，用户登录并成功进行身份验证通过提供个人识别号 (PIN) Skype 业务服务器，然后设置到电话的 SIP URI 并设置 Skype 业务服务器签名后证书或标识 Joe 用户证书 (例如： SN=joe@contoso.com) 到电话。 此证书用于使用注册器和 Web 服务进行身份验证。
    
> [!NOTE]
> 如果服务器支持对远程客户端和企业客户端进行身份验证，我们建议您同时启用 Kerberos 和 NTLM。边缘服务器与内部服务器通信，以确保只向远程客户端提供 NTLM 身份验证。如果在这些服务器上只启用 Kerberos，则无法对远程用户进行身份验证。如果该服务器也对企业用户进行身份验证，则会使用 Kerberos。 
  
如果您将使用 Lync Windows 应用商店应用程序客户端，则必须启用证书身份验证。
  
### <a name="to-create-new-registrar-configuration-settings"></a>创建新的注册器配置设置

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
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

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。
    
4. 在“注册器”**** 页上，单击某个服务，再单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在“编辑注册器设置”**** 中，根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
   - **启用 Kerberos 身份验证**，可使池中的服务器使用 Kerberos 身份验证发出质询。
    
   - **启用 NTLM 身份验证**，可使池中的服务器使用 NTLM 发出质询。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
6. 单击“**提交**”。
    
### <a name="to-delete-registrar-configuration-settings"></a>删除现有注册器配置设置

1. 从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“注册器”****。
    
4. 在“注册器”**** 页上的搜索字段中，键入要删除的注册器的全部或部分名称。
    
5. 在列表中，单击所需的注册器，再单击“编辑”****，然后单击“删除”****。
    
6. 单击“**确定**”。
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除注册器配置设置

您可以使用 Windows PowerShell 和**Remove-csproxyconfiguration** cmdlet 删除注册器配置设置。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
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

有关详细信息，请参阅[Remove-csproxyconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。
  

