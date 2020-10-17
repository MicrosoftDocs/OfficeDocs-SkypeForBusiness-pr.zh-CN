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
ms.openlocfilehash: db44ca77d217c1b7bc0bc4d05c56cb9b6ff99ea4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525449"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>在 Lync Server 2013 中删除邮件或清除过时邮件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

持久聊天管理员可以从持久聊天室中删除邮件 (并且可以选择将其替换为其他邮件) 。 此外，作为正在进行的维护工作的一部分，管理员可以清除已作废的消息以便最大程度地减小数据库的增长量。 例如，此 Windows PowerShell 命令将删除用户 kenmyer@litwareinc.com 发布的 ITChatRoom 聊天室中的所有邮件：

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

本示例将替换所有已删除的邮件，该邮件将不再可用（请注意）：

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

有关详细信息，请参阅 [CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet 的帮助主题。

</div>

<span> </span>

</div>

</div>

</div>

