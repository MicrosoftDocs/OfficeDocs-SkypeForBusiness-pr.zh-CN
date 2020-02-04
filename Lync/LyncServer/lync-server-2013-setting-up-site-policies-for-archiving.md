---
title: Lync Server 2013：设置用于存档的网站策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ebb1efdfff09f51b13ada9d1e2aa571ab88c888
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中设置用于存档的网站策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-09_

你可以通过为每个网站创建和配置存档策略来启用或禁用特定网站的存档。 站点策略将覆盖全局策略，但用户策略将覆盖站点策略。 仅当你不使用 Microsoft Exchange 集成时，或者，如果你使用的是 Microsoft Exchange 集成，但某些用户没有托管在 Exchange 2013 并将其邮箱放在原地保留中，则仅适用于存档策略。

有关存档策略的工作原理的详细信息（包括全局、网站和用户策略的层次结构），请参阅[Lync Server 2013 中的存档如何工作](lync-server-2013-how-archiving-works.md)规划文档、部署文档或操作文档。

<div>


> [!NOTE]  
> 如果为你的部署启用 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管于 Exchange 2013 的用户启用存档，并将其邮箱置于原地保留。 有关详细信息，请参阅在部署文档中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时在 Lync Server 2013 中设置存档策略</A>。<BR>在存档策略中启用内部或外部通信存档之前，应在存档配置中指定所有相应的选项。 有关详细信息，请参阅部署文档中<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中的 "配置存档选项</A>"。



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>为网站创建存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Lync Server 2013 控制面板。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
    有关存档策略的工作原理的详细信息（包括全局、网站和用户策略的层次结构），请参阅[Lync Server 2013 中的存档如何工作](lync-server-2013-how-archiving-works.md)规划文档、部署文档或操作文档。

4.  单击“**新建**”，然后单击“**站点策略**”。

5.  在“**选择站点**”中，单击要应用此策略的站点。

6.  在“**新建存档策略**”中，执行下列操作：
    
      - 在“**名称**”中，指定站点策略的名称。
    
      - 在“**说明**”中，提供有关该站点策略内容的信息（例如，Redmond 的站点策略）。
    
      - 若要控制指定站点的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
      - 若要控制指定站点的外部通信存档，请选中或清除“**存档外部通信**”复选框。

7.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

