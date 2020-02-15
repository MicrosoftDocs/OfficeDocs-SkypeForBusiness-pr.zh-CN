---
title: Lync Server 2013 电话拨入式会议要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80ab9db6b565530db211db8aa47e2e00cbd9cf2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="b9b6d-102">Lync Server 2013 中的电话拨入式会议要求</span><span class="sxs-lookup"><span data-stu-id="b9b6d-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9b6d-103">_**上次修改的主题：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="b9b6d-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="b9b6d-104">在启动 Lync Server 2013 部署过程之前，您需要规划以下各项：</span><span class="sxs-lookup"><span data-stu-id="b9b6d-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="b9b6d-105">连接到公用电话交换网 (PSTN) 时使用的配置</span><span class="sxs-lookup"><span data-stu-id="b9b6d-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="b9b6d-106">为拨入访问号码分配电话拨入式会议区域的策略</span><span class="sxs-lookup"><span data-stu-id="b9b6d-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="b9b6d-107">创建会议目录的策略</span><span class="sxs-lookup"><span data-stu-id="b9b6d-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="b9b6d-108">规划拨入 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="b9b6d-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="b9b6d-109">电话拨入式会议要求至少一个中介服务器和至少一个 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="b9b6d-110">您可以在中央站点或分支站点中部署中介服务器。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="b9b6d-111">在中央站点中，您可以在前端池或 Standard Edition 服务器上并置中介服务器，也可以将其部署在独立服务器或池上。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="b9b6d-112">在分支站点中，可以在独立服务器上部署中介服务器，也可以将其部署为 Survivable 分支设备的组件。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="b9b6d-113">您可以在中央站点或分支站点部署 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="b9b6d-114">在分支站点中，PSTN 网关可以是独立的，也可以是 Survivable 分支设备的组件。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9b6d-115">由于 A/V 会议服务器不支持媒体旁路，电话拨入式会议不会使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="b9b6d-116">有关规划用于电话拨入式会议的中介服务器和 PSTN 网关的配置的详细信息，请参阅规划文档中的 "[在 Lync server 2013 中的中介服务器的组件和拓扑](lync-server-2013-components-and-topologies-for-mediation-server.md)"。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="b9b6d-117">规划电话拨入式会议区域</span><span class="sxs-lookup"><span data-stu-id="b9b6d-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="b9b6d-p103">在拨入配置过程中，创建拨号计划和电话拨入式会议访问号码。拨号计划是几组规范化规则，用来指定电话号码的数字和数字模式，并将电话号码转换为标准 E.164 格式以进行呼叫路由。电话拨入式会议访问号码是参与者为加入会议而呼叫的号码。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-p103">During dial-in configuration, you create dial plans and dial-in conferencing access numbers. Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing. Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="b9b6d-p104">每个电话拨入式会议访问号码必须至少与一个拨号计划关联。电话拨入式会议区域会将电话拨入式会议访问号码与其拨号计划相关联。设置拨号计划时，指定应用于该拨号计划的电话拨入式会议区域。在创建拨入访问号码时，选择将该访问号码与相应拨号计划关联的区域。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-p104">Every dial-in conferencing access number must be associated with at least one dial plan. Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans. When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="b9b6d-p105">创建拨号计划时，指定拨号计划的作用域：用户作用域、池作用域或站点作用域。会按照各用户适用的最小作用域为其分配拨号计划。例如，如果适用，则为用户分配用户级别的拨号计划。如果用户级别的拨号计划不适用，则为用户分配池级别的拨号计划。如果池级别的拨号计划不适用，则为用户分配站点级别的拨号计划。如果站点级别的拨号计划不适用，则为用户分配全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-p105">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope. Every user is assigned the dial plan from the narrowest scope that applies to the user. For example, a user is assigned a user-level dial plan, if one applies. If a user-level dial plan does not apply, the user is assigned a pool-level dial plan. If a pool-level dial plan does not apply, the user is assigned a site-level dial plan. If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="b9b6d-p106">配置拨号计划之前，规划命名和使用区域的方式非常重要。对于电话拨入式会议区域，请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="b9b6d-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="b9b6d-133">区域通常是与某个办公室或一组办公室相关联的地理区域。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="b9b6d-p107">语言与拨入访问号码相关联。如果支持具有多种语言的地理区域，应该决定如何定义区域以便支持多种语言。例如，可以基于地理位置和语言的组合定义多个区域，或者基于地理位置定义一个区域，且每种语言拥有不同的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="b9b6d-137">用户安排会议时，默认情况下会议将使用用户的拨号计划所指定的区域。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="b9b6d-138">默认情况下，区域的所有拨入访问号码都会包含在会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="b9b6d-139">命名区域以使其清楚识别，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="b9b6d-140">用户可以使用区域名称更改会议的区域，以便在邀请中包含不同的访问号码。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="b9b6d-141">（当用户使用 Outlook 安排会议时，用户将使用 Lync 2013 的联机会议外接程序更改区域）。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="b9b6d-142">应该对区域加以设计，以便想要拨入会议的被邀请者可以在会议邀请中看到本地访问号码。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="b9b6d-143">您可以使用 Lync Server 命令行管理程序 cmdlet 配置区域中的访问号码在 "电话拨入式会议设置" 页上的显示顺序（因此，它们在会议邀请中的显示顺序）。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="b9b6d-144">任何位置的任何用户均可拨打拨入访问号码来加入会议。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="b9b6d-145">规划会议目录</span><span class="sxs-lookup"><span data-stu-id="b9b6d-145">Planning for Conference Directories</span></span>

<span data-ttu-id="b9b6d-146">会议目录维护参与者在使用 Lync 2013 时用于加入会议的字母数字会议 ID 之间的映射，以及电话拨入式会议参与者用于加入会议的仅数字会议 ID。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="b9b6d-147">会议 ID 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="b9b6d-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="b9b6d-p110">创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。通过使用此指南，通常可使会议 ID 保持较小数目。但是，一旦会议目录的数目（在池中）超过 9，则会议 ID 号将增大以支持其他会议。</span><span class="sxs-lookup"><span data-stu-id="b9b6d-p110">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created. In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9b6d-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9b6d-152">See Also</span></span>


[<span data-ttu-id="b9b6d-153">Lync Server 2013 中的中介服务器组件</span><span class="sxs-lookup"><span data-stu-id="b9b6d-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="b9b6d-154">Lync Server 2013 中的拨号计划和规范化规则</span><span class="sxs-lookup"><span data-stu-id="b9b6d-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

