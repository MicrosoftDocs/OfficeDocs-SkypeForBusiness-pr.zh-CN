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
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="1dfe4-102">在 Lync Server 2013 中配置聊天室</span><span class="sxs-lookup"><span data-stu-id="1dfe4-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dfe4-103">_**主题上次修改时间：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="1dfe4-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="1dfe4-104">配置持久聊天室通常由用户或其他中心团队通过使用 Windows PowerShell 命令行界面来处理;管理员通常不会管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="1dfe4-105">但是，如果您必须创建和管理聊天室，则可以使用 Windows PowerShell 命令行界面，或将自己添加为聊天室的成员，并使用 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="1dfe4-106">有关使用 Windows PowerShell 命令行界面配置聊天室的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="1dfe4-107">在聊天室中管理数据</span><span class="sxs-lookup"><span data-stu-id="1dfe4-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="1dfe4-108">持久聊天服务器使用户可以通过将消息发布到持久聊天室来进行协作。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="1dfe4-109">数据保留在服务器上，并且聊天室的成员可以访问数据，包括历史数据。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="1dfe4-110">但是，具有不同角色的用户具有不同的对持久数据的访问权限，如下列表中所述。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="1dfe4-111">管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="1dfe4-112">或者，他们可以删除或替换被视为不适合特定聊天室的邮件。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="1dfe4-113">最终用户（包括消息作者）无法删除任何聊天室的内容。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="1dfe4-114">聊天室管理员可以禁用会议室，但不能删除会议室。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="1dfe4-115">只有管理员才能在创建聊天室后将其删除。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="1dfe4-116">删除邮件时，无法撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="1dfe4-117">但是，如果存在备份，则可以还原已删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="1dfe4-118">如果启用了持久聊天合规性服务器，旧消息将保留在合规性数据库中。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1dfe4-119">本聊天室数据使用适用于 Lync Server 2013、持久聊天服务器 API 应用程序，但涉及管理员角色的情况除外。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="1dfe4-120">持久聊天服务器 API 无法用于执行任何管理员操作。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="1dfe4-121">必须在 Lync Server 命令行管理程序中执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="1dfe4-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

