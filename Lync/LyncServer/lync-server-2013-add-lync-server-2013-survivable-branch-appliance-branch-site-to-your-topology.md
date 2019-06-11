---
title: 将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83ae19b3683b725db64b2f598eb6fc3d182bac17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-07_

Microsoft Lync Server 2013 Survivable 分支装置 (SBA) 无法与 Microsoft Lync Server 2010 前端池关联作为备份注册机构。 SBA 必须与 Microsoft Lync Server 2013 前端池相关联。 这些步骤假设 Microsoft Lync Server 2013 SBA。 在中心站点执行此过程。

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>将分支站点添加到 Microsoft Lync Server 2013 SBA 到拓扑

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在控制台树中, 展开中心网站, 展开 "**分支网站**", 然后单击 "**新建分支站点**"。

3.  在 "**定义新分支网站**" 对话框中, 单击 "**名称**", 然后键入新分支网站的名称。

4.  可选单击 "**说明**", 然后为分支网站键入有意义的说明。

5.  单击" **下一步**"。

6.  可选在 "下一步**定义新分支站点**" 对话框中, 执行下列任一操作:
    
      - 单击 "**城市**", 然后键入分支站点所在城市的名称。
    
      - 单击 "**状态/区域**", 然后键入分支站点所在的省/市/自治区或地区的名称。
    
      - 单击 "**国家/地区代码**", 然后键入分支站点所在的国家/地区的两位数呼叫代码。

7.  单击 "**下一步**", 然后执行下列操作之一:
    
      - 如果在此网站上使用 Survivable 分支装置或 Survivable 分支服务器, 请确保选中 "**此向导关闭时打开新的 Survivable 向导**" 复选框。
    
      - 如果你未在此网站上使用 Survivable 分支装置或 Survivable 分支服务器, 请清除 "**关闭此向导时打开新的 Survivable 向导**" 复选框。
    
      - 单击 "**完成**", 然后按照向导中打开的说明进行操作。 有关向导项的信息, 请参阅[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。

8.  对要添加到拓扑中的每个分支站点重复上述步骤。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[在 Lync Server 2013 中为分支站点定义 PSTN 网关](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中配置不使用 "媒体旁路" 的主干](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

