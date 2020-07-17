---
title: 连接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fcba962129353ddeb5e5f4c77520cf6d127733
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>连接 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

每个 Survivable 分支设备（SBA）都与一个前端池相关联，该前端池充当 SBA 的备份注册器。 当将前端池迁移到 Lync Server 2013 时，在升级池时，SBA 必须与 Lync Server 2010 前端池解除关联，一旦将池迁移到 Lync Server 2013，则 SBA 可以与升级后的前端池重新关联。 这包括从拓扑生成器中的旧版 Lync Server 2010 拓扑中删除 SBA，然后将 SBA 添加到 Lync Server 2013 拓扑。 驻留在旧 Lync Server 2010 SBA 上的用户必须先移到另一个前端池，然后才能从拓扑中删除 SBA。 将 SBA 添加到 Lync Server 2013 拓扑后，这些用户即可移回 SBA。 这些步骤概括如下：

1.  将驻留在旧版 SBA Lync Server 2010 的分支用户移动到另一个前端池。

2.  从旧版 Lync Server 2010 拓扑中删除 SBA，以将现有的前端池作为备份注册器断开连接。

3.  将 SBA 添加到 Lync Server 2013 拓扑，并将此新的前端池配置为备份注册器。

4.  将分支用户移动到新的 Lync Server 2013 SBA。

**将 Lync Server 2010 SBA 分支站点添加到您的拓扑**

1.  打开“拓扑生成器”****。

2.  在左窗格中右键单击“分支站点”****，然后单击“新建分支站点”****。

3.  在“定义新的分支站点”**** 对话框中，单击“名称”****，然后键入分支站点的名称。

4.  （可选）单击“说明”****，然后为分支站点键入有一定含义的说明。

5.  单击“下一步”****。

6.  （可选）在下一个“定义新的分支站点”**** 对话框中，执行以下任一操作：
    
    1.  单击“市/县”****，然后键入分支站点所在的市/县的名称。
    
    2.  单击“国家/地区”****，然后键入分支站点所在的国家或地区的名称。
    
    3.  单击“国家/地区代码”****，然后键入分支站点所在的国家/地区的两位数呼叫代码。

7.  单击“下一步”****，然后执行以下操作之一：
    
    1.  如果在此站点使用的是 Lync 2010 Survivable Branch Appliance 或 Lync 2010 Survivable Branch Server，确保取消选中“此向导关闭后将打开新建 Survivable 向导”**** 选项。单击“完成”****。

8.  若要将旧版 Lync Server 2010 SBA 与 Lync Server 2013 前端池相关联，请执行以下操作：
    
    1.  展开已创建的分支站点。
    
    2.  右键单击“Lync Server 2010”****，然后单击“新建”****。
    
    3.  单击“Survivable Branch Appliance…”****

9.  按照打开的向导中的说明执行操作。 有关向导项的信息，请参阅[在 Lync Server 2013 中定义 Survivable 分支设备或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2010 Survivable 分支设备仅可与 Lync Server 2010 监视存储关联。

    
    </div>

10. 如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭后将打开新建 Survivable 向导”**** 复选框，然后单击“完成”****。

11. 对要添加到拓扑的每个分支站点重复之前的步骤。

</div>

<span> </span>

</div>

</div>

</div>

