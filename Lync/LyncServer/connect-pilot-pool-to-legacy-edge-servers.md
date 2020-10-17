---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d12a67b0ba102fdacea66b6196bafe32d89c9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503099"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>将试点池连接到旧 Edge Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-29_

部署 Lync Server 2013 后，需要为您的网站配置联盟路由。 为了使用 Lync Server 2010 正在使用的联盟路由，必须将 Lync Server 2013 配置为使用此路由。

若要使 Lync Server 2013 网站能够使用 Lync Server 2010 部署的控制器和边缘服务器，请使用拓扑生成器来关联旧版边缘池。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓扑生成器关联旧的边缘池

1.  打开**拓扑生成器**。

2.  选择位于 **Lync Server** 节点正下方的站点。

3.  在“操作”**** 菜单上，单击“编辑属性”****。

4.  在左侧窗格中，选择“联盟路由”****。

5.  在 " **站点联合路由分配**" 下，选择 " **启用 SIP 联盟**"，然后选择 lync server 2010 控制器，如果未列出控制器，则选择 Lync server 2010 边缘服务器。
    
    !["编辑属性"、"联盟路由" 页面](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg ""编辑属性"、"联盟路由" 页面")  

6.  单击“确定”**** 关闭“编辑属性”**** 页。

7.  在拓扑生成器中，在 "Lync Server 2013" 节点下，导航到 **Standard edition server** 或 **Enterprise Edition 前端池**，右键单击该池，然后单击 " **编辑属性**"。

8.  在“关联”**** 下，选中“关联边缘池(用于媒体组件)”**** 旁边的复选框。

9.  从列表中选择旧的边缘服务器。
    
    !["编辑属性" 对话框，选择旧版边缘](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg ""编辑属性" 对话框，选择旧版边缘")  

10. 单击“确定”**** 关闭“编辑属性”**** 页。

11. 在“拓扑生成器”**** 中，选择最顶层节点 **Lync Server**。

12. 从“操作”**** 菜单中，单击“发布拓扑”****，然后单击“下一步”****。

13. “发布向导”**** 完成时，单击“完成”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

