---
title: Lync Server 2013：配置 DNS 主机记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>配置 Lync Server 2013 的 DNS 主机记录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

若要成功完成此过程, 你应至少以域管理员组的成员或 DnsAdmins 组的成员的身份登录到服务器或域。

<div>

## <a name="to-configure-dns-host-a-records"></a>配置 DNS 主机 A 记录

1.  在 "域名系统 (DNS)" 服务器上, 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **DNS**"。

2.  在您的域的控制台树中, 展开 "**正向查找区域**", 然后右键单击将安装 Lync Server 2013 的域。

3.  单击 "**新建主机 (A 或 AAAA)**"。

4.  单击 "**名称**", 键入池的主机名 (从在其中定义记录的区域中假定为域名, 并且不需要将其输入为 A 记录的一部分)。

5.  单击 " **IP 地址**", 键入前端池的负载平衡器的虚拟 IP (VIP)。
    
    <div>
    

    > [!IMPORTANT]  
    > 在使用控制器池的部署中, 简单 Url 的主机 (A) 记录应指向控制器负载平衡器的 VIP。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如果仅部署一个连接到拓扑的企业版服务器或 Director 而不使用负载平衡器, 或者如果你部署标准版服务器, 请键入企业版服务器、标准版服务器或 Director 的 IP 地址。 如果在一个池中部署多个企业版服务器或控制器, 则需要负载平衡器。 负载平衡器不与标准版服务器一起使用。

    
    </div>

6.  单击 "**添加主机**", 然后单击 **"确定"**。

7.  若要创建其他 A 记录, 请重复步骤4和步骤5。

8.  完成创建所需的所有记录后, 单击 "**完成**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

