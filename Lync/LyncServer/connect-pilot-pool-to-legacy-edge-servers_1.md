---
title: 将试点池连接到旧 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect pilot pool to legacy Edge Servers
ms:assetid: 9ed13c41-f3ab-4e1d-beb6-a00152c541e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205136(v=OCS.15)
ms:contentKeyID: 48185003
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40d54a7432451901a32cb8e31d201ef732a731bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>将试点池连接到旧 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-02_

部署 Lync Server 2013 后, 未配置此网站的联盟路由。 为了使用由 Office 通信服务器 2007 R2 使用的联盟路由, Lync Server 2013 必须配置为使用此路由。

若要使 Lync Server 2013 网站能够使用 BackCompatSite 的 Director 和 Edge 服务器, 请使用拓扑生成器关联旧版 Edge 池。

<div>

## <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>使用拓扑生成器关联旧式边缘池

1.  在拓扑生成器中打开 "引导池" 拓扑。

2.  选择您的 Lync Server 2013 网站。

3.  在 "**操作**" 菜单上, 单击 "**编辑属性**"。

4.  在 "**站点联合路由分配**" 下, 选择 "**启用 SIP 联盟**", 然后选择 Office 通信服务器 2007 r2 控制器, 如果未列出 Director, 则选择 "Office 通信服务器 2007 r2 Edge 服务器"。
    
    !["编辑属性" 对话框, "联盟路由" 页面](images/JJ205136.bc13014b-3578-4d9e-9ff7-bdd09130b676(OCS.15).jpg "\"编辑属性\" 对话框, \"联盟路由\" 页面")  

5.  单击 **"确定"** 以关闭 "**编辑属性**" 页面。

6.  在拓扑生成器中, 在 Lync Server 2013 节点下, 导航到**标准版服务器**或**企业版前端池**, 右键单击该池, 然后单击 "**编辑属性**"。

7.  在 "**关联**" 下, 选中 "**关联边缘池" (对于媒体组件)** 旁边的复选框。

8.  从列表中选择 BackCompatSite 的边缘服务器接口。
    
    !["编辑属性" 对话框, "常规" 页面](images/JJ205136.75045212-03ca-4b82-8337-5dacb487094f(OCS.15).jpg "\"编辑属性\" 对话框, \"常规\" 页面")  

9.  单击 **"确定"** 以关闭 "**编辑属性**" 页面。

10. 在**拓扑生成器**中, 选择最上面的节点 " **Lync 服务器**"。

11. 从 "**操作**" 菜单中, 单击 "**发布拓扑**", 然后单击 "**下一步**"。

12. **发布向导**完成后, 单击 "**完成**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

