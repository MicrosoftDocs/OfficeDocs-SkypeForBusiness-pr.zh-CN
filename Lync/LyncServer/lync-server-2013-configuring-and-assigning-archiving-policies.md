---
title: Lync Server 2013：配置和分配存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db876d03f7322fae5f3a55f88708fe4165a20ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>在 Lync Server 2013 中配置和分配存档策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

在 Lync Server 2013 中，可以使用策略为驻留在 Lync Server 2013 上的用户启用和禁用对内部通信和外部通信的存档。 这包括以下存档策略：

  - 部署 Lync Server 2013 时默认创建的全局策略。

  - 您可以创建并用来指定如何针对特定站点或用户实施存档的可选站点级别和用户级别策略。

您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。 在 Lync Server 2013 控制面板中，可以使用 "**存档和监控**" 组的 "**存档策略**" 页来管理全局级别、站点级别和用户级别的策略。

<div>


> [!NOTE]  
> 若要控制存档的实现，您必须在存档配置中指定选项，例如，是否存档 IM 或会议、关键模式的用法和清除选项。 默认情况下，在全局存档配置或任意站点或池存档配置中未启用任何选项。 您应在存档配置中指定所有适当的选项，然后在存档策略中为内部或外部通信启用存档。 有关详细信息，请参阅 Operations 文档中的在<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 中管理存档配置选项（针对组织、网站和池</A>）。<BR>如果将 Lync Server 存储与 Exchange 2013 存储集成，则 Exchange 用户策略优先于 Lync Server 2013 存档策略，但仅适用于驻留在 Exchange 2013 的用户已将其邮箱置于就地保留状态的用户。



</div>

有关如何实施策略（包括策略的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。 有关如何在部署后管理策略的详细信息，请参阅操作文档中的在[Lync Server 2013 中管理内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中配置用于存档的全局策略](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [在 Lync Server 2013 中设置用于存档的网站策略](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [为 Lync Server 2013 中的用户设置存档策略](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

