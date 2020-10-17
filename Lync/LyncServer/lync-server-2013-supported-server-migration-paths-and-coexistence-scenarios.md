---
title: Lync Server 2013：支持的服务器迁移路径和共存方案
description: Lync Server 2013：支持的服务器迁移路径和共存方案。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d0a40ac6cc6570cf79b56dc896277c83909b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560228"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Lync Server 2013 中支持的服务器迁移路径和共存方案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-16_

Lync Server 2013 支持从以下任一项迁移：

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

不支持从同时运行上述这两个版本的环境中进行迁移。 不支持从早期版本（如 Microsoft Office 通信服务器2007或 Live 通信服务器2005）迁移。 如果以前的部署包含组聊天，则必须单独迁移。

<div>

## <a name="migration-methods"></a>迁移方法

支持迁移所有 Lync Server 拓扑和服务器角色。 可以从一个拓扑迁移到另一拓扑，包括从 Standard Edition Server 迁移到 Enterprise Edition Server。

Lync Server 2013 仅支持以下迁移方法：

  - <span></span>  
    **并行迁移。** 在并行迁移中，Lync Server 2013 与现有 Microsoft Lync Server 2010 或 Office 通信服务器 2007 R2 部署一起部署，然后将操作转移到新服务器并将用户移动到 Lync Server 2013。 采用这种方法时，在迁移过程中需要使用其他服务器平台（包括硬件和软件），并且新配置中的系统名称和池名称与原配置中的不同。 如果需要回滚到先前版本，可以将操作切换回先前的服务器。

不支持跨 Active Directory 域服务林进行迁移。

推荐的迁移路径是一种分阶段方法。有关从先前版本迁移（包括相应的组件分阶段部署）的详细信息，请参阅迁移文档中的以下主题：

  - [从 Lync Server 2010 迁移到 Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [从 Office Communications Server 2007 R2 迁移至 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>共存方案

Lync Server 2013 可与 Lync Server 2010 部署或 Office 通信服务器 2007 R2 部署的组件共存。 同时在 Lync Server 2010 和 Office 通信服务器 2007 (R2 中同时部署 Lync Server 2013，不支持) 的所有三个版本的并发部署。

在第一个分阶段的迁移过程中，以前的 Lync Server 2010 或 Office 通信服务器 2007 R2 部署 coexists 临时部署新的 Lync Server 2013 部署，对混合版本路由的支持将受到限制。 有关详细信息，请参阅迁移文档。

您必须使用运行 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 的单独和不同的计算机来为您的 Lync Server 2013 数据库实例。 您不能对用于 Lync Server 2010 或 Office 通信服务器 2007 R2 前端池的 Lync Server 2013 前端池使用相同的 SQL Server 实例。 如果为已部署 Lync Server 2010 或 Office 通信服务器 2007 R2 的部署在拓扑生成器中定义和配置了 Lync Server 2013，拓扑生成器将不允许您定义已在拓扑中使用的 Lync Server 2013 的实例。

拓扑生成器将显示以下消息，以通知您存在此问题： "服务器的 SQL server \[ FQDN \] 已包含一个 sql 实例托管角色 ' 用户存储 '"。

<div>


> [!NOTE]  
> 如果打算部署 Lync Server 2013 部署中新增的服务器角色，应首先升级您的现有部署，如迁移文档和部署文档中所述，然后部署新的服务器角色，如规划文档和部署文档中所述。 如果要迁移早期版本的组聊天，请在完成从 Lync Server 2010 或 Office 通信服务器 2007 R2 迁移所有其他组件的过程之后，将其迁移到最后一版。



</div>

有关 Lync Server 2010 或 Office 通信服务器 2007 R2 和 Lync Server 2013 组件的共存和迁移的特定共存要求和其他详细信息，请参阅迁移文档中的 [从 Lync server 2010 迁移到 Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) 和 [从 Office 通信服务器 2007 R2 迁移到 lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 。 有关客户端的混合版本支持的详细信息，请参阅 [Lync Server 2013 中的 "从以前的部署支持的客户端](lync-server-2013-supported-clients-from-previous-deployments.md)"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

