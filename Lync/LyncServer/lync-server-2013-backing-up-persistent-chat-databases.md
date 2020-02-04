---
title: Lync Server 2013：备份持久聊天数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f186552b9e0d5c78d0f40416cd92e41d5705e93a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="97074-102">在 Lync Server 2013 中备份持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="97074-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97074-103">_**主题上次修改时间：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="97074-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="97074-104">持久聊天室内容存储在持久聊天数据库（Mgc）中。</span><span class="sxs-lookup"><span data-stu-id="97074-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="97074-105">这是应定期备份的业务关键型数据。</span><span class="sxs-lookup"><span data-stu-id="97074-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="97074-106">除了聊天室内容，持久聊天数据库还存储有关主体（如用户和用户组）的信息，以及他们拥有的用于聊天室和聊天室的角色和访问权限。</span><span class="sxs-lookup"><span data-stu-id="97074-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="97074-107">备份持久聊天数据有两种方法。</span><span class="sxs-lookup"><span data-stu-id="97074-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="97074-108">SQL Server 备份</span><span class="sxs-lookup"><span data-stu-id="97074-108">SQL Server Backup</span></span>

  - <span data-ttu-id="97074-109">将`Export-CsPersistentChatData`永久聊天数据导出为文件的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="97074-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="97074-110">通过使用 SQL Server 备份创建的数据需要更多的磁盘空间，这可能比创建的过程要多 20 `Export-CsPersistentChatData`倍，但 SQL Server 备份更可能是管理员熟悉的过程。</span><span class="sxs-lookup"><span data-stu-id="97074-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

