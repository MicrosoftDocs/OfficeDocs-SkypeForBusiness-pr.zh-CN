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
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>在 Lync Server 2013 中在服务器上设置 Kerberos 身份验证帐户密码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-01-16_

若要成功完成此过程，你应以 RTCUniversalServerAdmins 组成员的用户身份登录。

对于拥有前端服务器、标准版服务器和控制器的每个网站，必须在 Kerberos 帐户上设置密码。 你可以通过在网站中的一台服务器（例如，一台前端服务器）上运行**CsKerberosAccountPassword** Windows PowerShell cmdlet 来设置密码。 对于每个网站，必须运行**CsKerberosAccountPassword** cmdlet。 该 cmdlet 为 Web 服务服务配置 Internet 信息服务（IIS），然后在 Active Directory 域服务中的计算机帐户上设置密码。 根据与 cmdlet 一起使用的参数，另一种方法是在一台服务器上配置 IIS，同时使用已配置为 Kerberos 帐户密码源的另一台服务器。

使用**CsKerberosAccountPassword** cmdlet 设置密码时，Kerberos 将密码设置为随机生成的字符串。 此 cmdlet 将联系人分配给此帐户的所有 Lync Server 2013 中央站点中的所有 IIS 实例。

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>为 Kerberos 身份验证帐户设置密码

1.  以 RTCUniversalServerAdmins 组成员的身份登录到安装了 Lync Server 管理外壳的任何域计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  从命令行运行以下两个命令：
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    例如：
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > 必须使用 "域 \ 用户名" 格式指定 UserAccount 参数。 User@Domain 扩展名格式不受支持，无法引用为 Kerberos 身份验证创建的计算机对象。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 对 Kerberos 身份验证进行任何更改（如添加帐户或删除帐户）后，必须从 Lync Server Management Shell 命令提示符运行<STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

