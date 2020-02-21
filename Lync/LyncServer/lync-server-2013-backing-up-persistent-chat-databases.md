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
ms.openlocfilehash: 218c011d2acc970028bfd0be529d89542d684758
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="61415-102">在 Lync Server 2013 中备份持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="61415-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61415-103">_**上次修改的主题：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="61415-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="61415-104">持久聊天聊天室内容存储在持久聊天数据库（Mgc）中。</span><span class="sxs-lookup"><span data-stu-id="61415-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="61415-105">这是应定期备份的关键业务数据。</span><span class="sxs-lookup"><span data-stu-id="61415-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="61415-106">除了聊天室内容之外，持久聊天数据库还存储有关主体（如用户和用户组）的信息，以及他们必须与聊天室和聊天室聊天的角色和访问权限。</span><span class="sxs-lookup"><span data-stu-id="61415-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="61415-107">有两种备份持久聊天数据的方法。</span><span class="sxs-lookup"><span data-stu-id="61415-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="61415-108">SQL Server 备份</span><span class="sxs-lookup"><span data-stu-id="61415-108">SQL Server Backup</span></span>

  - <span data-ttu-id="61415-109">将`Export-CsPersistentChatData`持久聊天数据导出为文件的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="61415-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="61415-110">使用 SQL Server 备份创建的数据需要显著更多的磁盘空间-可能比创建的数据更多20倍`Export-CsPersistentChatData`，但 SQL Server 备份更可能是管理员熟悉的过程。</span><span class="sxs-lookup"><span data-stu-id="61415-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

