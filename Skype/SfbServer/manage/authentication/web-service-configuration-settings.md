---
title: 管理 Web 服务配置设置中 Skype 业务服务器
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 摘要： 管理 Web 服务配置设置中 Skype 业务服务器。
ms.openlocfilehash: 7724ef576142c2eb6cebb287a88b7761a69028aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995832"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>管理 Web 服务配置设置中 Skype 业务服务器
 
**摘要：** 管理 Web 服务配置设置中 Skype 业务服务器。
  
您可以使用**Web 服务**页配置用于访问 Skype 的业务相关的服务器的身份验证方法 web 服务器和 Web 服务。
  
按照以下步骤创建新的 Web 服务策略。
  
### <a name="to-create-new-web-service-configuration-settings"></a>创建新的 Web 服务配置设置

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“Web 服务”****。
    
4. 在“Web 服务”**** 页上，单击“新建”****，然后执行下列操作之一：
    
   - 要配置站点的 Web 服务，请单击“站点配置”****。在“选择站点”**** 中，单击将应用此 Web 服务策略的站点，然后单击“确定”****。
    
   - 要配置池的 Web 服务，请单击“池配置”****。在“选择服务”**** 中，单击将应用此 Web 服务策略的服务，然后单击“确定”****。 
    
5. 在“新建 Web 服务设置”**** 的“集成的 Windows 身份验证”**** 中，选择“协商”****、“集成的 Windows 身份验证”**** 或“无”****。
    
6. 根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
   - **启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
   - **启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。
    
7. 单击“**提交**”。
    
## <a name="modify-existing-web-service-configuration-settings"></a>修改现有的 Web 服务配置设置

您可以使用**Web 服务**页配置用于访问 Skype 的业务相关的服务器的身份验证方法 web 服务器和 Web 服务。
  
按照以下步骤修改现有的 Web 服务策略。
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>修改现有的 Web 服务配置设置

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“Web 服务”****。
    
4. 在“Web 服务”**** 页上，单击某个配置，再单击“编辑”****，然后单击“显示详细信息”****。
    
5. 在“编辑 Web 服务设置”**** 的“集成 Windows 身份验证”**** 中，选择“协商”****、“集成 Windows 身份验证”**** 或“无”****。
    
6. 根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
   - **启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
   - **启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。
    
7. 单击“**提交**”。
    
## <a name="delete-existing-web-service-configuration-settings"></a>删除现有的 Web 服务配置设置

按照以下步骤删除 Web 服务配置设置。
  
### <a name="to-delete-web-service-configuration-settings"></a>删除 Web 服务配置设置

1.  从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
3. 在左侧导航栏中，单击“安全性”****，然后单击“Web 服务”****。
    
4. 在“Web 服务”**** 页上的搜索字段中，键入要删除的策略的全部或部分名称。
    
5. 在策略列表中，单击所需的策略，再单击“编辑”****，然后单击“删除”****。
    
6. 单击“**确定**”。
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 Web 服务配置设置

您可以使用 Windows PowerShell 和**Remove-cswebserviceconfiguration** cmdlet 删除 web 服务配置设置。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>删除特定的 Web 服务配置设置集合

- 以下命令会删除应用到 Redmond 站点的 Web 服务安全设置：
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>删除应用到站点范围的所有 Web 服务配置设置

以下命令会删除应用到服务范围的所有 Web 服务安全设置：
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>删除允许证书身份验证的所有 Web 服务配置设置

以下命令会删除允许使用证书身份验证的所有 Web 服务安全设置：
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

有关详细信息，请参阅[Remove-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。
  

