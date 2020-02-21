---
title: Lync Server 2013：配置电话拨入式会议的拨号计划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a86bf3061c714089ee326a729d0dd43ef267b8e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="ccca7-102">在 Lync Server 2013 中配置电话拨入式会议的拨号计划</span><span class="sxs-lookup"><span data-stu-id="ccca7-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccca7-103">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="ccca7-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="ccca7-p101">部署电话拨入式会议时，需要创建或修改一个或多个用于路由拨入访问电话号码的拨号计划。确保每个拨号计划中至少有一个规范化规则可以将电话分机号转换为 E.164 格式的完整电话号码。电话拨入式会议的用户通过输入其个人标识号 (PIN) 及其电话号码，可以作为经过身份验证的企业用户加入会议。需要使用规范化规则将分机号转换为完整的电话号码，以便在用户只输入电话分机号时可以对其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ccca7-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="ccca7-108">要设置电话拨入式会议的拨号计划，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ccca7-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="ccca7-109">无论是否部署企业语音，都要修改全局拨号计划以添加电话拨入式会议区域，并确保规范化规则准确地转换拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="ccca7-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="ccca7-110">有关详细说明，请参阅[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="ccca7-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="ccca7-111">如果未部署企业语音，请创建电话拨入式会议访问号码的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="ccca7-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="ccca7-112">确保其中包含电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="ccca7-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="ccca7-113">有关详细说明，请参阅[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="ccca7-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="ccca7-114">如果已部署企业语音，请根据需要修改企业语音拨号计划以包含区域，并对拨入访问号码使用适当的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="ccca7-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="ccca7-115">有关详细说明，请参阅[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="ccca7-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="ccca7-116">还可以创建仅用于拨入访问号码的专用拨号计划。</span><span class="sxs-lookup"><span data-stu-id="ccca7-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="ccca7-117">有关详细说明，请参阅[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="ccca7-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="ccca7-118">有关规划区域的详细信息，请参阅规划文档中的[Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ccca7-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ccca7-119">本部分内容</span><span class="sxs-lookup"><span data-stu-id="ccca7-119">In This Section</span></span>

  - [<span data-ttu-id="ccca7-120">在 Lync Server 2013 中查看拨号计划信息</span><span class="sxs-lookup"><span data-stu-id="ccca7-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="ccca7-121">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="ccca7-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="ccca7-122">在 Lync Server 2013 中修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="ccca7-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="ccca7-123">在 Lync Server 2013 中定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="ccca7-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

