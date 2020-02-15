---
title: Lync Server 2013：编辑设计
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7607fb2f31107e3368fa52167dc5015eb1b71f15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a>在 Lync Server 2013 中编辑设计

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

完成最初的访谈问题后，您可以编辑该网站的完全限定域名（FQDN）和 IP 地址。 要执行此操作，请在 **“全局拓扑”** 页上双击要编辑的站点。

规划工具显示选定网站的站点拓扑。 在站点页面的底部有四个选项卡：

![规划工具网站拓扑](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "规划工具网站拓扑")

  - 站点拓扑 – 当前显示的页面，其中包含推荐拓扑的视图概览。

  - 边缘网络图–设计人员在规划工具中执行大部分工作的 "边缘网络图" 页面。 该图显示了推荐的 Lync Server 2013 拓扑的网络配置，其中包含可编辑的 IP 地址和 Fqdn 的条目，以及服务器、池以及硬件和域名系统（DNS）负载平衡器。

  - 边缘管理报告 –“边缘管理报告”共包含四份报告：
    
    ![边缘管理报告页](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "边缘管理报告页")  
    
      - 摘要报告 - 边缘网络配置设置的常规报告。 如果将 "**边缘网络关系图**" 页上的值编辑为将在实际部署中使用的 "拓扑 tcp/ip" 和 "FQDN" 值，则这些地址和名称将在此处表示。 否则，将显示默认文本。
    
      - 证书报告 -“证书报告”会列出拓扑所需证书的使用者名称和使用者备用名称。
    
      - 防火墙报告 -“防火墙报告”列出在基础结构中配置外围防火墙的必要信息。 这包括 IP 地址（默认值或编辑的值）、服务器角色、源 IP 和端口、目标 IP 和端口、传输协议、应用程序协议和相关说明。
    
      - DNS 报告– DNS 报告列出您必须创建的 DNS 条目的相关信息。 其中包括相应操作所需的记录类型、FQDN、IP 地址和备注。

  - 网站摘要–网站摘要显示通过回答最初的调查问题或填写**设计网站**中的值所做的选择的概述。 还提供容量信息。
    
    <div>
    

    > [!NOTE]  
    > “站点摘要”页上的信息可针对每个设计进行自定义，可能不包含此处详细介绍的所有内容或信息。

    
    </div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中编辑网络配置图](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

