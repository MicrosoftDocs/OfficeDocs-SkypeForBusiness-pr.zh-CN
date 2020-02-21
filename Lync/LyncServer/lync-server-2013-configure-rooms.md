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
ms.openlocfilehash: 7e78401d0f72f3b29f50453f49f7d7eb66811715
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="fb9f0-102">在 Lync Server 2013 中配置聊天室</span><span class="sxs-lookup"><span data-stu-id="fb9f0-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb9f0-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fb9f0-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fb9f0-104">配置持久聊天室通常由用户或其他中心团队通过使用 Windows PowerShell 命令行界面来处理;管理员通常不管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="fb9f0-105">但是，如果您必须创建和管理聊天室，则可以使用 Windows PowerShell 命令行界面，也可以将自己添加为聊天室的成员，然后使用 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="fb9f0-106">有关使用 Windows PowerShell 命令行界面配置聊天室的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="fb9f0-107">管理聊天室中的数据</span><span class="sxs-lookup"><span data-stu-id="fb9f0-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="fb9f0-108">持久聊天服务器允许用户通过将邮件发布到持久聊天室来进行协作。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="fb9f0-109">数据是保存在服务器上的，聊天室的成员有权访问数据（包括历史记录数据）。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="fb9f0-110">但是，不同角色的用户对所保留的数据具有不同的访问权限，如下面的列表中概述。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="fb9f0-p103">管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。他们也可以删除或替换认为对特定聊天室不合适的消息。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-p103">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large. Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="fb9f0-113">最终用户（包括消息作者）无法删除任何聊天室的内容。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="fb9f0-p104">聊天室管理员可禁用聊天室，但无法删除聊天室。聊天室创建后，仅管理员可删除它。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-p104">Chat room managers can disable rooms, but cannot delete rooms. Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="fb9f0-116">消息删除后，便无法撤销该操作。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="fb9f0-117">但是，如果备份了已删除消息，则可还原这些消息。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="fb9f0-118">如果启用了持久聊天合规性服务器，则旧邮件将保留在合规性数据库中。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb9f0-119">此聊天室数据用法适用于 Lync Server 2013、持久聊天服务器 API 应用程序，但涉及管理员角色的情况除外。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="fb9f0-120">持久聊天服务器 API 不能用于执行任何管理员的操作。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="fb9f0-121">必须在 Lync Server 命令行管理程序中执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="fb9f0-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

