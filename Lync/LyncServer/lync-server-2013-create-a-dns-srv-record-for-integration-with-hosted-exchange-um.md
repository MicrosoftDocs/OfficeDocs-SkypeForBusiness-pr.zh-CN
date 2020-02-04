---
title: 为与托管 Exchange UM 的集成创建 DNS SRV 记录
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
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>为与托管 Exchange UM 的集成创建 DNS SRV 记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-20_

本主题介绍了如何配置 Lync Server 2013 Edge 服务器的域名系统（DNS） SRV 记录，以路由到 Microsoft Exchange Online 等托管 Exchange 服务。

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>为托管 Exchange 服务创建外部 DNS SRV 记录

1.  以 DnsAdmins 组成员的身份登录外部 DNS 服务器。

2.  单击 "**开始**"，单击 "**管理工具**"，然后单击 " **DNS**"。

3.  在 SIP 域的控制台树中，展开 "**正向查找区域**"，然后选择将在其中安装 Lync Server 2013 的 SIP 域。
    
    <div>
    

    > [!IMPORTANT]
    > 你必须在安装了 Lync Server 或将安装 Lync Server 的 SIP 域中创建 DNS SRV 记录。 创建 SRV 记录时，用于提供此服务字段的主机的 FQDN 必须是 Edge 池的外部 FQDN。 例如，如果 Edge 池的外部 FQDN 是 edge01.contoso.net，请输入该值。 这还必须位于 DNS 主机（A）记录所在的域中。

    
    </div>

4.  右键单击所选的域，然后单击 "**其他新记录**"。

5.  在 "**资源记录类型**" 中，单击 "**服务位置（SRV）**"，然后单击 "**创建记录**"。

6.  在 "**新建资源记录**" 中，单击 "**服务**"，然后键入** \_"sipfederationtls**"。

7.  单击 "**协议**"，然后** \_** 键入 "tcp"。

8.  单击 "**端口号**"，然后键入**5061**。

9.  单击 "**主机提供此服务**"，然后键入 lync Server 2013 Edge 池的完全限定的域名（FQDN），该域名为受信任的外部客户端提供对 lync server 2013 系统的访问权限。
    
    <div>
    

    > [!NOTE]
    > 域还必须在 Exchange Online 设置中设置为权威的 "接受域"。 有关详细信息，请参阅在中<A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>创建接受的域。

    
    </div>

10. 单击 **"确定**"，然后单击 "**完成**"。

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>验证是否已成功创建 DNS SRV 记录

1.  登录到域中的客户端计算机。

2.  单击 **“开始”**，然后单击 **“运行”**。

3.  在命令提示符处，运行以下命令：
    
        nslookup <FQDN Lync Edge Pool>

4.  验证您是否收到了解析为 FQDN 的相应 IP 地址的答复。

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

