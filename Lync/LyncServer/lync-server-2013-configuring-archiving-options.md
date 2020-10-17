---
title: Lync Server 2013：配置存档选项
description: Lync Server 2013：配置存档选项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options
ms:assetid: b2f7f74d-e1ad-494e-9d46-5eb0efe5fb29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205182(v=OCS.15)
ms:contentKeyID: 48185158
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99d57f016d76f9ae6a538ef28663a4b4c965b0a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562518"
---
# <a name="configuring-archiving-options-in-lync-server-2013"></a>在 Lync Server 2013 中配置存档选项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-10_

在 Lync Server 2013 控制面板中，可以使用存档配置来指定如何实施存档。 这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

存档配置最初是在部署存档时设置的，但您可以在部署后更改、添加和删除这些配置。 在 Lync Server 2013 控制面板中，可以使用 "**存档和监控**" 组的 "**存档配置**" 页来管理全局级别、站点级别和池级别的配置。 有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的 [存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md) 。 有关如何在部署后管理配置的详细信息，请参阅 Operations 文档中的在 [Lync Server 2013 中管理存档配置选项（针对组织、网站和池](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) ）。

<div>


> [!NOTE]  
> 若要使用存档，您必须配置存档策略，以指定是为内部通信启用存档，还是为外部通信启用存档，还是对驻留在 Lync Server 2013 上的用户启用存档。 默认情况下，不会为内部或外部通信启用存档。 在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。 有关启用存档的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 中配置和分配存档策略</A> 。<BR>如果您的部署中的所有用户不使用 Microsoft Exchange 集成，则必须配置存档策略，以指定是为内部通信启用存档，还是对二者启用存档。 默认情况下，在使用 Lync Server 2013 存档数据库时，不会为内部或外部通信启用存档来存档数据。 在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。 有关启用存档以用于 Lync Server 2013 存档数据库的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync server 2013 中配置和分配存档策略</A> 。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中配置全局级别的存档选项](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [在 Lync Server 2013 中配置网站的存档选项](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [在 Lync Server 2013 中配置池的存档选项](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

