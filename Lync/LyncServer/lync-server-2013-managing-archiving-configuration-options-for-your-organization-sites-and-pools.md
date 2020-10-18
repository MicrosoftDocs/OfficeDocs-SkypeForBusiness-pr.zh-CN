---
title: Lync Server 2013：管理组织、网站和池的存档配置选项
description: Lync Server 2013：管理组织、网站和池的存档配置选项。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eca448fcb9863f117bcb7e52e3290270fefa47
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576618"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>在 Lync Server 2013 中管理组织、网站和池的存档配置选项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

在 Lync Server 2013 控制面板中，可以使用存档配置来指定如何实施存档。 这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或池实施存档的可选站点级别和池级别配置。

存档配置最初是在部署存档时设置的，但您可以在部署后更改、添加和删除这些配置。 在 Lync Server 2013 控制面板中，可以使用 "**存档和监控**" 组的 "**存档配置**" 页来管理全局级别、站点级别和池级别的配置。 有关如何实施存档配置的详细信息，包括可以指定哪些选项以及存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的 [存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]  
> 若要使用存档，您必须配置存档策略，以指定是为内部通信启用存档，还是为外部通信启用存档，还是对驻留在 Lync Server 2013 上的所有用户都启用存档。 默认情况下，不对内部或外部通信启用存档。 如果使用 Microsoft Exchange 集成，则必须启用和配置 Exchange 2013，以支持驻留在 Exchange 2013 上的所有用户的邮箱放在 In-Place 保留状态的存档。<BR>如本节中所述，在启用存档之前，应该为您的部署指定相应存档配置，并且还可以选择为特定站点和池指定相应存档配置。 有关启用存档的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 中配置和分配存档策略</A> 。



</div>

**使用 Windows PowerShell cmdlet 查看存档配置信息**

  - 您可以使用 Windows PowerShell 和 **set-csarchivingconfiguration** Cmdlet 查看存档配置信息。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。
    
    在 Lync Server 命令行管理程序中，使用以下命令查看有关所有存档配置设置的信息：
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中创建存档配置，以管理特定网站或池的存档](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [在 Lync Server 2013 中启用或禁用 IM 或会议会话的存档](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [在 Lync Server 2013 中启用或禁用已存档数据的清除](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [启用或禁用 Lync Server 2013 中的关键模式以阻止或允许 IM 和 web 会议会话（如果存档失败）](lync-server-2013-enable-disable-critical-mode.md)

  - [在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [启用或禁用与 Exchange 存储的 Lync Server 2013 集成](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [在 Lync Server 2013 中删除存档配置](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[管理 Lync Server 2013 存档](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

