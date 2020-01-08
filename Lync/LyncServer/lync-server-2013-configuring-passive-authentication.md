---
title: Lync Server 2013：配置被动身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590a196ca0e34c0c063b10703c7edd131eb82c50
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>配置 Lync Server 2013 被动身份验证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-07-11_

以下部分介绍了如何通过累积更新配置 Lync Server 2013：7月2013以支持被动身份验证。 启用了双因素身份验证后，将需要启用了双因素身份验证的 Lync 用户才能使用使用 Lync 2013 和累积更新进行登录的 Lync：2013客户端。

<div class="">


> [!NOTE]  
> 强烈建议用户在服务级别为注册机构和 Web 服务启用被动身份验证。 如果为全局级别的注册机构和 Web 服务启用了被动身份验证，则对于未使用 Lync 2013 使用累积更新进行登录的用户而言，这可能会导致组织范围内的身份验证失败：2013客户端桌面客户端。



</div>

<div>

## <a name="web-service-configuration"></a>Web 服务配置

以下步骤介绍了如何为将启用被动身份验证的控制器、企业池和 Standard Edition 服务器创建自定义 Web 服务配置。

**创建自定义 Web 服务配置**

1.  使用 Lync 管理员帐户，通过累积更新登录 Lync Server 2013：年 7 2013 月的前端服务器。

2.  启动 Lync Server 2013 命令行管理程序。

3.  在 Lync Server Management Shell 命令行中，通过运行以下命令为要启用被动身份验证的每个 Director、企业版池和标准版服务器创建新的 Web 服务配置：
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > WsFedPassiveMetadataUri FQDN 的值是您的 AD FS 2.0 服务器的联合身份验证服务名称。可通过从导航窗格右键单击“服务”<STRONG></STRONG>，然后选择“编辑联合身份验证服务属性”<STRONG></STRONG>在 AD FS 2.0 管理控制台中找到联合身份验证服务名称值。

    
    </div>

4.  通过运行以下命令来验证 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值是否设置正确：
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  对于客户端，被动身份验证是 Web 票证身份验证最少首选的身份验证方法。 对于将为被动身份验证启用的所有控制器、企业版池和标准版服务器，必须通过运行以下命令在 Lync Web 服务中禁用所有其他身份验证类型：
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  通过运行以下命令验证是否已成功禁用所有其他身份验证类型：
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>代理配置

当为 Lync Web 服务禁用证书身份验证时，Lync 客户端将使用较少的首选身份验证类型（如 Kerberos 或 NTLM）对注册机构服务进行身份验证。 仍然需要证书身份验证以允许 Lync 客户端检索 webticket，但是注册机构服务必须禁用 Kerberos 和 NTLM。

以下步骤介绍了如何为将启用被动身份验证的边缘池、企业池和 Standard Edition 服务器创建自定义代理配置。

**创建自定义代理配置**

1.  在 Lync Server Management Shell 命令行中，使用累积更新为每个 Lync Server 2013 创建新的代理配置：将通过运行 "6 月 2013 Edge"、"企业版池" 和 "标准版" 服务器启用 "被动身份验证"以下命令：
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  通过运行以下命令来验证所有其他代理身份验证类型是否已成功禁用：
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

