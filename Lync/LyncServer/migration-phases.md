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
ms.openlocfilehash: 76719513d3b9df6b3259efef57fc0bd5ae94050f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>迁移阶段

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-17_

在 Lync Server 2013 中，你可以在网络上定义包含 Lync Server 2013 组件的网站。 站点是一组计算机，这些计算机通过高速、低延迟网络连接，如单个局域网（LAN）或通过高速光纤网络连接的两个网络。

*前端池*是一组前端服务器，这些服务器配置相同，并且协同工作以提供一组通用用户的服务。 池为你的用户提供了可伸缩性和故障转移功能。 池中的每台服务器必须运行一个或多个相同的服务器角色。 适用于小型组织的标准版服务器还定义了一个池并在单个服务器上运行。 这使您能够以较低的成本获得 Lync Server 2013 功能，但不提供真正高可用性的解决方案。

以下阶段介绍从 Lync Server 2010 到 Lync Server 2013 的池迁移过程。 对于包含多个池的多个网站，每个单独的池应遵循这种分段方法。

1.  [第1阶段：规划从 Lync Server 2010 的迁移](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [第 2 阶段：准备迁移](phase-2-prepare-for-migration.md)

3.  [第3阶段：部署 Lync Server 2013 试验池](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [第4阶段：将测试用户移动到试验池](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [第5阶段：将 Lync Server 2013 边缘服务器添加到试验池](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [第 6 阶段：从试点部署移动到生产中](phase-6-move-from-pilot-deployment-into-production.md)

7.  [第 7 阶段：完成迁移后任务](phase-7-complete-post-migration-tasks.md)

8.  [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

