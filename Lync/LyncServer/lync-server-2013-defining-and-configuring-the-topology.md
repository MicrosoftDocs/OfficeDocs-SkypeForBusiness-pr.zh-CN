---
title: Lync Server 2013：定义和配置拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8430ec5cc8b362aa78f97afc24ab0e588c7bc650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中定义和配置拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-14_

使用拓扑生成器定义和配置拓扑。 拓扑生成器不要求你是本地管理员组或权限域组（如域管理员）的成员。 你可以将拓扑定义为标准用户。 在首次使用时启动拓扑生成器和后续编辑会话时，系统会提示你输入希望拓扑生成器加载当前配置文档的位置。 选项如下所示：

  - 从现有部署下载拓扑

  - 打开本地文件中的拓扑

  - 新拓扑

如果已定义拓扑，并且已建立中央管理存储，则应选择从现有部署下载拓扑。 拓扑生成器将读取数据库并检索当前定义。 如果您有一个现有的中央管理存储，则应始终选择此选项。

如果尚未建立中央管理存储，并且想要编辑以前保存的配置，则应选择从本地文件打开拓扑。 将打开的文件将是以前会话中保存的配置文件。 可以使用此选项编辑以前保存的拓扑。

<div>


> [!WARNING]  
> 如果已有已发布的拓扑，则不应加载本地配置文件。 你应该选择从现有部署下载拓扑。



</div>

如果要创建新的拓扑生成器配置，请选择 "创建新拓扑"。 除非选择将以前保存的设计保存为在早期的设计会话中创建的同一文件，否则不会覆盖以前保存的设计。

在每个选项中，系统将提示你提供存储拓扑生成器配置文件的位置。 文件的位置可以是本地位置、已建立的文件共享上的共享位置或可移动媒体。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 拓扑生成器中定义和配置拓扑](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [在 Lync Server 2013 中针对灾难恢复部署配对的前端池](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [在 Lync Server 2013 中编辑或配置简单 URL](lync-server-2013-edit-or-configure-simple-urls.md)

  - [在 Lync Server 2013 中选择中央管理服务器](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

