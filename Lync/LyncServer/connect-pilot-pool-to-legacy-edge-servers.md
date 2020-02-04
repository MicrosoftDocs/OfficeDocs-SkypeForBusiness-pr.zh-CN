---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: c3b67220-5705-47f6-852e-415204f3626c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721875(v=OCS.15)
ms:contentKeyID: 49733808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447a0ead887b8283aa2701963a0107ef318bb312
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>将试点池连接到旧 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-29_

部署 Lync Server 2013 后，您需要为您的网站配置联盟路由。 为了使用 Lync Server 2010 正在使用的联盟路由，Lync Server 2013 必须配置为使用此路由。

若要使 Lync Server 2013 网站使用 Lync Server 2010 部署的 Director 和 Edge 服务器，请使用拓扑生成器关联旧版 Edge 池。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓扑生成器关联旧式边缘池

1.  打开**拓扑生成器**。

2.  选择您的网站，它位于**Lync Server**节点正下方。

3.  在 "**操作**" 菜单上，单击 "**编辑属性**"。

4.  在左窗格中，选择 "**联盟路由**"。

5.  在 "**站点联合路由分配**" 下，选择 "**启用 SIP 联盟**"，然后选择 lync Server 2010 控制器或 Lync server 2010 Edge 服务器（如果未列出 Director）。
    
    !["编辑属性"、"联盟路由" 页面](images/JJ721875.5f1d04c3-c724-426d-b27d-3fe89c6c5cfb(OCS.15).jpg ""编辑属性"、"联盟路由" 页面")  

6.  单击 **"确定"** 以关闭 "**编辑属性**" 页面。

7.  在拓扑生成器中，在 Lync Server 2013 节点下，导航到**标准版服务器**或**企业版前端池**，右键单击该池，然后单击 "**编辑属性**"。

8.  在 "**关联**" 下，选中 "**关联边缘池" （对于媒体组件）** 旁边的复选框。

9.  从列表中，选择旧式边缘服务器。
    
    !["编辑属性" 对话框，选择旧版边缘](images/JJ721875.feae8156-540e-4804-bb0a-2b5736ec2900(OCS.15).jpg ""编辑属性" 对话框，选择旧版边缘")  

10. 单击 **"确定"** 以关闭 "**编辑属性**" 页面。

11. 在**拓扑生成器**中，选择最上面的节点 " **Lync 服务器**"。

12. 从 "**操作**" 菜单中，单击 "**发布拓扑**"，然后单击 "**下一步**"。

13. **发布向导**完成后，单击 "**完成**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

