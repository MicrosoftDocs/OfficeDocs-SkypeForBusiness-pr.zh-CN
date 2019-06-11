---
title: Lync Server 2013：向拓扑添加分支站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029627060ff03b804d0d2f76f40fdd4052f0d1c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>在 Lync Server 2013 中向拓扑添加分支站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-05_

分支站点表示通过 WAN 链接连接到您的主办公室的物理分支机构。 若要将分支站点添加到 Lync 拓扑中, 请在中心站点执行此过程。

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>将分支站点添加到拓扑

1.  单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync 服务器**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在控制台树中, 展开中心网站, 右键单击 "**分支网站**", 然后单击 "**新建分支站点**"。

3.  在 "**定义新分支网站**" 对话框中, 单击 "**名称**", 然后键入分支网站的名称。

4.  可选单击 "**说明**", 然后为分支网站键入有意义的说明。

5.  单击" **下一步**"。

6.  可选在 "下一步**定义新分支站点**" 对话框中, 执行下列任一操作:
    
      - 单击 "**城市**", 然后键入分支站点所在城市的名称。
    
      - 单击 "**状态/区域**", 然后键入分支站点所在的省/市/自治区或地区的名称。
    
      - 单击 "**国家/地区代码**", 然后键入分支站点所在的国家/地区的两位数呼叫代码。

7.  单击 "**下一步**", 然后执行下列操作之一:
    
      - 如果您在此站点使用 Survivable 分支装置或服务器, 请确保选中 "**此向导关闭时打开新的 Survivable 向导**" 复选框, 单击 "**完成**", 然后按照向导中打开的说明进行操作。 有关向导项的信息, 请参阅[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
      - 如果未在此网站使用 Survivable 分支装置或服务器, 请清除 "**关闭此向导时打开新的 Survivable 向导**" 复选框, 然后单击 "**完成**"。

8.  对要添加到拓扑中的每个分支站点重复上述步骤。

**下一步:**

对于 Survivable 分支装置或服务器:[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

对于非复原 PSTN 连接:[在 lync server 2013 中定义分支站点的 PSTN 网关](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), 在[lync server 2013 中使用 "媒体绕过" 配置主干](lync-server-2013-configure-a-trunk-with-media-bypass.md)网, 或者[在 lync server 中配置不使用 "媒体旁路" 的 trunk 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

