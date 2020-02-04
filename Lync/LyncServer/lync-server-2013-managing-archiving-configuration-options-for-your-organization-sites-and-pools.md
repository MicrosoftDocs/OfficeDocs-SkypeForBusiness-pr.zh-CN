---
title: Lync Server 2013：管理你的组织、网站和池的存档配置选项
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
ms.openlocfilehash: 59db9765b9e9ee0b453268ea9c22d897f10ba662
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>管理您的组织、网站和池的 Lync Server 2013 中的存档配置选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

在 Lync Server 2013 "控制面板" 中，使用存档配置来指定如何实施存档。 这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 可创建和使用的可选网站级和池级配置，用于指定如何为特定网站或池实现存档。

你在部署存档时开始设置存档配置，但你可以在部署后更改、添加和删除配置。 在 Lync Server 2013 "控制面板" 中，可以使用 "**存档和监视**" 组的 "**存档配置**" 页来管理全局级别、网站级别和池级别的配置。 有关如何实现存档配置的详细信息（包括你可以指定哪些选项以及存档配置的层次结构），请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 若要使用存档，必须配置存档策略，以指定是为内部通信启用存档、对于外部通信还是对驻留在 Lync Server 2013 上的所有用户启用存档。 默认情况下，不会为内部或外部通信启用存档。 如果使用 Microsoft Exchange 集成，则必须启用和配置 Exchange 2013 以支持驻留在 Exchange 2013 上的所有用户的邮箱放置在原地保留中的所有用户的存档。<BR>在启用存档之前，你应该为你的部署指定适当的存档配置，并根据需要为特定的网站和池指定相应的存档配置，如本节所述。 有关启用存档的详细信息，请参阅部署文档中的<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">在 Lync Server 2013 中配置和分配存档策略</A>。



</div>

**使用 Windows PowerShell cmdlet 查看存档配置信息**

  - 你可以使用 Windows PowerShell 和**CsArchivingConfiguration** Cmdlet 查看存档配置信息。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    在 Lync Server Management Shell 中，使用以下命令查看有关所有存档配置设置的信息：
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中创建存档配置以管理特定网站或池的存档](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [在 Lync Server 2013 中启用或禁用 IM 或会议会话的存档](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [在 Lync Server 2013 中启用或禁用已存档数据的清除](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [启用或禁用 Lync Server 2013 中的关键模式，以阻止或允许 IM 和网络会议会话（如果存档失败）](lync-server-2013-enable-disable-critical-mode.md)

  - [在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [启用或禁用 Lync Server 2013 与 Exchange 存储的集成](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

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

