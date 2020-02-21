---
title: 将 Kerberos 身份验证帐户密码同步到 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95baeb1e3d55fd2c7ae3137b36c07a7974836bdb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>在 Lync Server 2013 中将 Kerberos 身份验证帐户密码同步到 IIS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2010-11-08_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

在网站中，前端服务器、Standard Edition 服务器和控制器可以使用 Kerberos 身份验证帐户，以对 Web 服务服务的请求进行身份验证。 此过程将查找在已分配 Kerberos 帐户的网站中运行 Web 服务的每台服务器，并将 Internet 信息服务（IIS）配置设置更新为使用 Kerberos 帐户。 有关详细信息，请参阅[在 Lync server 2013 中的服务器上设置 Kerberos 身份验证帐户密码](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)。

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>设置和配置 Kerberos 身份验证帐户密码

1.  以 RTCUniversalServerAdmins 组成员的身份登录到源计算机（例如 fe01.contoso.com）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在 Lync Server 命令行管理程序命令行中，运行以下两个命令：
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    例如：
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > 源计算机和目标计算机的名称必须是服务器的完全限定域名 (FQDN)。除非池名称与要用作源计算机或目标计算机的计算机名称相同，否则不能使用池 FQDN。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > 在对 Kerberos 身份验证（如添加帐户或删除帐户）进行任何更改之后，您必须从 Lync Server 命令行管理程序命令提示符处运行<STRONG>Enable-enable-cstopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

