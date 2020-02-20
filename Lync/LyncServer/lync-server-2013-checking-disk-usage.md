---
title: Lync Server 2013：检查磁盘使用情况
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d8881bc8b8a55351cc088c230574b958718a63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a>在 Lync Server 2013 中检查磁盘使用率

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-30_

硬盘是 Lync Server 2013 部署的重要组件。 如果没有足够的可用磁盘卷，操作系统和 Lync Server 2013 数据库都不能正常运行。 您必须每天监视 Lync Server 2013 后端数据库统计信息，以帮助确保服务器不会用尽磁盘空间，并准备好根据需要添加存储资源。

除了检查承载操作系统、程序文件、数据库和事务日志的磁盘空间（Lync Server 2013 后端）之外，还应监视文件系统的使用情况，其中包括包含以下重要项的文件共享的磁盘空间数据

  - 会议内容

  - 会议内容元数据

  - 会议合规性日志

  - 应用程序数据文件（由应用程序服务器组件在内部使用）

  - 组聊天服务器 web 服务和合规性文件夹（用于存储上载到组聊天 web 服务的文件）

  - Group Chat 合规性 XML 文件（包含组聊天合规性记录）

  - 更新文件（适用于设备更新服务）

  - 通讯簿文件

Lync Server 2013 需要硬盘空间来存储其数据库和事务日志，以及以前列出的文件共享上的文件。

应定期监视磁盘空间，以帮助确保由于存储资源不足，Lync Server 2013 部署不会产生负面影响。

比较并维护每个 Lync Server 2013 卷上的可用磁盘空间的统计信息，以及数据库和事务日志文件的预期增长。 这有助于在存储资源需要时进行容量规划和添加存储。

为了适应故障排除和灾难恢复情况，我们建议可用的可用卷空间等于或大于数据库大小的110%。

您可以使用以下方法检查可用磁盘空间：

1.  ****   当卷空间受到限制时，可以使用 system center operations manager system center operations manager 向管理员发出警告。

2.  ****   如果可用硬盘空间低于20%，则运行脚本以运行脚本来监视磁盘空间。 你可以在 TechNet 上的 Microsoft 脚本中心找到一个示例脚本，请检查以下内容：[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Windows 资源管理器**   使用 windows 资源管理器检查存储 Lync Server 2013 日志和数据库的卷上的磁盘空间。

</div>

<span> </span>

</div>

</div>

</div>

