---
title: Lync Server 2013：为用户设置存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a24bef13fe99178663f5655da794e6663ab8aeb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a>为 Lync Server 2013 中的用户设置存档策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

通过为用户创建和配置存档策略、然后将该策略应用于特定用户或用户组，可为特定用户启用或禁用存档。 用户策略会覆盖任何全局策略或站点策略。 仅当您不使用 Microsoft Exchange 集成时，或者，如果您使用 Microsoft Exchange 集成，但某些用户不驻留在 Exchange 2013 上，并且其邮箱置于就地保留状态，则存档策略才适用。

有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅[在 Lync Server 2013](lync-server-2013-how-archiving-works.md)规划文档、部署文档或操作文档中存档的工作原理。

<div>


> [!NOTE]  
> 如果为您的部署启用了 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管在 Exchange 2013 上的用户启用存档，并将其邮箱置于就地保留状态。 有关详细信息，请参阅部署文档中的<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A>。<BR>在存档策略中启用内部或外部通信的存档之前，应在存档配置中指定所有适当选项。 有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中设置用户策略以进行存档](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [在使用 Exchange Server 集成时，在 Lync Server 2013 中设置存档策略](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

