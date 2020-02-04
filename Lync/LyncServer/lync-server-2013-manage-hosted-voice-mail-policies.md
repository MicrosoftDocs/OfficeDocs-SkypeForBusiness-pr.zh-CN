---
title: Lync Server 2013：管理托管的语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 434cc1eb721635f4a56be33f48802da3bc6db0e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="f55a3-102">在 Lync Server 2013 中管理托管的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="f55a3-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f55a3-103">_**主题上次修改时间：** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="f55a3-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="f55a3-104">*托管语音邮件策略*向 Lync Server 2013 ExUM 路由应用程序提供有关邮箱位于托管 Exchange 服务上的用户的路由位置的信息。</span><span class="sxs-lookup"><span data-stu-id="f55a3-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f55a3-105">通常，只需要一个托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f55a3-105">Typically, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="f55a3-106">在许多情况下，你可以修改全局策略以满足你的所有需求。</span><span class="sxs-lookup"><span data-stu-id="f55a3-106">In many cases, you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="f55a3-107">如果你创建具有网站范围的策略，则该策略将自动分配给驻留在指定网站的所有用户。</span><span class="sxs-lookup"><span data-stu-id="f55a3-107">If you create a policy with site scope, it is assigned automatically to all users homed at the specified site.</span></span> <span data-ttu-id="f55a3-108">如果你创建具有每用户作用域的策略，则必须将其显式分配给用户、组和联系人对象。</span><span class="sxs-lookup"><span data-stu-id="f55a3-108">If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects.</span></span> <span data-ttu-id="f55a3-109">可以部署多个托管语音邮件策略，但在这种情况下，必须在每个用户的基础上分配策略。</span><span class="sxs-lookup"><span data-stu-id="f55a3-109">It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="f55a3-110">有关规划托管语音邮件策略的详细信息，请参阅规划文档中[Lync Server 2013 中的托管语音邮件策略](lync-server-2013-hosted-voice-mail-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="f55a3-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f55a3-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="f55a3-111">In This Section</span></span>

  - [<span data-ttu-id="f55a3-112">在 Lync Server 2013 中修改全局托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="f55a3-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="f55a3-113">在 Lync Server 2013 中创建网站级托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="f55a3-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="f55a3-114">在 Lync Server 2013 中创建每用户托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="f55a3-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="f55a3-115">在 Lync Server 2013 中分配每用户托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="f55a3-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

