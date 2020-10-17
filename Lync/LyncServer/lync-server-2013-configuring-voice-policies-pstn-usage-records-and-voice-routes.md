---
title: 配置语音策略、PSTN 用法记录和语音路由
description: 配置语音策略、PSTN 用法记录和语音路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94306e5c4d773a83fa6bfe3eec2857279e235642
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542228"
---
# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="44e0c-103">在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由</span><span class="sxs-lookup"><span data-stu-id="44e0c-103">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e0c-104">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="44e0c-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="44e0c-p101">语音策略、PSTN 用法记录和语音路由是一个有机整体。可以通过选择一组呼叫功能，然后为策略分配一组 PSTN 用法记录来配置语音策略，这些记录指定为分配了语音策略的用户或组授予哪些权限。系统还向语音路由分配 PSTN 用法记录，这些记录用于将路由与有权使用它们的用户进行匹配。也就是说，用户只能发出使用用户对于其有匹配的 PSTN 用法记录的路由的呼叫。</span><span class="sxs-lookup"><span data-stu-id="44e0c-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="44e0c-109">通过配置包含相应的 PSTN 用法记录的语音策略来启动新企业语音部署的建议工作流，然后将相应的路由关联到每个 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="44e0c-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="44e0c-110">您还可以创建具有用户<EM></EM>作用域的语音策略，并将其分配到各个用户或组。</span><span class="sxs-lookup"><span data-stu-id="44e0c-110">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="44e0c-111">有关执行上述各项任务的详细步骤，请参阅本节中的过程。</span><span class="sxs-lookup"><span data-stu-id="44e0c-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44e0c-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="44e0c-112">In This Section</span></span>

  - [<span data-ttu-id="44e0c-113">在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限</span><span class="sxs-lookup"><span data-stu-id="44e0c-113">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="44e0c-114">在 Lync Server 2013 中查看 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="44e0c-114">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="44e0c-115">在 Lync Server 2013 中配置出站呼叫的语音路由</span><span class="sxs-lookup"><span data-stu-id="44e0c-115">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="44e0c-116">在 Lync Server 2013 中导出和导入语音路由配置</span><span class="sxs-lookup"><span data-stu-id="44e0c-116">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="44e0c-117">在 Lync Server 2013 中发布对语音路由配置所做的挂起更改</span><span class="sxs-lookup"><span data-stu-id="44e0c-117">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="44e0c-118">在 Lync Server 2013 中测试语音路由</span><span class="sxs-lookup"><span data-stu-id="44e0c-118">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

