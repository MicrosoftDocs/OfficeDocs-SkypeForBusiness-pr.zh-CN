---
title: Lync Server 2013：将用户迁移至企业语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="be685-102">在 Lync Server 2013 中将用户迁移至企业语音</span><span class="sxs-lookup"><span data-stu-id="be685-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be685-103">_**主题上次修改时间：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="be685-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="be685-104">如果您要将用户从现有 PBX 电话基础结构移动到企业语音，则部署过程包括某些步骤，这些步骤不属于[Lync Server 2013 中的 "规划企业语音](lync-server-2013-planning-for-enterprise-voice.md)" 中已描述的规划过程。</span><span class="sxs-lookup"><span data-stu-id="be685-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="be685-105">有关从早期的企业语音部署迁移用户的信息，请参阅安装媒体附带的迁移文档。</span><span class="sxs-lookup"><span data-stu-id="be685-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="be685-106">将用户从现有的电话基础结构移动到企业语音的过程包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="be685-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="be685-107">指定主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="be685-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="be685-108">为用户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="be685-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="be685-109">为用户准备拨号计划。</span><span class="sxs-lookup"><span data-stu-id="be685-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="be685-110">规划用户语音策略。</span><span class="sxs-lookup"><span data-stu-id="be685-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="be685-111">计划呼叫流程。</span><span class="sxs-lookup"><span data-stu-id="be685-111">Plan call routes.</span></span>

6.  <span data-ttu-id="be685-112">将 PBX 或 SIP 干线配置为对启用企业语音的用户重新路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="be685-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="be685-113">将用户移动到 Exchange 统一消息（UM）（推荐）。</span><span class="sxs-lookup"><span data-stu-id="be685-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="be685-114">本主题介绍每个步骤所需的规划。</span><span class="sxs-lookup"><span data-stu-id="be685-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="be685-115">第 1 步</span><span class="sxs-lookup"><span data-stu-id="be685-115">Step 1.</span></span> <span data-ttu-id="be685-116">指定主要电话号码</span><span class="sxs-lookup"><span data-stu-id="be685-116">Designate primary phone numbers</span></span>

