---
title: Lync Server 2013：配置电话拨入式会议的拨号计划
description: Lync Server 2013：配置电话拨入式会议的拨号计划。
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
ms.openlocfilehash: 28123f905288ce35b6f470168962a3d8e6faa22b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567578"
---
# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="06c3b-103">在 Lync Server 2013 中配置电话拨入式会议的拨号计划</span><span class="sxs-lookup"><span data-stu-id="06c3b-103">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06c3b-104">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="06c3b-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="06c3b-p101">部署电话拨入式会议时，需要创建或修改一个或多个用于路由拨入访问电话号码的拨号计划。确保每个拨号计划中至少有一个规范化规则可以将电话分机号转换为 E.164 格式的完整电话号码。电话拨入式会议的用户通过输入其个人标识号 (PIN) 及其电话号码，可以作为经过身份验证的企业用户加入会议。需要使用规范化规则将分机号转换为完整的电话号码，以便在用户只输入电话分机号时可以对其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="06c3b-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="06c3b-109">要设置电话拨入式会议的拨号计划，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="06c3b-109">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="06c3b-110">无论是否部署企业语音，都要修改全局拨号计划以添加电话拨入式会议区域，并确保规范化规则准确地转换拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="06c3b-110">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="06c3b-111">有关详细说明，请参阅 [在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="06c3b-111">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="06c3b-112">如果未部署企业语音，请创建电话拨入式会议访问号码的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="06c3b-112">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="06c3b-113">确保其中包含电话拨入式会议区域。</span><span class="sxs-lookup"><span data-stu-id="06c3b-113">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="06c3b-114">有关详细说明，请参阅 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="06c3b-114">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="06c3b-115">如果已部署企业语音，请根据需要修改企业语音拨号计划以包含区域，并对拨入访问号码使用适当的规范化规则。</span><span class="sxs-lookup"><span data-stu-id="06c3b-115">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="06c3b-116">有关详细说明，请参阅 [在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="06c3b-116">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="06c3b-117">还可以创建仅用于拨入访问号码的专用拨号计划。</span><span class="sxs-lookup"><span data-stu-id="06c3b-117">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="06c3b-118">有关详细说明，请参阅 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="06c3b-118">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="06c3b-119">有关规划区域的详细信息，请参阅规划文档中的 [Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="06c3b-119">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="06c3b-120">本部分内容</span><span class="sxs-lookup"><span data-stu-id="06c3b-120">In This Section</span></span>

  - [<span data-ttu-id="06c3b-121">在 Lync Server 2013 中查看拨号计划信息</span><span class="sxs-lookup"><span data-stu-id="06c3b-121">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="06c3b-122">在 Lync Server 2013 中创建拨号计划</span><span class="sxs-lookup"><span data-stu-id="06c3b-122">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="06c3b-123">在 Lync Server 2013 中修改拨号计划</span><span class="sxs-lookup"><span data-stu-id="06c3b-123">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="06c3b-124">在 Lync Server 2013 中定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="06c3b-124">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

