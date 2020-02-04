---
title: 管理内部和外部通信的存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff349fcb7b012ed2604c4e75fe0f4bdd5ed99fc6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>在 Lync Server 2013 中管理内部和外部通信的存档

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-09_

在 Lync Server 2013 中，如果你不使用 Microsoft Exchange 集成，或者你的用户未托管在 Exchange 2013 上，并且你的邮箱放在 Exchange 上，则可以使用存档策略来启用和禁用对内部通信和外部通信的存档就地保留。 这包括以下存档策略：

  - 部署 Lync Server 2013 时默认创建的全局策略。

  - 可创建和使用的可选网站级和用户级策略，用于指定如何为特定网站或用户实现存档。

你在部署存档时最初设置存档策略，但你可以在部署后更改、添加和删除策略。 在 Lync Server 2013 控制面板中，你可以使用 "**存档和监视**" 组的 "**存档策略**" 页面管理全局级别、网站级别和用户级别的策略。 如果你将 Lync Server 存储与 Exchange 2013 存储集成，Exchange 用户策略将优先于 Lync Server 2013 存档策略。

有关如何实施策略的详细信息（包括策略的层次结构），请参阅规划文档、部署文档或操作文档中的在[Lync Server 2013 中的存档的工作原理](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]
> 若要控制存档的实现，必须指定存档配置中的选项，例如，是存档 IM 还是会议、使用关键模式和清除选项。 默认情况下，全局存档配置或任何网站或池存档配置中均未启用任何选项。 应在存档配置中指定所有适当的选项，然后才能在存档策略中启用内部或外部通信的存档。 有关详细信息，请参阅在<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 中为你的组织、网站和池在操作文档中管理存档配置选项</A>。<BR>如果为你的部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否为托管于 Exchange 2013 的用户启用存档，并将其邮箱置于原地保留。 有关详细信息，请参阅在部署文档中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时在 Lync Server 2013 中设置存档策略</A>。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中创建存档策略，以启用或禁用特定网站或用户的内部或外部通信的存档](lync-server-2013-create-archiving-policy-sites-users.md)

  - [在 Lync Server 2013 中更改存档策略以启用或禁用组织、网站或用户的内部或外部通信的存档](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [将存档策略应用于 Lync Server 2013 中的用户](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [使用 Exchange Server 集成时，在 Lync Server 2013 中设置存档策略](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [在 Lync Server 2013 中删除存档策略](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

