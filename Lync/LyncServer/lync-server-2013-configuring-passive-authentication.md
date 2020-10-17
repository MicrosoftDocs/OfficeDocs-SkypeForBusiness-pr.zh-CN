---
title: Lync Server 2013：配置被动身份验证
description: Lync Server 2013：配置被动身份验证。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52a83c1413dcac18fb37ff0fe308266a3d7aeab4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548288"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a>配置 Lync Server 2013 被动身份验证

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-11_

下一节介绍如何使用累积更新配置 Lync Server 2013：7月2013以支持被动身份验证。 一旦启用，启用了双重身份验证的 Lync 用户将需要使用物理或虚拟智能卡和有效 PIN，以使用使用 Lync 2013 的累积更新来登录：7月2013客户端。

<div class="">


> [!NOTE]  
> 强烈建议客户在服务级别为注册器和 Web 服务启用被动身份验证。 如果为全局级别的注册器和 Web 服务启用了被动身份验证，则可能会导致未使用 Lync 2013 以累积更新进行登录的用户对组织范围的身份验证失败：2013客户端桌面客户端。



</div>

<div>

## <a name="web-service-configuration"></a>Web 服务配置

以下步骤介绍如何为控制器、企业池和 Standard Edition 服务器创建自定义 web 服务配置，这些服务器将启用被动身份验证。

**创建自定义 web 服务配置**

1.  使用 "Lync 管理员" 帐户通过累积更新登录到 Lync Server 2013：7月 2013 6 日前端服务器。

2.  启动 Lync Server 2013 命令行管理程序。

3.  在 Lync Server 命令行管理程序命令行中，通过运行以下命令为每个控制器、企业版池和 Standard Edition 服务器创建一个新的 Web 服务配置，该配置将启用被动身份验证：
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > WsFedPassiveMetadataUri FQDN 的值是 AD FS 2.0 服务器的联合身份验证服务名称。 在 AD FS 2.0 管理控制台中，可通过右键单击导航窗格中的 " <STRONG>服务</STRONG> "，然后选择 " <STRONG>编辑联合身份验证服务属性</STRONG>" 来找到联合身份验证服务名称值。

    
    </div>

4.  通过运行以下命令，验证是否正确设置了 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值：
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  对于客户端，被动身份验证是 web 票证身份验证的最低首选身份验证方法。 对于将为其启用被动身份验证的所有控制器、企业池和 Standard Edition 服务器，必须通过运行以下命令在 Lync Web 服务中禁用所有其他身份验证类型：
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

如果禁用了 Lync Web 服务的证书身份验证，Lync 客户端将使用较少的首选身份验证类型（如 Kerberos 或 NTLM）对注册器服务进行身份验证。 仍需要证书身份验证以允许 Lync 客户端检索 web 票证，但是，必须为注册器服务禁用 Kerberos 和 NTLM。

以下步骤介绍了如何为将为被动身份验证启用的边缘池、企业池和 Standard Edition 服务器创建自定义代理配置。

**创建自定义代理配置**

1.  在 Lync Server 命令行管理程序命令行中，使用累积更新为每个 Lync Server 2013 创建一个新的代理配置：通过运行以下命令，将启用被动身份验证的7月 2013 Edge Edge 池、企业版池和 Standard Edition 服务器：
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  通过运行以下命令验证是否已成功禁用所有其他代理身份验证类型：
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

