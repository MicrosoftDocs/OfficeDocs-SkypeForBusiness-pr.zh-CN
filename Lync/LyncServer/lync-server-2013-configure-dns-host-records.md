---
title: Lync Server 2013：配置 DNS 主机记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8184568e18f37e2a00316d3b648b5e8813faa268
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>为 Lync Server 2013 配置 DNS 主机记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

要成功完成此过程，应至少以 Domain Admins 组或 DNSAdmins 组成员的身份登录到服务器或域。

<div>

## <a name="to-configure-dns-host-a-records"></a>配置 DNS 主机 A 记录

1.  在域名系统 (DNS) 服务器上，单击“开始”****，再单击“管理工具”****，然后单击“DNS”****。

2.  在您的域的控制台树中，展开 "**正向查找区域**"，然后右键单击将在其中安装 Lync Server 2013 的域。

3.  单击“新建主机(A 或 AAAA)”****。

4.  单击“名称”****，键入池的主机名（根据在其中定义记录的区域采用域名，但不需要输入域名作为 A 记录的一部分）。

5.  单击 " **IP 地址**"，键入前端池的负载平衡器的虚拟 IP （VIP）。
    
    <div>
    

    > [!IMPORTANT]  
    > 在使用控制器池的部署中，简单 URL 的主机 (A) 记录应指向控制器负载平衡器的 VIP。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如果只部署一台 Enterprise Edition Server 或控制器（连接到不带负载平衡器的拓扑中），或者部署一台 Standard Edition Server，请键入该 Enterprise Edition Server、Standard Edition Server 或控制器的 IP 地址。如果在一个池中部署多台 Enterprise Edition Server 或控制器，则需要使用负载平衡器。负载平衡器不与 Standard Edition Server 一起使用。

    
    </div>

6.  单击“添加主机”****，然后单击“确定”****。

7.  要创建另一个 A 记录，请重复步骤 4 和 5。

8.  创建完所需的全部 A 记录后，单击“完成”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

