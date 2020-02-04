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
ms.openlocfilehash: 230341bfc6b26bebd22b55195280ffdff130873d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中将 Kerberos 身份验证帐户分配给站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2017-04-18_

若要成功完成此过程，你应以 RTCUniversalServerAdmins 组成员的用户身份登录。

创建 Kerberos 帐户后，必须将其分配给网站。 这是 Lync Server 2013 网站，而不是 Active Directory 网站。 你可以为每个部署创建多个 Kerberos 身份验证帐户，但只能向网站分配一个帐户。 使用以下过程将以前创建的 Kerberos 身份验证帐户分配到网站。 有关创建 Kerberos 帐户的详细信息，请参阅[在 Lync Server 2013 中创建 Kerberos 身份验证帐户](lync-server-2013-create-a-kerberos-authentication-account.md)。

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>将 Kerberos 身份验证帐户分配给网站

1.  作为 RTCUniversalServerAdmins 组的成员，请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  从命令行运行以下两个命令：
    
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
    > 必须使用 "域 \ 用户名" 格式指定 UserAccount 参数。 User@Domain 扩展名格式不受支持，无法引用为 Kerberos 身份验证创建的计算机对象。

    
    </div>

4.  **可选**：你可能已为你的 WebServices 配置替代 FQDN （完全限定域名），如[在 Lync Server 2013 中按更改 Web 服务 URL](lync-server-2013-change-the-web-services-url.md)。 如果是这种情况，你还需要为此 FQDN 添加 SPN。 例如，如果 FQDN 是 webservices，您将运行：
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > 对 Kerberos 身份验证进行任何更改（如添加帐户或删除帐户）后，必须从 Lync Server Management Shell 命令提示符运行<STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

