---
title: 标准迁移方案-高级别
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92812a791d09c5afc52ebffb4f7989418a5576f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="62554-102">标准迁移方案-高级别</span><span class="sxs-lookup"><span data-stu-id="62554-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62554-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="62554-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="62554-104">将 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器时，请使用以下项目作为起点。</span><span class="sxs-lookup"><span data-stu-id="62554-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="62554-105">标准 Lync Server 2013 迁移路径如下所示：</span><span class="sxs-lookup"><span data-stu-id="62554-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="62554-106">您的组织之前已部署 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天，并且您希望部署 Lync Server 2013、持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="62554-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="62554-107">部署 Lync Server 2013，然后部署持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="62554-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="62554-108">准备并规划持久聊天室的迁移，并确定适当的时间来关闭系统以进行迁移。</span><span class="sxs-lookup"><span data-stu-id="62554-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="62554-109">运行用于迁移的 Windows PowerShell cmdlet （**export-cspersistentchatdata**和**Import-export-cspersistentchatdata**）以将内容移动到持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="62554-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="62554-110">验证该迁移是否成功。</span><span class="sxs-lookup"><span data-stu-id="62554-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="62554-111">停用旧版部署。</span><span class="sxs-lookup"><span data-stu-id="62554-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="62554-112">配置持久聊天服务器，以便旧版客户端可以连接到 Lync Server 2013、持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="62554-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="62554-113">这是必需的，因为部署新的客户端需要一些时间，且您想使用旧版客户端支持现有用户来尽快取得对其聊天室的访问权限。</span><span class="sxs-lookup"><span data-stu-id="62554-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="62554-114">部署新客户端，同时继续帮助确保具有旧式组聊天（客户端）的工作人员可以访问其聊天室。</span><span class="sxs-lookup"><span data-stu-id="62554-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

