---
title: Lync Server 2013：在服务器上设置 Kerberos 身份验证帐户密码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9799be0fda2b1a3c5b7765774b1f9e3199cc61f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>在 Lync Server 2013 中的服务器上设置 Kerberos 身份验证帐户密码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-01-16_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

必须为拥有前端服务器、Standard Edition Server 和控制器的每个站点设置 Kerberos 帐户密码。 您可以通过在站点中的一台服务器（例如，一台前端服务器）上运行**CsKerberosAccountPassword** Windows PowerShell cmdlet 来设置密码。 对于每个网站，必须运行**CsKerberosAccountPassword** cmdlet。 Cmdlet 为 Web 服务服务配置 Internet 信息服务（IIS），然后在 Active Directory 域服务中的计算机帐户上设置密码。 使用已配置为 Kerberos 帐户密码源的其他服务器时，另一种基于与 cmdlet 一起使用的参数的方法会在服务器上配置 IIS。

使用 **Set-CsKerberosAccountPassword** cmdlet 设置密码时，Kerberos 会将密码设置为随机生成的字符串。 此 cmdlet 将联系分配此帐户的所有 Lync Server 2013 中央站点中的所有 IIS 实例。

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>为 Kerberos 身份验证帐户设置密码

1.  以 RTCUniversalServerAdmins 组成员的身份登录到安装了 Lync Server 命令行管理程序的任何域计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  通过命令行运行以下两个命令：
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    例如：
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > 必须使用 Domain\User 格式指定 UserAccount 参数。User@Domain.extension 格式不支持引用出于 Kerberos 身份验证目的创建的计算机对象。

    
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

