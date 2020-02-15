---
title: Lync Server 2013：创建 Kerberos 身份验证帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e59703328fad7c8763bc1a6cc018c2cbc585c3ed
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>在 Lync Server 2013 中创建 Kerberos 身份验证帐户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-01-02_

要成功完成此过程，至少应以 Domain Admins 组成员身份登录到服务器或域。

可以为每个站点创建多个 Kerberos 身份验证帐户，或者创建一个 Kerberos 身份验证帐户，然后将其用于所有站点。 您可以使用 Windows PowerShell cmdlet 来创建和管理帐户，包括标识分配给每个网站的帐户。 拓扑生成器和 Lync Server 2013 控制面板不显示 Kerberos 身份验证帐户。 使用以下过程创建一个或多个要用于 Kerberos 身份验证的用户帐户。

<div>

## <a name="to-create-a-kerberos-account"></a>创建 Kerberos 帐户

1.  作为 Domain Admins 组的成员，请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令行中运行以下命令：
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    例如：
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  通过打开“Active Directory 用户和计算机”确认是否已创建计算机对象，展开“用户”**** 容器，然后确认容器中存在此用户帐户的计算机对象。

</div>

</div>

<span> </span>

</div>

</div>

</div>

