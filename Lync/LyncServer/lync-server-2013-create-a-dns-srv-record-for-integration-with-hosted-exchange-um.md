---
title: 创建 DNS SRV 记录以与托管 Exchange UM 集成
description: 创建用于与托管 Exchange UM 集成的 DNS SRV 记录。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694a595977abe33bebbb5fbcf2a508c9bb4e35a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542138"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>创建 DNS SRV 记录以与托管 Exchange UM 集成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

本主题介绍如何将 Lync Server 2013 边缘服务器所需的域名系统 (DNS) SRV 记录配置为路由到托管 Exchange 服务（如 Microsoft Exchange Online）。

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>为承载的 Exchange 服务创建外部 DNS SRV 记录

1.  以 DnsAdmins 组成员的身份登录外部 DNS 服务器。

2.  依次单击“开始”****、“管理工具”**** 和“DNS”****。

3.  在您的 SIP 域的控制台树中，展开 " **正向查找区域**"，然后选择将在其中安装 Lync Server 2013 的 SIP 域。
    
    <div>
    

    > [!IMPORTANT]
    > 您必须在 Lync Server 所在的或将安装 Lync Server 的 SIP 域中创建 DNS SRV 记录。在创建 SRV 记录时，用于“提供此服务的主机”字段的 FQDN 必须是边缘池的外部 FQDN。例如，如果边缘池的外部 FQDN 为 edge01.contoso.net，请输入该值。此外，此记录必须位于 DNS 主机 (A) 记录所在的域中。

    
    </div>

4.  右键单击选定的域，再单击“其他新记录”****。

5.  在“资源记录类型”**** 中，单击“服务位置(SRV)”****，再单击“创建记录”****。

6.  在 "**新建资源记录**" 中，单击 "**服务**"，然后键入** \_ sipfederationtls**。

7.  单击 "**协议**"，然后键入** \_ tcp**。

8.  单击“端口号”****，再键入“5061”****。

9.  单击 " **主机提供此服务**"，然后键入 lync Server 2013 Edge 池 (FQDN) 的完全限定域名，该名称为受信任的外部客户端提供对 lync server 2013 系统的访问权限。
    
    <div>
    

    > [!NOTE]
    > 此外，还必须将域设置为 Exchange Online 设置中的权威性的接受域。 有关详细信息，请参阅在上创建接受的域 <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> 。

    
    </div>

10. 单击“确定”****，再单击“完成”****。

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>验证是否已成功创建 DNS SRV 记录

1.  登录到域中的一台客户端计算机。

2.  单击“开始”****，再单击“运行”****。

3.  在命令提示符下，运行下列命令：
    
        nslookup <FQDN Lync Edge Pool>

4.  验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为反向代理服务器创建 DNS 记录](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

