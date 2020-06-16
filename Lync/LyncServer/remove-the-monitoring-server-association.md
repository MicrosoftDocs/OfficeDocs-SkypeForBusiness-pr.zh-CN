---
title: 删除监控服务器关联
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aa78a49686ca555fdbc26d3ffd4953d88d64a95
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>删除监控服务器关联

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

若要删除监视服务器，您需要更改或清除关联的前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器上的依赖项。 您可以编辑前端池、前端服务器、Survivable 分支设备和 Survivable 分支服务器的属性以删除依赖项。 清除依赖项并在拓扑生成器中删除服务器后，系统会通知拓扑生成器中关联的数据库存储对象也将被删除。

<div>

## <a name="to-remove-the-monitoring-server-association"></a>删除监控服务器关联

1.  打开 Lync Server 2013 前端服务器，打开拓扑生成器。

2.  导航到 "Lync Server 2010" 节点。

3.  在拓扑生成器中，根据在其中定义监视服务器的位置扩展**Enterprise Edition 前端池**、 **Standard edition 前端服务器**或**分支站点**。

4.  如果你有与 Survivable 分支服务器相关联的，请展开 "**分支站点**"，展开分支站点名称，然后展开 " **Survivable 分支设备**"。
    
    <div>
    

    > [!NOTE]  
    > 用户界面中的<STRONG>Survivable 分支设备</STRONG>适用于 Survivable 分支服务器和 Survivable 分支设备。

    
    </div>

5.  右键单击与监视服务器关联的池、服务器或设备，然后单击 "**编辑属性**"。

6.  在“编辑属性”**** 中，在“常规”**** 的“关联”**** 下，清除“关联监控服务器”**** 复选框，然后单击“确定”****。

7.  对与监视服务器关联的任何其他池、服务器或设备重复上一步骤。

8.  右键单击监视服务器，然后单击 "**删除**"。

9.  在“删除相关存储”**** 上，单击“确定”****。

10. 发布拓扑，检查复制状态，并根据需要运行 Lync Server 部署向导。

</div>

</div>

<span> </span>

</div>

</div>

</div>

