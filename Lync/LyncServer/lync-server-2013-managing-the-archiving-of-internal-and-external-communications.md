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
ms.openlocfilehash: 14df9a4472d920e5b583e4d2abe2deeb3fba0c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525029"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>在 Lync Server 2013 中管理内部和外部通信的存档

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

在 Lync Server 2013 中，如果不使用 Microsoft Exchange 集成，或者您的用户没有驻留在 Exchange 2013 上的用户的邮箱置于 In-Place 保留状态，则可以使用存档策略来启用和禁用对内部通信和外部通信的存档。 这包括以下存档策略：

  - 部署 Lync Server 2013 时默认创建的全局策略。

  - 您可以创建并用来指定如何针对特定站点或用户实施存档的可选站点级别和用户级别策略。

您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。 在 Lync Server 2013 控制面板中，可以使用 "**存档和监控**" 组的 "**存档策略**" 页来管理全局级别、站点级别和用户级别的策略。 如果将 Lync Server 存储与 Exchange 2013 存储集成，则 Exchange 用户策略将优先于 Lync Server 2013 存档策略。

有关如何实施策略（包括策略的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的 [存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]
> 若要控制存档的实现，您必须在存档配置中指定选项，例如，是否存档 IM 或会议、关键模式的用法和清除选项。 默认情况下，在全局存档配置或任意站点或池存档配置中未启用任何选项。 您应在存档配置中指定所有适当的选项，然后在存档策略中为内部或外部通信启用存档。 有关详细信息，请参阅 Operations 文档中的在 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 中管理存档配置选项（针对组织、网站和池</A> ）。<BR>如果为您的部署启用了 Microsoft Exchange 集成，Exchange 策略将控制是否为驻留在 Exchange 2013 上的用户启用存档，并将其邮箱置于 In-Place 保留状态。 有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A> 。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中创建存档策略，以便为特定站点或用户启用或禁用对内部或外部通信的存档](lync-server-2013-create-archiving-policy-sites-users.md)

  - [在 Lync Server 2013 中更改存档策略，以启用或禁用对组织、网站或用户的内部或外部通信的存档](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [在 Lync Server 2013 中向用户应用存档策略](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [在使用 Exchange Server 集成时，在 Lync Server 2013 中设置存档策略](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [在 Lync Server 2013 中删除存档策略](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

