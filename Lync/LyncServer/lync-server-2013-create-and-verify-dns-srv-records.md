---
title: Lync Server 2013：创建并验证 DNS SRV 记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8440d2ae91d535c8c4747c923b1b17dda9bb0f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>在 Lync Server 2013 中创建并验证 DNS SRV 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

若要成功完成此过程，你应至少作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。

本主题介绍了如何配置您需要在 Lync Server 2013 部署中创建的域名系统（DNS）记录以及自动客户端登录所需的域名系统（DNS）记录。 创建前端池时，安装程序将为池创建 Active Directory 对象和设置，包括池完全限定的域名（FQDN）。 为标准版服务器创建类似的对象和设置。 对于能够连接到池或标准版服务器的客户端，必须在 DNS 中注册池或标准版服务器的 FQDN。 必须在每个 SIP 域的内部 DNS 中创建 DNS SRV 记录。 此过程假定你的内部 DNS 具有适用于你的 SIP 用户域的区域。

<div>

## <a name="to-configure-a-dns-srv-record"></a>配置 DNS SRV 记录

1.  在 DNS 服务器上，单击 "**开始**"，单击 "**管理工具**"，然后单击 " **DNS**"。

2.  在 SIP 域的控制台树中，展开 "**正向查找区域**"，然后右键单击将在其中安装 Lync Server 2013 的 SIP 域。

3.  单击 "**其他新记录**"。

4.  在 "**选择资源记录类型**" 中，单击 "**服务位置（SRV）**"，然后单击 "**创建记录**"。

5.  单击 "**服务**"，然后** \_** 键入 "sipinternaltls"。

6.  单击 "**协议**"，然后** \_** 键入 "tcp"。

7.  单击 "**端口号**"，然后键入**5061**。

8.  单击 "**主机提供此服务**"，然后键入池或标准版服务器的 FQDN。

9.  单击 **"确定**"，然后单击 "**完成**"。

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>验证 DNS SRV 记录的创建

1.  使用已验证用户组的成员的帐户登录到域中的客户端计算机或具有同等权限。

2.  单击 **“开始”**，然后单击 **“运行”**。

3.  在 "**打开**" 框中，键入**cmd**，然后单击 **"确定"**。

4.  在命令提示符处，键入**nslookup**，然后按 ENTER。

5.  键入 " **set type = srv**"，然后按 enter。

6.  键入** \_sipinternaltls。\_tcp.contoso.com**，然后按 ENTER。 为传输层安全（TLS）记录显示的输出如下所示：
    
    服务器： \<dns 服务器\>contoso.com
    
    地址： \<DNS 服务器的 IP 地址\>
    
    非权威应答：
    
    \_sipinternaltls.\_tcp.contoso.com SRV 服务位置：
    
    优先级 = 0
    
    权重 = 0
    
    端口 = 5061
    
    svr hostname = poolname.contoso.com （或标准版服务器 A 记录）
    
    poolname.contoso.com internet 地址 = \<单个企业版服务器的负载平衡\>器\<或 ip 地址的虚拟 IP 地址，只有一个企业版服务器\>或\<标准版服务器的 ip 地址的池\>

7.  完成后，在命令提示符处键入 "**退出**"，然后按 enter。

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>验证是否可以解析前端池或标准版服务器的 FQDN

1.  登录到域中的客户端计算机。

2.  单击 **“开始”**，然后单击 **“运行”**。

3.  在 "**打开**" 框中，键入**cmd**，然后单击 **"确定"**。

4.  在命令提示符处，键入 " **nslookup** \<FQDN" （标准版\>服务器\<\>的前端池或 fqdn），然后按 ENTER。

5.  验证您是否收到了解析为 FQDN 的相应 IP 地址的答复。

</div>

</div>

<span> </span>

</div>

</div>

</div>

