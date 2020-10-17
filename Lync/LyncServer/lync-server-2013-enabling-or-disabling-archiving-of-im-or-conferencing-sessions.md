---
title: 启用或禁用 IM 或会议会话的存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f2d9f08ade88a3c19dd861457a46200e7517a34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515509"
---
# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用 IM 或会议会话的存档

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-10_

在 Lync Server 2013 控制面板中，使用存档配置启用和禁用 IM、会议会话的存档。 这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

存档配置最初是在部署存档时设置的，但您可以在部署后更改、添加和删除这些配置。 有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的 [存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]
> 若要使用存档，您必须配置存档策略，以指定是为内部通信启用存档，还是为外部通信启用存档，还是对驻留在 Lync Server 2013 上的用户启用存档。 默认情况下，不会为内部或外部通信启用存档。 在任何策略中启用存档之前，您应为您的部署和（可选）特定站点和池指定相应的存档配置，如本节所述。 有关启用存档的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 中配置和分配存档策略</A> 。<BR>如果您在部署了要使用 Microsoft Exchange 集成来存储 Exchange 2013 服务器上的存档数据和文件的存档后决定，并且您的所有用户都驻留在 Exchange 2013 服务器上，则应从拓扑中删除 SQL Server 数据库配置。 您必须使用拓扑生成器执行此操作。 有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 中更改存档数据库选项</A> 。



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a>启用或禁用 IM 或会议会话的存档

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。

4.  从存档配置列表中选择相应的全局、站点或池策略，单击“编辑”****，再单击“显示详细信息”****，然后执行下列操作：
    
      - 若要只为即时消息 (IM) 会话启用存档，请单击“存档 IM 会话”****。
    
      - 若要同时为 IM 会话和会议启用存档，请单击“存档 IM 和会议会话”****。
    
      - 若要为策略禁用存档，请单击“禁用存档”****。

5.  单击“提交”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中管理组织、网站和池的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[在 Lync Server 2013 中配置和分配存档策略](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

