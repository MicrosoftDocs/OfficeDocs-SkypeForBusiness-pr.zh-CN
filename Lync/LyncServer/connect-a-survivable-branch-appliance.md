---
title: 连接 Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a>连接 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

每个 Survivable 分支装置 (SBA) 都与一个前端池相关联, 该池充当 SBA 的备份注册机构。 当将前端池迁移到 Lync Server 2013 时, SBA 必须在池升级时与 Lync Server 2010 前端池解除关联, 一旦池迁移到 Lync Server 2013 后, SBA 可以与升级的前端池重新关联。 这包括从拓扑生成器中的旧 Lync Server 2010 拓扑中删除 SBA, 然后将 SBA 添加到 Lync Server 2013 拓扑。 驻留在旧 Lync Server 2010 SBA 上的用户必须首先将其移动到另一个前端池, 然后才能从拓扑结构中删除 SBA。 一旦将 SBA 添加到 Lync Server 2013 拓扑, 这些用户就可以移回 SBA。 下面总结了这些步骤:

1.  将驻留在旧版 SBA Lync Server 2010 的分支用户移动到另一个前端池。

2.  从旧版 Lync Server 2010 拓扑中删除 SBA, 以将现有的前端池作为备份注册机构断开连接。

3.  将 SBA 添加到 Lync Server 2013 拓扑, 并将此新的前端池配置为备份注册机构。

4.  将分支用户移动到新的 Lync Server 2013 SBA。

**将 Lync Server 2010 SBA 分支网站添加到拓扑**

1.  打开**拓扑生成器**。

2.  在左窗格中, 右键单击 "**分支站点**", 然后单击 "**新建分支站点**"。

3.  在 "**定义新分支网站**" 对话框中, 单击 "**名称**", 然后键入分支网站的名称。

4.  可选单击 "**说明**", 然后为分支网站键入有意义的说明。

5.  单击" **下一步**"。

6.  可选在 "下一步**定义新分支站点**" 对话框中, 执行下列任一操作:
    
    1.  单击 "**城市**", 然后键入分支站点所在城市的名称。
    
    2.  单击 "**状态/区域**", 然后键入分支站点所在的省/市/自治区或地区的名称。
    
    3.  单击 "**国家/地区代码**", 然后键入分支站点所在的国家/地区的两位数呼叫代码。

7.  单击 "**下一步**", 然后执行下列操作之一:
    
    1.  如果您在此站点使用 Lync 2010 Survivable 分支设备或服务器, 请务必取消选中 "**关闭此向导时打开新 Survivable 向导**" 选项。 单击“**完成**”。

8.  要将旧版 Lync Server 2010 SBA 关联到 Lync Server 2013 前端池, 请执行以下操作:
    
    1.  展开已创建的分支站点。
    
    2.  右键单击 " **Lync Server 2010** ", 然后单击 "**新建**"。
    
    3.  单击 " **Survivable 分支装置 ...** "

9.  按照向导中打开的说明进行操作。 有关向导项的信息, 请参阅[在 Lync Server 2013 中定义 Survivable 分支装置或服务器](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2010 Survivable 分支设备只能与 Lync Server 2010 Monitoring Store 相关联。

    
    </div>

10. 如果未在此网站使用 Survivable 分支装置或服务器, 请清除 "**关闭此向导时打开新的 Survivable 向导**" 复选框, 然后单击 "**完成**"。

11. 对要添加到拓扑中的每个分支网站重复上述步骤。

</div>

<span> </span>

</div>

</div>

</div>

