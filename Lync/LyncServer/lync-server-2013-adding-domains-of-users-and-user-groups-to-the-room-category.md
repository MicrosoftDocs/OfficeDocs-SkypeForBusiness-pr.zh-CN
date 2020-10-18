---
title: Lync Server 2013：将用户和用户组的域添加到聊天室类别
description: Lync Server 2013：将用户和用户组的域添加到聊天室类别中。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196a795547d5caa6dfd1732c3d6b4630ef79438a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573518"
---
# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a><span data-ttu-id="6dc85-103">在 Lync Server 2013 中将用户和用户组的域添加到聊天室类别</span><span class="sxs-lookup"><span data-stu-id="6dc85-103">Adding domains of users and user groups to the room category in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dc85-104">_**上次修改的主题：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="6dc85-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="6dc85-105">若要向聊天室添加更多用户组，请参阅在 [Lync Server 2013 中配置类别](lync-server-2013-configure-categories.md) 和在部署文档中 [管理类别](manage-categories.md) 。</span><span class="sxs-lookup"><span data-stu-id="6dc85-105">To add larger groups of users to a chat room, see [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) and [Manage categories](manage-categories.md) in the Deployment documentation.</span></span> <span data-ttu-id="6dc85-106">例如，此命令将 active Directory 中的 NorthAmericaUsers OU 中的所有用户添加到 "北美" 聊天室：</span><span class="sxs-lookup"><span data-stu-id="6dc85-106">For example, this command adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

<span data-ttu-id="6dc85-107">他的命令将财务通讯组中的所有成员添加到同一个聊天室：</span><span class="sxs-lookup"><span data-stu-id="6dc85-107">His command adds all the members from the Finance distribution group to the same chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

