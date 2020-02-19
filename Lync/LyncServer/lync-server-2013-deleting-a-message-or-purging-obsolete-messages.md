---
title: Lync Server 2013：删除邮件或清除过时邮件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c806de25b6936916f99eb262d40acb10aaa8e1f6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="f36de-102">在 Lync Server 2013 中删除邮件或清除过时邮件</span><span class="sxs-lookup"><span data-stu-id="f36de-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f36de-103">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="f36de-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="f36de-104">持久聊天管理员可以从持久聊天室中删除邮件（可选的，也可以将其替换为其他邮件）。</span><span class="sxs-lookup"><span data-stu-id="f36de-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="f36de-105">此外，作为正在进行的维护工作的一部分，管理员可以清除已作废的消息以便最大程度地减小数据库的增长量。</span><span class="sxs-lookup"><span data-stu-id="f36de-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="f36de-106">例如，此 Windows PowerShell 命令将删除用户 kenmyer@litwareinc.com 发布的 ITChatRoom 聊天室中的所有邮件：</span><span class="sxs-lookup"><span data-stu-id="f36de-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="f36de-107">本示例将替换所有已删除的邮件，该邮件将不再可用（请注意）：</span><span class="sxs-lookup"><span data-stu-id="f36de-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="f36de-108">有关详细信息，请参阅[CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="f36de-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

