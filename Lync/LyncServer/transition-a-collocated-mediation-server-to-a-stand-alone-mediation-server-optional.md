---
title: 将并置中介服务器转换为独立的中介服务器（可选）
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ce0228edacba502161c4d44a6a94b38cede6655
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755686"
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

4.  On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.

5.  选择新中介服务器会将入站呼叫路由到的下一跃点前端服务器池，然后单击“下一步”****。

6.  选择中介服务器要使用的边缘池，然后单击“下一步”****。

7.  On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.

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

