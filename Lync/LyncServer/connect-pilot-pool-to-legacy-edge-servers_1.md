---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b83877505bfc9c2accc2057a9ebb1fb62355b3d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>将试点池连接到旧 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

部署 Lync Server 2013 后，未配置此网站的联合身份验证路由。 为了使用 Office 通信服务器 2007 R2 使用的联盟路由，Lync Server 2013 必须配置为使用此路由。

若要使 Lync Server 2013 网站能够使用 BackCompatSite 的控制器和边缘服务器，请使用拓扑生成器来关联旧版边缘池。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓扑生成器关联旧式边缘池

1.  在拓扑生成器中打开试点池拓扑。

2.  选择你的 Lync Server 2013 网站。

3.  在“操作”**** 菜单上，单击“编辑属性”****。

4.  在 "**站点联合路由分配**" 下，选择 "**启用 SIP 联盟**"，然后选择 Office 通信服务器 2007 R2 控制器或 Office 通信服务器 2007 r2 边缘服务器（如果未列出控制器）。
    
    !["编辑属性" 对话框（"联合路由" 页）](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg ""编辑属性" 对话框（"联合路由" 页）")  

5.  单击“确定”**** 关闭“编辑属性”**** 页。

6.  在拓扑生成器中，在 "Lync Server 2013" 节点下，导航到**Standard edition server**或**Enterprise Edition 前端池**，右键单击该池，然后单击 "**编辑属性**"。

7.  在“关联”**** 下，选中“关联边缘池(用于媒体组件)”**** 旁的复选框。

8.  从列表中选择用于 BackCompatSite 的边缘服务器接口。
    
    !["编辑属性" 对话框（"常规" 页）](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg ""编辑属性" 对话框（"常规" 页）")  

9.  单击“确定”**** 关闭“编辑属性”**** 页。

10. 在“拓扑生成器”**** 中，选择最顶层节点 **Lync Server**。

11. 从“操作”**** 菜单中，单击“发布拓扑”****，然后单击“下一步”****。

12. “发布向导”**** 完成时，单击“完成”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

