---
title: Lync Server 2013：附录 B：管理 Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b16d4c55197785a6df12ad2031dbd2e624501ebd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a>附录 B：在 Lync Server 2013 中管理 Survivable Branch Appliance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-18_

本主题介绍管理 Survivable 分支装置的过程。 具体而言，如何替换和重命名 Survivable 分支装置，以及如何更改 Survivable 分支设备关联的 Lync Server 2013 前端池。

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a>替换 Survivable 分支装置

1.  在 Survivable 分支设备上停止所有 Lync Server 2013 服务。 （请参阅 Survivable 分支装置供应商文档。）

2.  建议您使用从域中删除 Survivable 分支装置。

3.  删除 Active Directory 域服务中的 Survivable 分支装置计算机对象，方法是执行以下步骤：
    
      - 作为企业管理员组的成员登录到成员服务器。
    
      - 单击 "**开始**"，单击 "**管理工具**"，然后单击 " **Active Directory 用户和计算机**"。
    
      - 右键单击 "Survivable 分支装置" 对象，然后单击 "**删除**"。

4.  再次添加 Survivable 分支装置计算机对象。 （请参阅[在 Lync Server 2013 中将 Survivable 分支装置添加到 Active Directory](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)。）

5.  请等待 Active Directory 复制发生。

6.  打开 Lync Server 命令行管理程序，然后键入**Enable-CSTopology**。

7.  将新的 Survivable 分支设备连接到网络，然后按照[使用 Lync server 2013 部署 Survivable 分支设备或服务器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)中的步骤进行操作，并使用[lync server 2013 （分支站点任务）部署 Survivable 分支装置或服务器](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a>重命名 Survivable 分支装置

1.  将用户移动到中心网站。 有关详细信息，请参阅[在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。

2.  在 Survivable 分支设备上停止所有 Lync Server 2013 服务。 （请参阅 Survivable 分支装置供应商文档。）

3.  通过以下步骤从拓扑中删除 Survivable 分支设备：
    
      - 单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync 服务器**"，然后单击 " **Lync server 拓扑生成器**"。
    
      - 在控制台树中，展开 "**分支站点**"，单击 "Survivable 分支装置"，然后在操作窗格中单击 "**删除**"。

4.  从域中删除 Survivable 分支装置。

5.  通过执行以下步骤，在 Active Directory 中删除 Survivable 分支装置计算机对象：
    
      - 以企业管理员组的成员身份登录域控制器。
    
      - 单击 "**开始**"，单击 "**管理工具**"，然后单击 " **Active Directory 用户和计算机**"。
    
      - 右键单击 "Survivable 分支装置" 对象，然后单击 "**删除**"。

6.  将 Survivable 分支装置还原为出厂默认值。 （请参阅 Survivable 分支装置供应商文档。）

7.  按照[使用 Lync server 2013 部署 Survivable 分支设备或服务器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)中的步骤进行操作-中心站点任务和[使用 Lync Server 2013 部署 Survivable 分支装置或服务器（分支站点任务）](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)。

8.  将用户移动到重命名的 Survivable 分支装置。 有关详细信息，请参阅[在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a>更改 Survivable 分支设备关联的 Lync Server 前端池

1.  将用户从 Survivable 分支设备移动到中央站点上的 Lync Server 前端池。 有关详细信息，请参阅[在 Lync Server 2013 中将用户移动到另一个池](lync-server-2013-move-users-to-another-pool.md)。

2.  停止 Survivable 分支装置上的所有 Lync Server 服务。 （请参阅 Survivable 分支装置供应商文档）。

3.  通过执行以下步骤，更新 Survivable 分支设备关联的 Lync Server 前端池：
    
      - 单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync 服务器**"，然后单击 " **Lync server 拓扑生成器**"。
    
      - 展开 "**分支站点**"。
    
      - 右键单击要修改的 Survivable 分支装置对象，然后单击 "**编辑属性**"
    
      - 在 "复原" 下，选择 Survivable 分支装置将关联到的新前端池，然后单击 "**下一步**"。
    
      - 在控制台树中，右键单击新的 Survivable 分支装置，单击 "**拓扑**"，然后单击 "**发布**"。

4.  在 Survivable 分支设备上重新启动所有 Lync Server 服务。

5.  测试 Survivable 分支装置。 有关详细信息，请参阅[Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

6.  将用户从中央站点上的 Lync Server 前端池移动到 Survivable 分支装置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

