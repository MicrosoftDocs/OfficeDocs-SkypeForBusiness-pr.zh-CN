---
title: Lync Server 2013：将 Kerberos 身份验证从站点中删除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e88f3de6f653354087d1abd0f7884ee09eda2f36
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>在 Lync Server 2013 中将 Kerberos 身份验证从站点中删除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-01-16_

若要成功完成此过程，你应以 RTCUniversalServerAdmins 组成员的用户身份登录。

如果需要从网站中删除 Kerberos 身份验证或停用网站，则必须使用**CsKerberosAccountAssignment** cmdlet 从网站中删除 kerberos 身份验证帐户分配。 使用以下过程删除 Kerberos 身份验证帐户分配，这将从网站中的所有计算机中删除作业。

<div class=" ">


> [!WARNING]  
> 如果你永久停止启用 Kerberos 的帐户，则在删除作业后，你应该使用 Active Directory 用户和计算机从 Active Directory 域服务中删除它。 如果计划将来使用该对象，可能需要保留 Active Directory 对象。



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>从网站中删除 Kerberos 身份验证

1.  作为 RTCUniversalServerAdmins 组的成员，请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  从命令行运行以下两个命令：
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    例如：
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 对 Kerberos 身份验证进行任何更改（如添加帐户或删除帐户）后，必须从 Lync Server Management Shell 命令提示符运行<STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

