---
title: Lync Server 2013：将用户移动到企业语音
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
ms.openlocfilehash: 5554a9c7fde74b5bcf9c81c451023d0f48bbf918
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="c5b30-102">将用户移动到 Lync Server 2013 中的企业语音</span><span class="sxs-lookup"><span data-stu-id="c5b30-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5b30-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c5b30-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c5b30-104">如果要将用户从现有的 PBX 电话基础结构移动到企业语音，则部署过程包括一些步骤，这些步骤不是在[Lync Server 2013 中规划企业语音中](lync-server-2013-planning-for-enterprise-voice.md)已介绍的规划过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="c5b30-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="c5b30-105">有关从早期的企业语音部署迁移用户的信息，请参阅安装介质中包含的迁移文档。</span><span class="sxs-lookup"><span data-stu-id="c5b30-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="c5b30-106">将用户从现有的电话基础结构迁移到企业语音的过程包含以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c5b30-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="c5b30-107">指定主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b30-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="c5b30-108">为用户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="c5b30-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="c5b30-109">为用户准备拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c5b30-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="c5b30-110">规划用户语音策略。</span><span class="sxs-lookup"><span data-stu-id="c5b30-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="c5b30-111">规划呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="c5b30-111">Plan call routes.</span></span>

6.  <span data-ttu-id="c5b30-112">将 PBX 或 SIP 中继配置为对启用了企业语音的用户重新路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="c5b30-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="c5b30-113">将用户移动到 Exchange 统一消息（UM）（推荐）。</span><span class="sxs-lookup"><span data-stu-id="c5b30-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="c5b30-114">本主题介绍上述每个步骤所必需的规划。</span><span class="sxs-lookup"><span data-stu-id="c5b30-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="c5b30-p102">步骤 1. 指定主要电话号码</span><span class="sxs-lookup"><span data-stu-id="c5b30-p102">Step 1. Designate primary phone numbers</span></span>

<span data-ttu-id="c5b30-p103">企业语音将语音与其他消息传递媒体集成在一起，这样，当传入呼叫到达服务器时，服务器会将该号码映射到用户的 SIP-URI，然后将该呼叫定向到与该 SIP-URI 相关联的所有客户端终结点。此过程要求每个用户都与一个主要电话号码相关联。</span><span class="sxs-lookup"><span data-stu-id="c5b30-p103">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI. This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="c5b30-119">主要电话号码必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="c5b30-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="c5b30-120">全局唯一，如果是内部分机，则必须在企业中保持唯一。</span><span class="sxs-lookup"><span data-stu-id="c5b30-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="c5b30-p104">由企业拥有且可路由。不应当使用个人号码。</span><span class="sxs-lookup"><span data-stu-id="c5b30-p104">Owned by and routable in the enterprise. Personal numbers should not be used.</span></span>

