---
title: Lync Server 2013：在 Lync Server 中设置用于存档的用户策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78a30684619a67fc1e48f3692a2bc40ccae55b14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中设置用户策略以进行存档

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-10_

如果为驻留在 Lync Server 2013 上的特定用户启用或禁用存档，则需要创建和配置一个或多个用户策略，然后将适当的策略应用于特定用户或用户组。 用户策略会覆盖网站和全局策略，但仅适用于驻留在 Lync Server 2013 上的用户。

用户始终驻留在 Lync Server 中。 如果启用了 Microsoft Exchange 集成，则邮箱位于 Microsoft Exchange Server 2013 中的用户不需要在 Lync Server 中管理其存档策略。 将通过 Exchange 就地保留来管理这些具有存档的用户。

有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 如果为您的部署启用了 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管在 Exchange 2013 上的用户启用存档。 为这些用户启用存档要求他们将其邮箱置于就地保留状态。 有关详细信息，请参阅部署文档中的<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A>。<BR>在启用存档之前，应在存档配置中指定所有适当选项。 有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中创建和配置用于存档的用户策略](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [在 Lync Server 2013 中将 Lync Server 存档策略应用于用户](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

