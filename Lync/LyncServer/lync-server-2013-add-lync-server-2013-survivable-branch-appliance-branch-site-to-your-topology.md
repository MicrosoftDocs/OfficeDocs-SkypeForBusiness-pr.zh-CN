---
title: 将 Lync Server 2013 Survivable 分支装置分支站点添加到您的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad708f2f37b95d970f9c9585730c015ff6798f6a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521459"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a>将 Lync Server 2013 Survivable 分支装置分支站点添加到您的拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-07_

Microsoft Lync Server 2013 Survivable 分支装置 (SBA) 不能与 Microsoft Lync Server 2010 前端池关联，作为备份注册器。 SBA 必须与 Microsoft Lync Server 2013 前端池相关联。 这些步骤假设 Microsoft Lync Server 2013 SBA。 请在中央站点执行此过程。

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a>将分支站点添加到 Microsoft Lync Server 2013 SBA 到您的拓扑

1.  启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在控制台树中，展开中央站点，再展开“分支站点”****，然后单击“新建分支站点”****。

3.  在“定义新的分支站点”**** 对话框中，单击“名称”****，然后键入新分支站点的名称。

4.  （可选）单击“说明”****，然后为分支站点键入有一定含义的说明。

5.  单击“下一步”****。

6.  （可选）在下一个“定义新的分支站点”**** 对话框中，执行以下任一操作：
    
      - 单击“市/县”****，然后键入分支站点所在的市/县的名称。
    
      - 单击“国家/地区”****，然后键入分支站点所在的国家或地区的名称。
    
      - 单击“国家/地区代码”****，然后键入分支站点所在的国家/地区的两位数呼叫代码。

7.  单击“下一步”****，然后执行以下操作之一：
    
      - 如果在此网站上使用的是 Survivable 分支设备或 Survivable 分支服务器，请确保选中 " **关闭此向导时打开新的 Survivable 向导** " 复选框。
    
      - 如果未在此站点上使用 Survivable 分支设备或 Survivable 分支服务器，请清除 " **关闭此向导时打开新的 Survivable 向导** " 复选框。
    
      - 单击“完成”****，然后按照打开的向导中的说明进行操作。 有关向导项的信息，请参阅 [在 Lync Server 2013 中定义 Survivable 分支设备或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。

8.  对要添加到拓扑的每个分支站点重复之前的步骤。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中定义 Survivable 分支设备或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[在 Lync Server 2013 中为分支站点定义 PSTN 网关](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[在 Lync Server 2013 中配置具有媒体旁路功能的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中配置无媒体旁路功能的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

