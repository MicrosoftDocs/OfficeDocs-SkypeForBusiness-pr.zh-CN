---
title: 迁移阶段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e877afc67e5dea1bc2feada22e5bbbbe81e15139
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>迁移阶段

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

在 Lync Server 2013 中，您在网络上定义包含 Lync Server 2013 组件的网站。 站点是一组通过高速度、低延迟网络（例如单个局域网 (LAN) 或由高速光纤网络连接的两个网络）正确连接的计算机。

*前端池* 是一组配置相同的前端服务器，这些服务器协同工作来为公用组用户提供服务。 池为用户提供可伸缩性和故障转移功能。 池中的每台服务器必须运行一个或多个相同的服务器角色。 适用于小型组织的 Standard Edition 服务器还定义了一个池，并在一台服务器上运行。 这使您能够以较低的成本获取 Lync Server 2013 功能，但不提供真正的高可用性解决方案。

以下阶段介绍了从 Lync Server 2010 迁移到 Lync Server 2013 的池过程。 对于包含多个池的多个站点，每个池都应遵循此分阶段方法。

1.  [第1阶段：从 Lync Server 2010 规划迁移](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [第2阶段：准备迁移](phase-2-prepare-for-migration.md)

3.  [第3阶段：部署 Lync Server 2013 试点池](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [第4阶段：将测试用户移动到引导池](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [第5阶段：将 Lync Server 2013 边缘服务器添加到引导池](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [第6阶段：从试点部署移动到生产环境](phase-6-move-from-pilot-deployment-into-production.md)

7.  [第7阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)

8.  [第8阶段：停止旧版池](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

