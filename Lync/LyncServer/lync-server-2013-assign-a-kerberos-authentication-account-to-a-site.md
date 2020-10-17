---
title: Lync Server 2013：将 Kerberos 身份验证帐户分配给站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6137224f313238dae33462298931167ba7bb810
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529519"
---
# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中向网站分配 Kerberos 身份验证帐户

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-04-18_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

创建 Kerberos 帐户后，必须将其分配给站点。 这是 Lync Server 2013 网站，而不是 Active Directory 站点。 每个部署可以创建多个 Kerberos 身份验证帐户，但只能将一个帐户分配给站点。 使用以下过程将之前创建的 Kerberos 身份验证帐户分配给站点。 有关创建 Kerberos 帐户的详细信息，请参阅 [在 Lync Server 2013 中创建 kerberos 身份验证帐户](lync-server-2013-create-a-kerberos-authentication-account.md)。

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>将 Kerberos 身份验证帐户分配给站点

1.  作为 RTCUniversalServerAdmins 组的成员，登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  通过命令行运行以下两个命令：
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    例如：
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > 必须使用 Domain\User 格式指定 UserAccount 参数。User@Domain.extension 格式不支持引用出于 Kerberos 身份验证目的创建的计算机对象。

    
    </div>

4.  **可选**：您可能已为您的 WebServices 配置替代 FQDN (完全限定的域名) ，因为 [在 Lync Server 2013 中，根据更改 Web 服务 URL](lync-server-2013-change-the-web-services-url.md)。 如果是这种情况，您还需要为此 FQDN 添加 SPN。 例如，如果 FQDN 为 webservices，则应运行：
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > 在对 Kerberos 身份验证（如添加帐户或删除帐户）进行任何更改之后，您必须从 Lync Server 命令行管理程序命令提示符处运行 <STRONG>Enable-enable-cstopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

