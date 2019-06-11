---
title: Lync Server 2013：报告 Kerberos 帐户分配
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>在 Lync Server 2013 中报告 Kerberos 帐户分配

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-01-16_

若要成功完成此过程, 你应以 RTCUniversalServerAdmins 组成员的用户身份登录。

你可以使用**CsKerberosAccountAssignment** cmdlet 查询有关 Kerberos 身份验证帐户分配的信息, 并报告有关你的部署中的当前作业的信息。

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>查询网站的 Kerberos 身份验证帐户分配

1.  作为 RTCUniversalServerAdmins 组的成员, 请登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  从命令行运行以下命令之一:
    
      - 若要查询组织中的所有 Kerberos 身份验证帐户分配并返回每个的作业信息, 请运行不带任何参数的 cmdlet:
        
            Get-CsKerberosAccountAssignment
    
      - 若要在部署中查询所有 Kerberos 身份验证帐户分配并返回每个 Kerberos 身份验证帐户分配的信息, 请通过 Identity 参数运行 cmdlet:
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        例如：
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - 若要查询单个网站中的所有 Kerberos 身份验证帐户分配并返回有关每个帐户的作业信息, 请使用筛选器参数运行 cmdlet:
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        例如：
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > 为 Filter 参数指定 * SiteName 返回有关包含指定网站名称的所有网站的信息, 这些网站在网站标识符中的任意位置 (例如, 包含字符串 Redmond 的所有网站位于网站标识符中)。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

