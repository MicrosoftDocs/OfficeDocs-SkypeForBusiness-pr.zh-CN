---
title: 'Lync Server 2013: 配置全局策略以进行存档'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccb5ba267c3dc94e14f00cf96f240fa2f0e91b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中配置用于存档的全局策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-09_

当您部署前端服务器时, Lync 服务器将为存档创建全局策略。 默认情况下, 存档在全局策略中处于禁用状态。 全局策略控制是否为整个部署启用存档以进行内部和外部通信, 除非你设置网站或用户策略 (这将覆盖全局策略), 或者你对部分或全部使用 Microsoft Exchange 集成您的用户。 如果你使用 Microsoft Exchange 集成, 则全局策略不会应用于托管在 Exchange 2013 上的任何用户, 并将邮箱置于原地保留。

有关存档策略的工作原理的详细信息 (包括全局、网站和用户策略的层次结构), 请参阅[Lync Server 2013 中的存档如何工作](lync-server-2013-how-archiving-works.md)规划文档、部署文档或操作文档。

<div>


> [!NOTE]  
> 如果为你的部署启用 Microsoft Exchange 集成, 则 Exchange 就地保留策略控制是否为托管于 Exchange 2013 的用户启用存档, 并将其邮箱置于原地保留。 有关详细信息, 请参阅在部署文档中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时在 Lync Server 2013 中设置存档策略</A>。<BR>在启用存档之前, 应在存档配置中指定所有适当的选项。 有关详细信息, 请参阅部署文档中<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中的 "配置存档选项</A>"。



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>在使用 Lync Server 存档数据库时配置存档的全局策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Lync Server 2013 控制面板。 有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。

4.  在“**存档策略**”页上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在“**编辑存档策略 - 全局**”中，执行下列操作：
    
      - 在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
      - 在“**说明**”中，提供有关该策略内容的信息（例如，*divisionName* 的全局策略）
    
      - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“**存档内部通信**”复选框。
    
      - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“**存档外部通信**”复选框。

6.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

