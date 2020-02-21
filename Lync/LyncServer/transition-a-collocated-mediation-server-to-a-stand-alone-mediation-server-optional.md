---
title: 将并置中介服务器转换为独立的中介服务器（可选）
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4140732fd5d091f3ed03e2dadd2f827a24531e9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>将并置中介服务器转换为独立的中介服务器（可选）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

使用下面的过程可将在 Standard Edition Server 或前端池上并置的中介服务器转换为单站点部署的独立中介服务器。

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>将并置中介服务器转换为独立中介服务器

1.  从拓扑生成器中打开现有拓扑。

2.  在左窗格中，导航到“中介池”****。

3.  右键单击“中介池”****，然后选择“新建中介服务器”****。

4.  在“定义新的中介池”**** 页上，提供新中介服务器池的 FQDN。另外，选择该池是单服务器池还是多服务器池，然后单击“下一步”****。

5.  选择新中介服务器会将入站呼叫路由到的下一跃点前端服务器池，然后单击“下一步”****。

6.  选择中介服务器要使用的边缘池，然后单击“下一步”****。

7.  在“指定 PSTN 网关”**** 页上，将以前的 PSTN 网关与中介服务器相关联。选择该网关，然后单击“添加”****。

8.  单击“完成”**** 以关闭“定义新的中介池”**** 向导。

9.  从**拓扑生成器**中，选择顶部节点**Lync Server 2013**。

10. 从“操作”**** 窗格中，选择“发布拓扑”**** 并完成向导。

11. 按照部署文档中的 "在[Lync server 2013 中安装用于中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)" 中的步骤操作，将文件安装到新中介服务器上。

12. 在中介服务器上安装文件后，返回拓扑生成器，并在左窗格中导航到池。

13. 右键单击该池，然后选择“编辑属性”****。

14. 在“中介服务器”**** 下，清除“并置中介服务器已启用”**** 复选框，然后单击“确定”****。

15. 从**拓扑生成器**中，选择顶部节点**Lync Server 2013**。

16. 从“操作”**** 菜单中，选择“发布拓扑”**** 并完成向导。

</div>

</div>

<span> </span>

</div>

</div>

</div>

