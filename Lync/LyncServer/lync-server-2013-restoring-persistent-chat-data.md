---
title: Lync Server 2013：还原持久聊天数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c905ee22ed237e908fc72e551f973b6f20fa8f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="7fd96-102">在 Lync Server 2013 中还原持久聊天数据</span><span class="sxs-lookup"><span data-stu-id="7fd96-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fd96-103">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="7fd96-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="7fd96-104">持久聊天聊天室内容存储在持久聊天数据库（mgc）中。</span><span class="sxs-lookup"><span data-stu-id="7fd96-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="7fd96-105">这是应定期备份的关键业务数据。</span><span class="sxs-lookup"><span data-stu-id="7fd96-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="7fd96-106">除了聊天室内容之外，主体（如用户和组）以及必须与聊天室和聊天室内容聊天的角色和访问也存储在持久聊天数据库中。</span><span class="sxs-lookup"><span data-stu-id="7fd96-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="7fd96-107">还原持久聊天数据的方式取决于您用于备份持久聊天数据的方法。</span><span class="sxs-lookup"><span data-stu-id="7fd96-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="7fd96-108">如果您使用的是 SQL Server 备份过程，则必须使用 SQL Server 还原过程。</span><span class="sxs-lookup"><span data-stu-id="7fd96-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="7fd96-109">如果您使用**export-cspersistentchatdata** cmdlet 来备份持久聊天数据，则必须使用**export-cspersistentchatdata** cmdlet 来还原数据。</span><span class="sxs-lookup"><span data-stu-id="7fd96-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