<span data-ttu-id="be685-117">企业语音与其他邮件媒体集成语音，这样，当传入呼叫到达服务器时，服务器会将该号码映射到用户的 SIP URI，然后将该呼叫派生到与该 SIP URI 关联的所有客户终结点。</span><span class="sxs-lookup"><span data-stu-id="be685-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="be685-118">此过程要求每个用户都与一个主要电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="be685-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="be685-119">主要电话号码必须：</span><span class="sxs-lookup"><span data-stu-id="be685-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="be685-120">全球唯一的或在内部扩展的情况下，企业中的独特之处。</span><span class="sxs-lookup"><span data-stu-id="be685-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="be685-121">企业中拥有和可路由的。</span><span class="sxs-lookup"><span data-stu-id="be685-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="be685-122">不应使用个人号码。</span><span class="sxs-lookup"><span data-stu-id="be685-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="be685-123">企业用户可以在 Active Directory 域服务中为其列出两个或多个电话号码。</span><span class="sxs-lookup"><span data-stu-id="be685-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="be685-124">在 Active Directory 用户和计算机管理单元中，可以在该用户的属性表上查看或更改与特定用户相关联的所有电话号码。</span><span class="sxs-lookup"><span data-stu-id="be685-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="be685-125">"**用户属性**" 对话框的 "**常规**" 选项卡上的 "**电话号码**" 框应包含用户的主工作电话号码。</span><span class="sxs-lookup"><span data-stu-id="be685-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="be685-126">此号码通常指定为用户的主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="be685-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="be685-127">某些用户可能有特殊要求（例如，希望所有传入呼叫通过行政助理进行路由的管理者），但此类例外仅限于需要明确且关键的用户。</span><span class="sxs-lookup"><span data-stu-id="be685-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="be685-128">选择主号码后，它必须：</span><span class="sxs-lookup"><span data-stu-id="be685-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="be685-129">尽可能规范化为. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="be685-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="be685-130">已复制到 Active Directory **msRTCSIP line**属性。</span><span class="sxs-lookup"><span data-stu-id="be685-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be685-131"><STRONG>与远程呼叫控制（RCC）共存</STRONG></span><span class="sxs-lookup"><span data-stu-id="be685-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="be685-132">RCC 是使用 Lync Server 监控和控制桌面 PBX 电话的功能。</span><span class="sxs-lookup"><span data-stu-id="be685-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="be685-133">控制通过服务器路由，它充当 PBX 的网关。</span><span class="sxs-lookup"><span data-stu-id="be685-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="be685-134">尽管不能同时为 RCC 和企业语音配置用户，但行 URI 设置会在任何一种情况下都指定用户的主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="be685-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="be685-135">如果你有一个现有的 PBX 基础结构，而你希望选择用户继续使用，则可以在你的组织中以增量方式引入企业语音。</span><span class="sxs-lookup"><span data-stu-id="be685-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="be685-136">有关此部署方案的详细信息，请参阅规划文档中<A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013 中的直接 SIP 部署选项</A>。</span><span class="sxs-lookup"><span data-stu-id="be685-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="be685-137">在以前的版本中，你可以为用户启用 RCC 和企业语音，但仅当你还为双重呼叫配置了用户时，传入呼叫将同时拨打用户的 PBX 手机和 Communicator。</span><span class="sxs-lookup"><span data-stu-id="be685-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="be685-138">在 Lync Server 2010 中，不支持双分叉。</span><span class="sxs-lookup"><span data-stu-id="be685-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="be685-139">填充**msRTCSIP**属性有三种方法：</span><span class="sxs-lookup"><span data-stu-id="be685-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="be685-140">Microsoft 身份集成服务器（推荐）</span><span class="sxs-lookup"><span data-stu-id="be685-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="be685-141">Lync Server "控制面板" 中的 "**用户**" 页面</span><span class="sxs-lookup"><span data-stu-id="be685-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="be685-142">必须处理多个电话号码时，由您的组织制定的脚本自定义是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="be685-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="be685-143">根据您的组织如何表示 Active Directory 域服务中的电话号码，该脚本可能必须先将主要电话号码正常化为164个格式，然后才能将其复制到**msRTCSIP**属性。</span><span class="sxs-lookup"><span data-stu-id="be685-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="be685-144">如果你的组织以单个格式维护 Active Directory 域服务中的所有电话号码，并且如果该格式为 E.i，则你的脚本只需要将每个主要电话号码写入**msRTCSIP**属性。</span><span class="sxs-lookup"><span data-stu-id="be685-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="be685-145">如果你的组织以单个格式维护 Active Directory 域服务中的所有电话号码，但该格式不是 E.i，则你的脚本应定义一个相应的规范化规则，以便将主要电话号码从其现有格式转换为 MsRTCSIP，然后再将其写入到\*\*\*\* 属性。</span><span class="sxs-lookup"><span data-stu-id="be685-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="be685-146">如果你的组织未对 Active Directory 域服务中的电话号码强制使用标准格式，你的脚本应定义适当的规范化规则，以便将主要电话号码从其各种格式转换为 MsRTCSIP，然后再将主要电话号码写入\*\*\*\* 属性。</span><span class="sxs-lookup"><span data-stu-id="be685-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="be685-147">你的脚本还必须插入前缀**电话：** 在每个主号码之前，将其写入**msRTCSIP**属性。</span><span class="sxs-lookup"><span data-stu-id="be685-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="be685-148">此属性中指定的数字的预期格式为：</span><span class="sxs-lookup"><span data-stu-id="be685-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="be685-149">电话： + 14255550100; ext = 50100。</span><span class="sxs-lookup"><span data-stu-id="be685-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="be685-150">电话：5550100（适用于唯一的企业级扩展）</span><span class="sxs-lookup"><span data-stu-id="be685-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="be685-151">由通讯簿服务（ABS）执行的规范化不替换或消除了在 Active Directory 域服务中对每个用户的主要电话号码进行规范化的需要，因为 ABS 对 Active directory 域服务没有访问权限，因此无法将主数字复制到<STRONG>msRTCSIP</STRONG>属性。</span><span class="sxs-lookup"><span data-stu-id="be685-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="be685-152">第 2 步</span><span class="sxs-lookup"><span data-stu-id="be685-152">Step 2.</span></span> <span data-ttu-id="be685-153">为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="be685-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="be685-154">除了确定要启用哪些用户之外，不需要特殊计划来完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="be685-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="be685-155">第 3 步</span><span class="sxs-lookup"><span data-stu-id="be685-155">Step 3.</span></span> <span data-ttu-id="be685-156">为用户准备拨号计划。</span><span class="sxs-lookup"><span data-stu-id="be685-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="be685-157">已启用企业语音的用户将无法在没有拨号计划的情况下拨打 PSTN。</span><span class="sxs-lookup"><span data-stu-id="be685-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="be685-158">拨号计划是一组指定的规范化规则，可将指定位置、单个用户或联系人对象的电话号码转换为统一标准 (E.164) 格式，以进行电话授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="be685-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="be685-159">规范化规则定义如何针对每个指定的位置、用户或联系人对象来路由以不同格式表示的电话号码。</span><span class="sxs-lookup"><span data-stu-id="be685-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="be685-160">有关准备拨号计划的信息，请参阅[Lync Server 2013 中的 "拨号计划和规范规则](lync-server-2013-dial-plans-and-normalization-rules.md)"。</span><span class="sxs-lookup"><span data-stu-id="be685-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="be685-161">第 4 步</span><span class="sxs-lookup"><span data-stu-id="be685-161">Step 4.</span></span> <span data-ttu-id="be685-162">规划用户语音策略</span><span class="sxs-lookup"><span data-stu-id="be685-162">Plan user voice policies</span></span>

<span data-ttu-id="be685-163">在旧式 PBX （如从公司电话进行长途或国际长途）的用户级服务设置必须重新配置为将用户移动到企业语音的 VoIP 策略。</span><span class="sxs-lookup"><span data-stu-id="be685-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="be685-164">有关为企业语音规划和创建策略的详细信息，请参阅[Lync Server 2013 中的语音策略](lync-server-2013-voice-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="be685-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="be685-165">第 5 步</span><span class="sxs-lookup"><span data-stu-id="be685-165">Step 5.</span></span> <span data-ttu-id="be685-166">规划出站呼叫流程</span><span class="sxs-lookup"><span data-stu-id="be685-166">Plan outbound call routes</span></span>

<span data-ttu-id="be685-167">呼叫路线指定 Lync 服务器如何处理由企业语音用户发出的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="be685-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="be685-168">当用户拨号码时，服务器（如有必要）会将拨号字符串标准化为164格式，并尝试将其与 SIP URI 匹配。</span><span class="sxs-lookup"><span data-stu-id="be685-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="be685-169">如果服务器无法进行匹配，它将基于该号码应用传出呼叫路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="be685-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="be685-170">定义该逻辑的最后一步是为每个拨号计划中列出的每组目标电话号码创建单独的命名呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="be685-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="be685-171">有关规划呼叫路由的详细信息，请参阅[Lync Server 2013 中的语音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="be685-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="be685-172">第 6 步</span><span class="sxs-lookup"><span data-stu-id="be685-172">Step 6.</span></span> <span data-ttu-id="be685-173">配置 PBX 或 SIP 干线以重排企业语音用户的呼叫</span><span class="sxs-lookup"><span data-stu-id="be685-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="be685-174">以前托管于传统 PBX 或在与 Internet 电话服务提供商（ITSP）的 SIP 中继连接上的用户在移动后保留其电话号码。</span><span class="sxs-lookup"><span data-stu-id="be685-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="be685-175">唯一的要求是在移动后，必须重新配置 PBX 或 SIP 干线，才能将企业语音用户的传入呼叫路由到中介服务器。</span><span class="sxs-lookup"><span data-stu-id="be685-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="be685-176">第 7 步</span><span class="sxs-lookup"><span data-stu-id="be685-176">Step 7.</span></span> <span data-ttu-id="be685-177">将用户移动到 Exchange 统一消息（推荐）</span><span class="sxs-lookup"><span data-stu-id="be685-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="be685-178">将用户移动到 Exchange 统一消息包含以下任务：</span><span class="sxs-lookup"><span data-stu-id="be685-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="be685-179">将 Exchange 统一消息和 Lync 服务器配置为协同工作。</span><span class="sxs-lookup"><span data-stu-id="be685-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="be685-180">为用户启用 Exchange 统一消息呼叫应答和 Outlook Voice Access。</span><span class="sxs-lookup"><span data-stu-id="be685-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="be685-181">此任务在 Exchange 统一消息服务器上执行。</span><span class="sxs-lookup"><span data-stu-id="be685-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="be685-182">有关详细信息，请参阅 Exchange Server 2010 中的[http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)"TechNet 库"。</span><span class="sxs-lookup"><span data-stu-id="be685-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

