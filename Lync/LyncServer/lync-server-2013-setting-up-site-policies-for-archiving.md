---
title: Lync Server 2013：设置用于存档的网站策略
description: Lync Server 2013：设置用于存档的网站策略。
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
ms.openlocfilehash: 27e5b80b7f62ddc18d418415307457c7f2c4010d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558388"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中设置用于存档的网站策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

您可以通过为每个网站创建和配置存档策略来启用或禁用对特定网站的存档。 站点策略会覆盖全局策略，但用户策略会覆盖站点策略。 仅当您不使用 Microsoft Exchange 集成时，或者，如果您使用 Microsoft Exchange 集成，但某些用户不驻留在 Exchange 2013 上，并且其邮箱置于 In-Place 保留状态，则存档策略仅适用。

有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅 [在 Lync Server 2013](lync-server-2013-how-archiving-works.md) 规划文档、部署文档或操作文档中存档的工作原理。

<div>


> [!NOTE]  
> 如果为部署启用了 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否为驻留在 Exchange 2013 上的用户启用存档，并将其邮箱置于 In-Place 保留状态。 有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A> 。<BR>在存档策略中启用内部或外部通信的存档之前，应在存档配置中指定所有适当选项。 有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A> 。



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>为网站创建存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 Lync Server 2013 控制面板。

3.  在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。
    
    有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅 [在 Lync Server 2013](lync-server-2013-how-archiving-works.md) 规划文档、部署文档或操作文档中存档的工作原理。

4.  单击“新建”****，然后单击“站点策略”****。

5.  在 " **选择站点**" 中，单击要应用该策略的站点。

6.  在 **“新建存档策略”** 中，执行下列操作：
    
      - 在 " **名称**" 中，指定网站策略的名称。
    
      - 在 " **说明**" 中，提供有关网站策略 (的信息，例如，Redmond) 的网站策略。
    
      - 若要控制指定站点的内部通信的存档，请选中或清除 " **存档内部通信** " 复选框。
    
      - 若要控制指定站点的外部通信存档，请选中或清除 " **存档外部通信** " 复选框。

7.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

