---
title: 为持久聊天服务器运行向后兼容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d7054e9dfb3eba8e6365710accfd3a9693bc39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a><span data-ttu-id="acb3e-102">为持久聊天服务器运行向后兼容</span><span class="sxs-lookup"><span data-stu-id="acb3e-102">Run backward compatibility for Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acb3e-103">_**主题上次修改时间：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="acb3e-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="acb3e-104">Lync Server 2013、持久聊天服务器终结点提供一种方法来创建指向持久聊天服务器池的简单 URL。</span><span class="sxs-lookup"><span data-stu-id="acb3e-104">The Lync Server 2013, Persistent Chat Server endpoint provides a way to create a simple URL that points to a Persistent Chat Server pool.</span></span> <span data-ttu-id="acb3e-105">这对于旧版客户端（Microsoft Office 通信服务器 2007 R2 群组聊天服务器或 Lync Server 2010，群组聊天）很有用，因为当尝试将旧客户端指向运行 Lync 2013 的计算机时，用户可以在手动配置中输入简单的 URL。持久聊天。</span><span class="sxs-lookup"><span data-stu-id="acb3e-105">This is useful for legacy clients (Microsoft Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat) because users can enter a simple URL in the manual configuration when trying to point the legacy client to a computer running Lync 2013, Persistent Chat.</span></span> <span data-ttu-id="acb3e-106">此终结点不会由永久聊天使用，并且仅对旧客户端是必需的。</span><span class="sxs-lookup"><span data-stu-id="acb3e-106">This endpoint isn’t used by Persistent Chat, and is required for legacy clients only.</span></span> <span data-ttu-id="acb3e-107">这对于可以迁移会议室的中间时期非常有用，但 Lync 2013 客户端尚未在整个组织中部署。</span><span class="sxs-lookup"><span data-stu-id="acb3e-107">This is useful for the interim period where rooms may be migrated, but the Lync 2013 clients have not been deployed throughout the organization.</span></span> <span data-ttu-id="acb3e-108">运行 Lync 2010 组聊天（客户端）的用户仍然可以连接到持久聊天服务器后端服务器。</span><span class="sxs-lookup"><span data-stu-id="acb3e-108">Users running Lync 2010 Group Chat (client) can then still connect to the Persistent Chat Server Back End Server.</span></span>

<span data-ttu-id="acb3e-109">无需创建多个持久聊天服务器终结点;您只需要每个持久聊天服务器池的一个。</span><span class="sxs-lookup"><span data-stu-id="acb3e-109">You don’t need to create multiple Persistent Chat Server endpoints; you just need one for each Persistent Chat Server pool.</span></span> <span data-ttu-id="acb3e-110">管理员可以创建多个终结点（每个池一个终结点），但旧客户端可以配置为一次仅连接到一个池。</span><span class="sxs-lookup"><span data-stu-id="acb3e-110">Administrators can create multiple endpoints (one per pool), but legacy clients can be configured to connect to only one pool at a time.</span></span> <span data-ttu-id="acb3e-111">在常规或主流方案中，旧式部署仅为一个池。</span><span class="sxs-lookup"><span data-stu-id="acb3e-111">In the usual or mainstream scenario, the legacy deployment is one pool only.</span></span> <span data-ttu-id="acb3e-112">新部署通常会将该池迁移到新的 Lync Server 2013，并且可能会添加一些新的附加持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="acb3e-112">A new deployment generally migrates that pool to a new Lync Server 2013 and might add some new additional Persistent Chat Server pools.</span></span>

