---
title: Lync Server 2013：配置存档选项
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
ms.openlocfilehash: 9aa49aceacbd5053ead1af6b881be87c74b2ea30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-in-lync-server-2013"></a>在 Lync Server 2013 中配置存档选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-10_

在 Lync Server 2013 "控制面板" 中，使用存档配置来指定如何实施存档。 这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 可创建和使用的可选网站级和池级配置，用于指定如何为特定网站或池实现存档。

你在部署存档时开始设置存档配置，但你可以在部署后更改、添加和删除配置。 在 Lync Server 2013 "控制面板" 中，可以使用 "**存档和监视**" 组的 "**存档配置**" 页来管理全局级别、网站级别和池级别的配置。 有关如何实现存档配置的详细信息，包括你可以指定哪些选项和存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。 有关如何在部署后管理配置的详细信息，请参阅操作文档中的[组织、网站和池的 Lync Server 2013 中的 "管理存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)"。

<div>


> [!NOTE]  
> 若要使用存档，必须配置存档策略以指定是为内部通信启用存档、对于外部通信还是对驻留在 Lync Server 2013 上的用户启用存档。 默认情况下，不会为内部或外部通信启用存档。 在任何策略中启用存档之前，应为你的部署指定相应的存档配置，并根据需要为特定的网站和池指定相应的存档配置，如本节所述。 有关启用存档的详细信息，请参阅部署文档中的<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">在 Lync Server 2013 中配置和分配存档策略</A>。<BR>如果你不为部署中的所有用户使用 Microsoft Exchange 集成，则必须配置存档策略，以指定是为内部通信还是在外部通信启用存档。 默认情况下，在使用 Lync Server 2013 存档数据库时，不会为内部或外部通信启用存档，以便存档数据。 在任何策略中启用存档之前，应为你的部署指定相应的存档配置，并根据需要为特定的网站和池指定相应的存档配置，如本节所述。 有关启用用于 Lync Server 2013 存档数据库的存档的详细信息，请参阅在部署文档中<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">配置和分配 Lync server 2013 中的存档策略</A>。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 的全局级别配置存档选项](lync-server-2013-configuring-archiving-options-at-the-global-level.md)

  - [在 Lync Server 2013 中配置网站的存档选项](lync-server-2013-configuring-archiving-options-for-a-site.md)

  - [在 Lync Server 2013 中配置池的存档选项](lync-server-2013-configuring-archiving-options-for-a-pool.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

