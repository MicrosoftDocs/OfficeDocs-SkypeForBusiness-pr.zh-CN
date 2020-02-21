---
title: Lync Server 2013：将聊天室从一个类别移动到另一个类别
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27ca186fa31b1207238c3a7d254bbd6066cc1d89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="779ff-102">在 Lync Server 2013 中将聊天室从一个类别移动到另一个类别</span><span class="sxs-lookup"><span data-stu-id="779ff-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="779ff-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="779ff-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="779ff-104">我们建议您在创建聊天室后，不要更改持久聊天室的类别。</span><span class="sxs-lookup"><span data-stu-id="779ff-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="779ff-105">但是，如果聊天室管理员在其他类别中具有 **Creator** 特权，则他/她可以将聊天室从一个类别移动到另一个类别。</span><span class="sxs-lookup"><span data-stu-id="779ff-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="779ff-106">将不会删除和重新创建该聊天室。</span><span class="sxs-lookup"><span data-stu-id="779ff-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="779ff-107">这是数据库中的关联的更改。</span><span class="sxs-lookup"><span data-stu-id="779ff-107">It is a change of association within the database.</span></span>

<span data-ttu-id="779ff-p102">应该尽量不要更改聊天室类别。类别用于确定聊天室允许的成员身份，因此当聊天室移动到另一个类别时，新类别不再支持的所有系统访问控制列表 (SACL) 都将清除。例如，如果用户是聊天室的成员，且不再是新类别中的 **AllowedMember**，则系统会修改聊天室成员身份，并将用户从聊天室中删除。</span><span class="sxs-lookup"><span data-stu-id="779ff-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="779ff-111">有关使用 Windows PowerShell 命令行界面移动聊天室的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。</span><span class="sxs-lookup"><span data-stu-id="779ff-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="779ff-112">有关配置聊天室的详细信息，请参阅部署文档中的在[Lync Server 2013 中配置会议室](lync-server-2013-configure-rooms.md)。</span><span class="sxs-lookup"><span data-stu-id="779ff-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

