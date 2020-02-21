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
ms.openlocfilehash: c7faf0cd00b59d5df5bab1650a28eff8b9563f91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>在 Lync Server 2013 中创建和验证 DNS SRV 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。

本主题介绍如何配置您需要在 Lync Server 2013 部署中创建的域名系统（DNS）记录以及自动客户端登录所需的域名系统（DNS）记录。 创建前端池时，安装程序将为池创建 Active Directory 对象和设置，包括池完全限定的域名（FQDN）。 将为 Standard Edition server 创建类似的对象和设置。 若要使客户端能够连接到池或 Standard Edition 服务器，则必须在 DNS 中注册池或 Standard Edition 服务器的 FQDN。 必须在内部 DNS 中为每个 SIP 域创建 DNS SRV 记录。 此过程假定内部 DNS 具有 SIP 用户域的区域。

<div>

## <a name="to-configure-a-dns-srv-record"></a>配置 DNS SRV 记录

1.  在 DNS 服务器上，单击“开始”****，再单击“管理工具”****，然后单击“DNS”****。

2.  在您的 SIP 域的控制台树中，展开 "**正向查找区域**"，然后右键单击将在其中安装 Lync Server 2013 的 SIP 域。

3.  单击“其他新记录”****。

4.  在“选择资源记录类型”**** 中，单击“服务位置(SRV)”****，然后单击“创建记录”****。

5.  单击 "**服务**"，然后键入** \_sipinternaltls**。

6.  单击 "**协议**"，然后键入** \_tcp**。

7.  单击“端口号”****，再键入“5061”****。

8.  单击 "**主机提供此服务**"，然后键入 Pool 或 Standard Edition SERVER 的 FQDN。

9.  单击“确定”****，然后单击“完成”****。

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>验证 DNS SRV 记录的创建

1.  使用属于 Authenticated Users 组成员的帐户或具有等效权限的帐户登录到域中的客户端计算机。

2.  单击“开始”****，然后单击“运行”****。

3.  在“打开”**** 框中，键入 **cmd**，然后单击“确定”****。

4.  在命令提示符处键入 **nslookup**，然后按 Enter。

5.  键入 **set type=srv**，然后按 Enter。

6.  键入** \_sipinternaltls。\_tcp.contoso.com**，然后按 enter。 输出的传输层安全性 (TLS) 记录如下所示：
    
    服务器： \<dns 服务器\>contoso.com
    
    Address： \<DNS 服务器的 IP 地址\>
    
    Non-authoritative answer:
    
    \_sipinternaltls.\_tcp.contoso.com SRV 服务位置：
    
    优先级 = 0
    
    权重 = 0
    
    端口 = 5061
    
    svr hostname = poolname.contoso.com （或 Standard Edition server A record）
    
    poolname.contoso.com internet address = \<仅具有一个\> Enterprise Edition server \<\>或\<Standard edition server 的 ip 地址的单个企业版服务器的负载平衡器或 ip 地址的虚拟 IP 地址\>

7.  完成后，在命令提示符处键入 **exit**，然后按 Enter。

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>验证是否可以解析前端池或 Standard Edition Server 的 FQDN

1.  登录到域中的客户端计算机。

2.  单击“开始”****，然后单击“运行”****。

3.  在“打开”**** 框中，键入 **cmd**，然后单击“确定”****。

4.  在命令提示符处，键入**nslookup** \<FQDN 的前端池\>或\<Standard Edition 服务器\>的 FQDN，然后按 enter。

5.  验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。

</div>

</div>

<span> </span>

</div>

</div>

</div>