<span data-ttu-id="c5b30-123">企业用户可以在 Active Directory 域服务中为其列出两个或更多的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b30-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="c5b30-124">与特定用户相关联的所有电话号码都可以在“Active Directory 用户和计算机”管理单元中该用户的属性表中进行查看或更改。</span><span class="sxs-lookup"><span data-stu-id="c5b30-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="c5b30-p106">**“用户属性”** 对话框的 **“常规”** 选项卡上的 **“电话号码”** 框应当包含该用户的主要单位号码。此号码通常被指定为该用户的主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b30-p106">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number. This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="c5b30-127">某些用户可能会有特殊要求（例如，主管经理希望所有的传入呼叫都通过行政助理路由），但是这样的例外应当仅限于有明确需求的关键人员。</span><span class="sxs-lookup"><span data-stu-id="c5b30-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="c5b30-128">选择了主要号码之后，必须将它：</span><span class="sxs-lookup"><span data-stu-id="c5b30-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="c5b30-129">规范化为 E.164 格式（只要可能）。</span><span class="sxs-lookup"><span data-stu-id="c5b30-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="c5b30-130">复制到 Active Directory **msRTCSIP-line** 属性。</span><span class="sxs-lookup"><span data-stu-id="c5b30-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5b30-131"><STRONG>与远程呼叫控制 (RCC) 共存</STRONG></span><span class="sxs-lookup"><span data-stu-id="c5b30-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="c5b30-132">RCC 是一种使用 Lync Server 监视和控制桌面 PBX 电话的功能。</span><span class="sxs-lookup"><span data-stu-id="c5b30-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="c5b30-133">远程呼叫控制是通过充当 PBX 网关的服务器路由的。</span><span class="sxs-lookup"><span data-stu-id="c5b30-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="c5b30-134">尽管无法同时为用户配置 RCC 和企业语音，但线路 URL 设置在任一情况下都会指定用户的主要电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b30-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="c5b30-135">如果希望选定用户继续使用现有的 PBX 基础结构，则可在组织中逐步引入企业语音。</span><span class="sxs-lookup"><span data-stu-id="c5b30-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="c5b30-136">有关此部署方案的详细信息，请参阅规划文档中的<A href="lync-server-2013-direct-sip-deployment-options.md">Lync Server 2013 中的直接 SIP 部署选项</A>。</span><span class="sxs-lookup"><span data-stu-id="c5b30-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="c5b30-137">在以前的版本中，您可以为用户启用 RCC 和企业语音，但前提是您还为用户配置了双分叉，即传入呼叫将同时拨打用户的 PBX 电话和 Communicator 的功能。</span><span class="sxs-lookup"><span data-stu-id="c5b30-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="c5b30-138">在 Lync Server 2010 中，不支持双重分叉。</span><span class="sxs-lookup"><span data-stu-id="c5b30-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="c5b30-139">可通过三种方法来填充 **msRTCSIP-line** 属性：</span><span class="sxs-lookup"><span data-stu-id="c5b30-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="c5b30-140">Microsoft 身份集成服务器（推荐）</span><span class="sxs-lookup"><span data-stu-id="c5b30-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="c5b30-141">Lync Server "控制面板" 中的 "**用户**" 页</span><span class="sxs-lookup"><span data-stu-id="c5b30-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="c5b30-142">在必须处理多少个电话号码的情况下，由您的组织开发的脚本自定义是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="c5b30-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="c5b30-143">根据您所在组织在 Active Directory 域服务中表示电话号码的方式，脚本可能必须先将主要电话号码规范化为 E.164 格式，然后再将这些号码复制到 **msRTCSIP-line** 属性。</span><span class="sxs-lookup"><span data-stu-id="c5b30-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="c5b30-144">如果您所在组织保持 Active Directory 域服务中的所有电话号码都采用一种格式，而且如果该格式为 E.164，则脚本只需要将每个主要电话号码写入 **msRTCSIP-line** 属性。</span><span class="sxs-lookup"><span data-stu-id="c5b30-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="c5b30-145">如果您所在组织保持 Active Directory 域服务中的所有电话号码都采用一种格式，但该格式不是 E.164，则脚本应当定义一个相应的规范化规则，先将主要电话号码从其现有格式转换为 E.164，然后再将这些号码写入 **msRTCSIP-line** 属性。</span><span class="sxs-lookup"><span data-stu-id="c5b30-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="c5b30-146">如果您所在组织不强制 Active Directory 域服务中的电话号码采用标准格式，则脚本应当定义相应的规范化规则，先将主要电话号码从其各自格式转换为符合 E.164 的格式，然后再将这些主要电话号码写入 **msRTCSIP-line** 属性。</span><span class="sxs-lookup"><span data-stu-id="c5b30-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="c5b30-147">脚本还必须先在每个主要电话号码前面插入前缀 **Tel:**，然后再将这些主要电话号码写入 **msRTCSIP-line** 属性。</span><span class="sxs-lookup"><span data-stu-id="c5b30-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="c5b30-148">在此属性中指定的号码格式应当如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5b30-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="c5b30-149">电话： + 14255550100; ext = 50100。</span><span class="sxs-lookup"><span data-stu-id="c5b30-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="c5b30-150">Tel:5550100（对于企业范围内唯一的分机）</span><span class="sxs-lookup"><span data-stu-id="c5b30-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c5b30-151">即使由通讯簿服务 (ABS) 执行规范化之后，也需要对 Active Directory 域服务中每个用户的主要电话号码进行规范化，这是由于 ABS 无权访问 Active Directory 域服务，因此无法将主要号码复制到 <STRONG>msRTCSIP-line</STRONG> 属性。</span><span class="sxs-lookup"><span data-stu-id="c5b30-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="c5b30-p111">步骤 2. 为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="c5b30-p111">Step 2. Enable users for Enterprise Voice</span></span>

