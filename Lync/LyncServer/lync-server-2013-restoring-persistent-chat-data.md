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
ms.openlocfilehash: 5734296a9b3463740b28e6ead33cc64234640432
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="ccefc-102">在 Lync Server 2013 中还原永久聊天数据</span><span class="sxs-lookup"><span data-stu-id="ccefc-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccefc-103">_**主题上次修改时间：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ccefc-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ccefc-104">持久聊天室内容存储在持久聊天数据库（mgc）中。</span><span class="sxs-lookup"><span data-stu-id="ccefc-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="ccefc-105">这是应定期备份的业务关键型数据。</span><span class="sxs-lookup"><span data-stu-id="ccefc-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="ccefc-106">除了聊天室内容之外，主体（如用户和组）以及他们拥有的用于聊天聊天室和聊天室内容的角色和访问也存储在持久聊天数据库中。</span><span class="sxs-lookup"><span data-stu-id="ccefc-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="ccefc-107">还原持久聊天数据的方式取决于用于备份的方法。</span><span class="sxs-lookup"><span data-stu-id="ccefc-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="ccefc-108">如果您使用 SQL Server 备份过程，则必须使用 SQL Server 还原过程。</span><span class="sxs-lookup"><span data-stu-id="ccefc-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="ccefc-109">如果你使用**Export CsPersistentChatData** Cmdlet 备份持久聊天数据，则必须使用**CsPersistentChatData** cmdlet 来还原数据。</span><span class="sxs-lookup"><span data-stu-id="ccefc-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

