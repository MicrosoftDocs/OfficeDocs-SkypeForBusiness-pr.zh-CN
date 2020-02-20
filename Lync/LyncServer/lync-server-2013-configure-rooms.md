---
title: Lync Server 2013：配置聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3521e533dee1ff995fae417b8a7f29a75a77ac63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>在 Lync Server 2013 中配置聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

配置持久聊天室通常由用户或其他中心团队通过使用 Windows PowerShell 命令行界面来处理;管理员通常不管理聊天室。 但是，如果您必须创建和管理聊天室，则可以使用 Windows PowerShell 命令行界面，也可以将自己添加为聊天室的成员，然后使用 Lync 2013 客户端。

有关使用 Windows PowerShell 命令行界面配置聊天室的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。

<div>

## <a name="managing-data-in-chat-rooms"></a>管理聊天室中的数据

持久聊天服务器允许用户通过将邮件发布到持久聊天室来进行协作。 数据是保存在服务器上的，聊天室的成员有权访问数据（包括历史记录数据）。 但是，不同角色的用户对所保留的数据具有不同的访问权限，如下面的列表中概述。

  - 管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。他们也可以删除或替换认为对特定聊天室不合适的消息。

  - 最终用户（包括消息作者）无法删除任何聊天室的内容。

  - 聊天室管理员可禁用聊天室，但无法删除聊天室。聊天室创建后，仅管理员可删除它。

消息删除后，便无法撤销该操作。 但是，如果备份了已删除消息，则可还原这些消息。 如果启用了持久聊天合规性服务器，则旧邮件将保留在合规性数据库中。

<div>


> [!NOTE]  
> 此聊天室数据用法适用于 Lync Server 2013、持久聊天服务器 API 应用程序，但涉及管理员角色的情况除外。 持久聊天服务器 API 不能用于执行任何管理员的操作。 必须在 Lync Server 命令行管理程序中执行这些操作。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

