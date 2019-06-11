---
title: Lync Server 2013：删除消息或清除作废的消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e6d383b1c64441f8ff052e390dc141102e8901
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="93656-102">在 Lync Server 2013 中删除消息或清除作废的消息</span><span class="sxs-lookup"><span data-stu-id="93656-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93656-103">_**主题上次修改时间:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="93656-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="93656-104">持续聊天管理员可以从持久聊天室删除消息 (也可以选择将其替换为其他消息)。</span><span class="sxs-lookup"><span data-stu-id="93656-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="93656-105">管理员还可以清除过时的消息作为持续维护的一部分, 以最大程度地减少数据库增长。</span><span class="sxs-lookup"><span data-stu-id="93656-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="93656-106">例如, 此 Windows PowerShell 命令将删除由用户 kenmyer@litwareinc.com 发布的 ITChatRoom 聊天室中的所有消息:</span><span class="sxs-lookup"><span data-stu-id="93656-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="93656-107">此示例将替换所有已删除的邮件, 注意该邮件不再可用:</span><span class="sxs-lookup"><span data-stu-id="93656-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="93656-108">有关详细信息, 请参阅[CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="93656-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

