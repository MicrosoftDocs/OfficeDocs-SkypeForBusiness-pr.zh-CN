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
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>在 Lync Server 2013 中配置聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

配置持久聊天室通常由用户或其他中心团队通过使用 Windows PowerShell 命令行界面来处理;管理员通常不会管理聊天室。 但是，如果您必须创建和管理聊天室，则可以使用 Windows PowerShell 命令行界面，或将自己添加为聊天室的成员，并使用 Lync 2013 客户端。

有关使用 Windows PowerShell 命令行界面配置聊天室的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。

<div>

## <a name="managing-data-in-chat-rooms"></a>在聊天室中管理数据

持久聊天服务器使用户可以通过将消息发布到持久聊天室来进行协作。 数据保留在服务器上，并且聊天室的成员可以访问数据，包括历史数据。 但是，具有不同角色的用户具有不同的对持久数据的访问权限，如下列表中所述。

  - 管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。 或者，他们可以删除或替换被视为不适合特定聊天室的邮件。

  - 最终用户（包括消息作者）无法删除任何聊天室的内容。

  - 聊天室管理员可以禁用会议室，但不能删除会议室。 只有管理员才能在创建聊天室后将其删除。

删除邮件时，无法撤消该操作。 但是，如果存在备份，则可以还原已删除的邮件。 如果启用了持久聊天合规性服务器，旧消息将保留在合规性数据库中。

<div>


> [!NOTE]  
> 本聊天室数据使用适用于 Lync Server 2013、持久聊天服务器 API 应用程序，但涉及管理员角色的情况除外。 持久聊天服务器 API 无法用于执行任何管理员操作。 必须在 Lync Server 命令行管理程序中执行这些操作。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

