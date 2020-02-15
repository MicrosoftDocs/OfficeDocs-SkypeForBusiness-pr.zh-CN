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
ms.openlocfilehash: c4f4f5ef6dfe595c87745571d061d104916067c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>在 Lync Server 2013 中定义和配置拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-14_

您可以使用拓扑生成器定义和配置拓扑。 拓扑生成器不要求您是本地 Administrators 组的成员，也不要求是权限域组（如 Domain Admins）的成员。 您能够以标准用户身份定义拓扑。 因第一次使用而启动拓扑生成器并随后编辑会话时，系统会提示您要使拓扑生成器加载当前配置文档的位置。 选项如下所示：

  - 从现有部署下载拓扑

  - 从本地文件打开拓扑

  - 新建拓扑

如果已经定义了一个拓扑并已建立了中央管理存储，则应选择从现有部署下载拓扑。 拓扑生成器将读取数据库并检索当前的定义。 如果您有一个现有的中央管理存储，则应始终选择此选项。

如果尚未建立中央管理存储，并且想要编辑以前保存的配置，则应选择从本地文件中打开拓扑。 将要打开的文件就是以前会话中保存的配置文件。 可以使用此选项编辑以前保存的拓扑。

<div>


> [!WARNING]  
> 如果您已有发布的拓扑，则不应加载本地配置文件，而应选择从现有部署下载拓扑。



</div>

如果要创建新的拓扑生成器配置，请选择创建新的拓扑。 以前保存的设计不会被覆盖，除非选择将其另存为以前设计会话中创建的同一文件。

在上述每个选项中，系统都会提示您提供存储拓扑生成器配置文件的位置。 文件的位置可以是本地位置、已建立文件共享上的共享位置或可移动介质。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 拓扑生成器中定义和配置拓扑](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [在 Lync Server 2013 中为灾难恢复部署配对的前端池](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [在 Lync Server 2013 中部署 SQL 镜像以实现后端服务器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [在 Lync Server 2013 中编辑或配置简单 Url](lync-server-2013-edit-or-configure-simple-urls.md)

  - [在 Lync Server 2013 中选择中央管理服务器](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

