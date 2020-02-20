---
title: Lync Server 2013：创建或编辑新聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 564db7b9d1bfaab00e51628377f330da05af17e8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="19af1-102">在 Lync Server 2013 中创建或编辑新聊天室</span><span class="sxs-lookup"><span data-stu-id="19af1-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19af1-103">_**上次修改的主题：** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="19af1-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="19af1-104">配置持久聊天室通常由用户处理;持久聊天管理员通常不配置或管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="19af1-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="19af1-105">用于管理聊天室的 Windows PowerShell cmdlet 仅适用于**CsPersistentChatAdministrator**管理员。</span><span class="sxs-lookup"><span data-stu-id="19af1-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="19af1-106">任何给定类别中的**创建者**的用户都可以使用 Lync 客户端来创建和管理会议室。</span><span class="sxs-lookup"><span data-stu-id="19af1-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="19af1-107">已被指定为特定聊天室的管理员的用户也可以对聊天室执行持续的管理，如编辑聊天室属性或成员身份。</span><span class="sxs-lookup"><span data-stu-id="19af1-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="19af1-108">持久聊天管理员也可以是创建者，它们不受限于创建者的限制。</span><span class="sxs-lookup"><span data-stu-id="19af1-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="19af1-109">（可选）如果您是持久聊天管理员，则可以使用用户界面来创建和管理聊天室，而不是使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19af1-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="19af1-110">为此，SIP 启用持久聊天服务器的管理员，然后使用 Lync 客户端来创建和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="19af1-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="19af1-111">如果要为用户创建自定义会议室管理工作流，可以在持久聊天服务器配置上设置**RoomManagementUrl**属性，以将用户重定向到 Lync 客户端的自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="19af1-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="19af1-112">有关使用 Windows PowerShell 命令行界面配置聊天室的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。</span><span class="sxs-lookup"><span data-stu-id="19af1-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="19af1-113">有关配置聊天室的详细信息，请参阅部署文档中的在[Lync Server 2013 中配置会议室](lync-server-2013-configure-rooms.md)。</span><span class="sxs-lookup"><span data-stu-id="19af1-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19af1-114">持久聊天服务器允许用户为特定网站创建和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="19af1-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="19af1-115">但是，用户无法在同一拓扑中的其他网站上创建或管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="19af1-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="19af1-116">请务必为你组织中的所有网站指定聊天室创建者和经理。</span><span class="sxs-lookup"><span data-stu-id="19af1-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="19af1-117">驻留在 Lync Server Survivable 分支设备上的用户无法创建新的聊天室或查看现有聊天室的会议室卡片。</span><span class="sxs-lookup"><span data-stu-id="19af1-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