<span data-ttu-id="c5b30-154">除了标识要启用的用户，无需进行其他特殊规划即可完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="c5b30-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="c5b30-p112">步骤 3. 为用户准备拨号计划。</span><span class="sxs-lookup"><span data-stu-id="c5b30-p112">Step 3. Prepare dial plans for users.</span></span>

<span data-ttu-id="c5b30-p113">已启用企业语音的用户在没有拨号计划的情况下将无法向 PSTN 发起呼叫。拨号计划是一组指定的规范化规则，可将指定位置、单个用户或联系人对象的电话号码转换为统一标准 (E.164) 格式，以进行电话授权和呼叫路由。规范化规则定义如何针对每个指定的位置、用户或联系人对象来路由以不同格式表示的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b30-p113">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place. A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing. Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="c5b30-160">有关准备拨号计划的信息，请参阅[Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b30-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="c5b30-161">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="c5b30-161">Step 4.</span></span> <span data-ttu-id="c5b30-162">规划用户语音策略</span><span class="sxs-lookup"><span data-stu-id="c5b30-162">Plan user voice policies</span></span>

<span data-ttu-id="c5b30-163">随着用户的 VoIP 策略迁移到企业语音，必须重新配置旧版 PBX 上的用户服务级别设置（如从公司电话拨打长途或国际长途电话的权限）。</span><span class="sxs-lookup"><span data-stu-id="c5b30-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="c5b30-164">有关规划和创建企业语音策略的详细信息，请参阅[Lync Server 2013 中的语音策略](lync-server-2013-voice-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b30-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="c5b30-165">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="c5b30-165">Step 5.</span></span> <span data-ttu-id="c5b30-166">规划出站呼叫路由</span><span class="sxs-lookup"><span data-stu-id="c5b30-166">Plan outbound call routes</span></span>

<span data-ttu-id="c5b30-167">呼叫路由指定 Lync Server 如何处理由企业语音用户发出的出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="c5b30-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="c5b30-168">当用户拨打号码时，服务器在必要时将拨号串规范为 E.164 格式，并尝试将它与 SIP URI 进行匹配。</span><span class="sxs-lookup"><span data-stu-id="c5b30-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="c5b30-169">如果服务器无法进行匹配，它将基于该号码应用传出呼叫路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="c5b30-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="c5b30-170">定义该逻辑的最后一步是为每个拨号计划中所列出的每组目标电话号码创建单独的命名呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="c5b30-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="c5b30-171">有关规划呼叫路由的详细信息，请参阅[Lync Server 2013 中的语音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="c5b30-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="c5b30-172">步骤 6.</span><span class="sxs-lookup"><span data-stu-id="c5b30-172">Step 6.</span></span> <span data-ttu-id="c5b30-173">将 PBX 或 SIP 中继配置为重新路由企业语音用户的呼叫</span><span class="sxs-lookup"><span data-stu-id="c5b30-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="c5b30-174">迁移之后，以前在传统 PBX 或到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接上承载的用户仍保留其电话号码。</span><span class="sxs-lookup"><span data-stu-id="c5b30-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="c5b30-175">唯一要求是移动后，必须重新配置 PBX 或 SIP 中继，才能将企业语音用户的传入呼叫路由到中介服务器。</span><span class="sxs-lookup"><span data-stu-id="c5b30-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="c5b30-p120">步骤 7. 将用户迁移到 Exchange 统一消息（推荐）</span><span class="sxs-lookup"><span data-stu-id="c5b30-p120">Step 7. Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="c5b30-178">将用户迁移到 Exchange 统一消息包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="c5b30-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="c5b30-179">将 Exchange 统一消息和 Lync Server 配置为协同工作。</span><span class="sxs-lookup"><span data-stu-id="c5b30-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="c5b30-180">为用户启用 Exchange 统一消息呼叫应答和 Outlook Voice Access。</span><span class="sxs-lookup"><span data-stu-id="c5b30-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="c5b30-181">此任务在 Exchange 统一消息服务器上执行。</span><span class="sxs-lookup"><span data-stu-id="c5b30-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="c5b30-182">有关详细信息，请参阅 Exchange Server 2010 TechNet Library [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372)（网址为）。</span><span class="sxs-lookup"><span data-stu-id="c5b30-182">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