<span data-ttu-id="acb3e-113">此主流方案通常遵循以下模式：</span><span class="sxs-lookup"><span data-stu-id="acb3e-113">This mainstream scenario generally follows this pattern:</span></span>

  - <span data-ttu-id="acb3e-114">使用一个 Lync Server 2010、群组聊天池和 Lync 2010 组聊天客户端管理用户通过使用某些已知用户（默认 sip： ocschat@\<domainName\>或类似的用户）连接到该池。</span><span class="sxs-lookup"><span data-stu-id="acb3e-114">You administer users with one Lync Server 2010, Group Chat pool, and your Lync 2010 Group Chat clients connect to that pool by using some well-known user (either default sip:ocschat@\<domainName\>.com, or a similar one).</span></span> <span data-ttu-id="acb3e-115">用户是启用 SIP 的 Active Directory 域服务，并且查找服务会向他们注册以接收传入的请求。</span><span class="sxs-lookup"><span data-stu-id="acb3e-115">The users are SIP-enabled Active Directory Domain Services, and the Lookup service registers with them to receive incoming requests.</span></span>

  - <span data-ttu-id="acb3e-116">然后，安装 Lync Server 2013 持久聊天服务器和持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="acb3e-116">Subsequently, you install a Lync Server 2013 Persistent Chat Server and Persistent Chat Server pool.</span></span>

  - <span data-ttu-id="acb3e-117">在用户通常处于离线状态（例如周末）的时间内：</span><span class="sxs-lookup"><span data-stu-id="acb3e-117">During a time when users are generally offline (for example, a weekend):</span></span>
    
      - <span data-ttu-id="acb3e-118">关闭 Lync Server 2010，群组聊天。</span><span class="sxs-lookup"><span data-stu-id="acb3e-118">Turn off Lync Server 2010, Group Chat.</span></span>
    
      - <span data-ttu-id="acb3e-119">将数据从 Lync Server 2010、群组聊天池迁移到 Lync Server 2013 持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="acb3e-119">Migrate data from the Lync Server 2010, Group Chat pool to the Lync Server 2013 Persistent Chat Server pool.</span></span>
    
      - <span data-ttu-id="acb3e-120">从 Active Directory 域服务中删除众所周知的用户。</span><span class="sxs-lookup"><span data-stu-id="acb3e-120">Delete the well-known user from the Active Directory Domain Services.</span></span>
    
      - <span data-ttu-id="acb3e-121">使用与以前删除的已知用户相同的 SIP URI 创建新的*旧式终结点*。</span><span class="sxs-lookup"><span data-stu-id="acb3e-121">Create a new *legacy endpoint* with the same SIP URI as the previously deleted well-known user.</span></span>
    
      - <span data-ttu-id="acb3e-122">启动 Lync Server 2013 和持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="acb3e-122">Start the Lync Server 2013, Persistent Chat Servers.</span></span>

  - <span data-ttu-id="acb3e-123">用户通过其 Lync 2010 群组聊天（客户端）重新登录，并连接到其数据，而无需更改任何配置。</span><span class="sxs-lookup"><span data-stu-id="acb3e-123">Users log back on by using their Lync 2010 Group Chat (client) and connect to their data without needing to change any configuration.</span></span>

  - <span data-ttu-id="acb3e-124">以后，您可以解除 Lync Server 2010、群组聊天。</span><span class="sxs-lookup"><span data-stu-id="acb3e-124">At a later time, you can decommission the Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="acb3e-125">然后，你可以部署 Lync Server 2013、持久聊天服务器以及安装新的 Lync Server 2013 持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="acb3e-125">Subsequently, you can deploy Lync Server 2013, Persistent Chat Server, and install new Lync Server 2013 Persistent Chat Server pools.</span></span>

<span data-ttu-id="acb3e-126">有关从 Lync Server 2010 进行迁移的详细信息，群组聊天到 Lync Server 2013，持久聊天服务器，请参阅[从 Lync server 2010 迁移、群组聊天或 Office 通信服务器 2007 R2 群组聊天到 Lync Server 2013、持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="acb3e-126">For details about migrating from Lync Server 2010, Group Chat to Lync Server 2013, Persistent Chat Server, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="acb3e-127">若要运行向后兼容性（若要创建指向持久聊天服务器池的持久聊天服务器终结点，可由旧式组聊天池客户端使用）：</span><span class="sxs-lookup"><span data-stu-id="acb3e-127">To run backward compatibility (to create a Persistent Chat Server endpoint that points to a Persistent Chat Server pool, which can be used by legacy Group Chat pool clients):</span></span>

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

<span data-ttu-id="acb3e-128">接下来，配置持久聊天客户端以将该 SIP 地址用作其 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="acb3e-128">Next, configure Persistent Chat clients to use that SIP address as their contact object.</span></span> <span data-ttu-id="acb3e-129">SIP 地址是使用特定持久聊天服务器池的**CsPersistentChatEndpoint** cmdlet 创建的。</span><span class="sxs-lookup"><span data-stu-id="acb3e-129">The SIP address is created with the **New-CsPersistentChatEndpoint** cmdlet for a specific Persistent Chat Server pool.</span></span>

<span data-ttu-id="acb3e-130">若要使用 Windows PowerShell 命令行界面添加持久聊天服务器终结点，请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="acb3e-130">To add the Persistent Chat Server endpoint by using Windows PowerShell command-line interface, consider the following example.</span></span> <span data-ttu-id="acb3e-131">在这种情况下，你正在将 contact 对象配置为 "contoso.com" 拓扑中的 "persistentchat"，其中池完全限定的域名（FQDN）为 "pcpool.contoso.com"：</span><span class="sxs-lookup"><span data-stu-id="acb3e-131">In this case, you are configuring the contact object to be named "persistentchat" on the "contoso.com" topology, where the pool fully qualified domain name (FQDN) is "pcpool.contoso.com":</span></span>

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a><span data-ttu-id="acb3e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acb3e-132">See Also</span></span>


[<span data-ttu-id="acb3e-133">从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="acb3e-133">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

