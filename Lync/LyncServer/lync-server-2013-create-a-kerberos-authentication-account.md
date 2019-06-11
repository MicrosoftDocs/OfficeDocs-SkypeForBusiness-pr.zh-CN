---
title: Lync Server 2013：创建 Kerberos 身份验证帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>在 Lync Server 2013 中创建 Kerberos 身份验证帐户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-01-02_

若要成功完成此过程, 你应至少作为域管理员组的成员登录到服务器或域。

你可以为每个网站创建 Kerberos 身份验证帐户, 也可以创建单个 Kerberos 身份验证帐户并将其用于所有网站。 你可以使用 Windows PowerShell cmdlet 来创建和管理帐户, 包括标识分配给每个网站的帐户。 拓扑生成器和 Lync Server 2013 "控制面板" 不显示 Kerberos 身份验证帐户。 使用以下过程创建要用于 Kerberos 身份验证的一个或多个用户帐户。

<div>

## <a name="to-create-a-kerberos-account"></a>创建 Kerberos 帐户

1.  作为域管理员组的成员, 请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  从命令行运行以下命令:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    例如：
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  通过打开 "Active Directory 用户和计算机" 确认是否创建了计算机对象, 展开 "**用户**" 容器, 然后确认该用户帐户的计算机对象位于容器中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

