---
title: 管理 Web 服务配置设置Skype for Business Server
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
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 摘要：管理 Web 服务配置设置Skype for Business Server。
ms.openlocfilehash: f007a93eb71fc015f71ddef51011008315de82e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633606"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a>管理 Web 服务配置设置Skype for Business Server
 
**摘要：** 管理 Web 服务配置设置Skype for Business Server。
  
您可以使用 **"Web 服务**"页来配置用于访问相关 Web 服务器Skype for Business Server Web 服务的身份验证方法。
  
按照以下步骤创建新的 Web 服务策略。
  
### <a name="to-create-new-web-service-configuration-settings"></a>创建新的 Web 服务配置设置

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署了 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“Web 服务”。
    
4. 在“Web 服务”页上，单击“新建”，然后执行下列操作之一：
    
   - 要配置站点的 Web 服务，请单击“站点配置”。在“选择站点”中，单击将应用此 Web 服务策略的站点，然后单击“确定”。
    
   - 要配置池的 Web 服务，请单击“池配置”。在“选择服务”中，单击将应用此 Web 服务策略的服务，然后单击“确定”。 
    
5. 在“新建 Web 服务设置”的“集成的 Windows 身份验证”中，选择“协商”、“集成的 Windows 身份验证”或“无”。
    
6. 根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
   - **启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
   - **启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。
    
7. 单击“提交”。
    
## <a name="modify-existing-web-service-configuration-settings"></a>修改现有 Web 服务配置设置

您可以使用 **"Web 服务**"页来配置用于访问相关 Web 服务器Skype for Business Server Web 服务的身份验证方法。
  
按照以下步骤修改现有的 Web 服务策略。
  
### <a name="to-modify-existing-web-service-configuration-settings"></a>修改现有 Web 服务配置设置

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署了 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“Web 服务”。
    
4. 在“Web 服务”页上，单击某个配置，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑 Web 服务设置”的“集成 Windows 身份验证”中，选择“协商”、“集成 Windows 身份验证”或“无”。
    
6. 根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
   - **启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。
    
   - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
   - **启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。
    
7. 单击“提交”。
    
## <a name="delete-existing-web-service-configuration-settings"></a>删除现有 Web 服务配置设置

按照以下步骤删除 Web 服务配置设置。
  
### <a name="to-delete-web-service-configuration-settings"></a>删除 Web 服务配置设置

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署了 Skype for Business Server 的网络内的任何计算机。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“安全性”，然后单击“Web 服务”。
    
4. 在“Web 服务”页上的搜索字段中，键入要删除的策略的全部或部分名称。
    
5. 在策略列表中，单击所需的策略，再单击“编辑”，然后单击“删除”。
    
6. 单击“确定”。
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 设置 Web 服务Windows PowerShell配置

可以通过使用 Windows PowerShell **和 Remove-CsWebServiceConfiguration** cmdlet 删除 Web 服务配置设置。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程 PowerShell 管理[Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在Skype for Business Server。
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>删除特定的 Web 服务配置设置集合

- 以下命令会删除应用到 Redmond 站点的 Web 服务安全设置：
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>删除应用于站点范围的所有 Web 服务配置设置

以下命令会删除应用到服务范围的所有 Web 服务安全设置：
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>删除允许证书身份验证的所有 Web 服务配置设置

以下命令会删除允许使用证书身份验证的所有 Web 服务安全设置：
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

有关详细信息，请参阅 [Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)。
