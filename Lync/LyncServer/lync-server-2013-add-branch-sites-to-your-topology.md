---
title: Lync Server 2013：将分支站点添加到您的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d4e024ed5cdb29bb8a8a4170b89399f955254bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a>在 Lync Server 2013 中向拓扑添加分支站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

分支站点代表通过 WAN 链路连接到总部的物理分支办公室。要将分支站点添加到 Lync 拓扑，请在中央站点执行以下过程。

<div>

## <a name="to-add-branch-sites-to-your-topology"></a>向拓扑中添加分支站点

1.  依次单击“开始”****、“所有程序”****、“Microsoft Lync Server”****，然后单击“Lync Server 拓扑生成器”****。

2.  在控制台树中，展开中央站点，右键单击“分支站点”****，然后单击“新建分支站点”****。

3.  在“定义新的分支站点”**** 对话框中，单击“名称”****，然后键入分支站点的名称。

4.  （可选）单击“说明”****，然后为分支站点键入有一定含义的说明。

5.  单击“下一步”****。

6.  （可选）在下一个“定义新的分支站点”**** 对话框中，执行以下任一操作：
    
      - 单击“市/县”****，然后键入分支站点所在的市/县的名称。
    
      - 单击“国家/地区”****，然后键入分支站点所在的国家或地区的名称。
    
      - 单击“国家/地区代码”****，然后键入分支站点所在的国家/地区的两位数呼叫代码。

7.  单击“下一步”****，然后执行以下操作之一：
    
      - 如果在此网站上使用 Survivable 分支设备或服务器，请确保选中 "在**此向导关闭时打开新 Survivable 向导**" 复选框，单击 "**完成**"，然后按照向导中打开的说明进行操作。 有关向导项的信息，请参阅[在 Lync Server 2013 中定义 Survivable 分支设备或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
      - 如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭后将打开新建 Survivable 向导”**** 复选框，然后单击“完成”****。

8.  对要添加到拓扑的每个分支站点重复之前的步骤。

**下一步：**

对于 Survivable 分支装置或服务器：[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

对于非复原 PSTN 连接：在 lync server 2013 中为[分支站点定义 PSTN 网关](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)，[在 lync server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)，或[在 lync server 2013 中配置不使用媒体旁路的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

