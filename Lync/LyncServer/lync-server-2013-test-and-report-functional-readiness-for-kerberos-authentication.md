---
title: 测试和报告 Kerberos 身份验证的功能准备情况
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3c5a2c83d664182226decb88ab6bd1c34d6d3a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中测试和报告 Kerberos 身份验证的功能准备情况

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-01-16_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

您可以使用**CsKerberosAccountAssignment** Windows PowerShell cmdlet 测试和报告 Kerberos 身份验证的网站分配的功能准备情况。 此命令查询必需参数 Identity 中指定的站点。 可选报告参数使 cmdlet 将 HTML 报告写入 C：\\运行该命令的计算机上的日志。 可选参数 Verbose 会将活动信息显示在屏幕上。

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>测试并报告站点的 Kerberos 身份验证的运行就绪情况

1.  作为 RTCUniversalServerAdmins 组的成员，登录到运行 Lync Server 2013 的域中的计算机，或登录到安装了管理工具的计算机上。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令行中运行以下命令：
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    例如：
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

