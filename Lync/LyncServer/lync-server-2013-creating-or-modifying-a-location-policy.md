---
title: Lync Server 2013：创建或修改位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1648e845fc3759e7083c2443013f89fb49c1b00f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="12bb7-102">在 Lync Server 2013 中创建或修改位置策略</span><span class="sxs-lookup"><span data-stu-id="12bb7-102">Creating or modifying a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12bb7-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12bb7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12bb7-104">在 Lync Server 2013 中，你可以使用位置策略应用与增强的9-1-1 （E9）功能以及用户或联系人的位置设置相关的设置。</span><span class="sxs-lookup"><span data-stu-id="12bb7-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="12bb7-105">位置策略确定用户是否启用了 E9-1，如果是紧急呼叫，该行为是什么。</span><span class="sxs-lookup"><span data-stu-id="12bb7-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="12bb7-106">例如，您可以使用位置策略定义哪个号码构成紧急呼叫（例如，美国911）、是否应自动通知企业安全以及如何路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="12bb7-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="12bb7-107">你可以从 Lync Server 2013 控制面板中的 "**网络配置**" 组配置位置策略。</span><span class="sxs-lookup"><span data-stu-id="12bb7-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="12bb7-108">从 Lync Server 控制面板，您可以查看、创建、修改或删除位置策略。</span><span class="sxs-lookup"><span data-stu-id="12bb7-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="12bb7-109">使用此部分中的过程创建或修改位置策略。</span><span class="sxs-lookup"><span data-stu-id="12bb7-109">Use the procedures in this section to create or modify a location policy.</span></span> <span data-ttu-id="12bb7-110">有关删除位置策略的详细信息，请参阅[在 Lync Server 2013 中删除位置策略](lync-server-2013-deleting-a-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="12bb7-110">For details on deleting location policies, see [Deleting a location policy in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).</span></span>

<span data-ttu-id="12bb7-111">在 Lync Server 2013 中，你可以覆盖来自位置信息服务的位置更新的客户端请求之间的默认时间量。</span><span class="sxs-lookup"><span data-stu-id="12bb7-111">In Lync Server 2013, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="12bb7-112">默认值为4小时。</span><span class="sxs-lookup"><span data-stu-id="12bb7-112">The default value is 4 hours.</span></span> <span data-ttu-id="12bb7-113">将**CsLocationPolicy** Cmdlet 与 LocationRefreshInterval 参数配合使用，以替代默认值。</span><span class="sxs-lookup"><span data-stu-id="12bb7-113">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="12bb7-114">在 Lync Server "控制面板" 中创建新的位置策略</span><span class="sxs-lookup"><span data-stu-id="12bb7-114">To create a new location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="12bb7-115">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="12bb7-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12bb7-116">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12bb7-117">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="12bb7-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12bb7-118">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**位置策略**"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-118">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="12bb7-119">在 "**位置策略**" 页面上，单击 "**新建**"，然后选择要创建的策略类型：</span><span class="sxs-lookup"><span data-stu-id="12bb7-119">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="12bb7-120">若要创建网站策略，请单击 "**网站策略**"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-120">To create a site policy, click **Site policy**.</span></span> <span data-ttu-id="12bb7-121">在 "**选择网站**" 中，选择要应用策略的网站，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="12bb7-121">In **Select a Site**, choose the site to which you want the policy applied and click **OK**.</span></span> <span data-ttu-id="12bb7-122">在 "**新建位置策略**" 页上，"**范围**" 字段包含 "值"**网站**，"**名称**" 字段包含您选择的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="12bb7-122">On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose.</span></span> <span data-ttu-id="12bb7-123">您不能修改这些字段中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="12bb7-123">You cannot modify either of these fields.</span></span> <span data-ttu-id="12bb7-124">网站策略将自动应用到指定网站上的所有用户，并替代这些用户的全局策略。</span><span class="sxs-lookup"><span data-stu-id="12bb7-124">A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="12bb7-125">若要创建**用户策略**，请单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-125">To create a **User policy**, click **User policy**.</span></span> <span data-ttu-id="12bb7-126">在**新的位置策略**中，"**范围**" 域包含 "**用户**" 值。</span><span class="sxs-lookup"><span data-stu-id="12bb7-126">In the **New Location Policy**, the **Scope** field contains the value **User**.</span></span> <span data-ttu-id="12bb7-127">您不能修改此值。</span><span class="sxs-lookup"><span data-stu-id="12bb7-127">You cannot modify this value.</span></span> <span data-ttu-id="12bb7-128">在 "**名称**" 字段中，键入要赋予此策略的名称。</span><span class="sxs-lookup"><span data-stu-id="12bb7-128">In the **Name** field, type the name you want to give this policy.</span></span> <span data-ttu-id="12bb7-129">用户策略不会自动应用到任何用户。</span><span class="sxs-lookup"><span data-stu-id="12bb7-129">A user policy does not automatically apply to any users.</span></span> <span data-ttu-id="12bb7-130">创建用户策略后，必须手动向要应用策略的用户或网络网站授予该策略。</span><span class="sxs-lookup"><span data-stu-id="12bb7-130">After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="12bb7-131">按如下方式填写其余字段：</span><span class="sxs-lookup"><span data-stu-id="12bb7-131">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="12bb7-132">**启用增强的紧急服务**   选中此复选框可启用与此策略关联的用户 E9-1。</span><span class="sxs-lookup"><span data-stu-id="12bb7-132">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="12bb7-133">启用紧急服务时，Lync Server 客户将在注册时检索位置信息，并在进行紧急呼叫时包含该信息。</span><span class="sxs-lookup"><span data-stu-id="12bb7-133">When emergency services are enabled, Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="12bb7-134">**位置**   指定下列值之一：</span><span class="sxs-lookup"><span data-stu-id="12bb7-134">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="12bb7-135">**必填**   当客户端注册到新位置时，系统会提示用户输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="12bb7-135">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="12bb7-136">用户可以在不输入任何信息的情况下关闭提示。</span><span class="sxs-lookup"><span data-stu-id="12bb7-136">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="12bb7-137">如果输入了信息，紧急服务提供商将首先答复紧急电话，以便在将位置路由到公共安全应答点（PSAP）运算符（即911接线员）之前对该位置进行验证。</span><span class="sxs-lookup"><span data-stu-id="12bb7-137">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="12bb7-138">**不要求**   用户将不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="12bb7-138">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="12bb7-139">当拨打没有位置信息的电话时，紧急服务提供商将接听呼叫并请求一个位置。</span><span class="sxs-lookup"><span data-stu-id="12bb7-139">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="12bb7-140">**免责声明**   此选项与**必需**的相同，只是用户无法在不输入位置信息的情况下取消提示。</span><span class="sxs-lookup"><span data-stu-id="12bb7-140">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="12bb7-141">用户仍然可以完成紧急呼叫，但无需输入信息即可完成任何其他通话。</span><span class="sxs-lookup"><span data-stu-id="12bb7-141">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="12bb7-142">此外，将向用户显示免责声明文本，可向用户发出提示，提醒他们注意您拒绝输入位置信息的后果。</span><span class="sxs-lookup"><span data-stu-id="12bb7-142">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="12bb7-143">若要设置免责声明文本，必须使用 Lync Server Management Shell 使用 EnhancedEmergencyServiceDisclaimer 参数运行**CsLocationPolicy** Cmdlet 或**CsLocationPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="12bb7-143">To set the disclaimer text, you must use Lync Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="12bb7-144">有关详细信息，请参阅 Lync Server Management Shell 文档中的 "[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) " 或 "[新建-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) "。</span><span class="sxs-lookup"><span data-stu-id="12bb7-144">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) in the Lync Server Management Shell documentation.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="12bb7-145">在 Lync Server 2013 中，你可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明，与 Lync Server 2010 中不同，你可以仅为整个组织指定全局免责声明。</span><span class="sxs-lookup"><span data-stu-id="12bb7-145">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users, unlike in Lync Server 2010 where you could specify only a global disclaimer for the entire organization.</span></span>

            
            </div>
    
      - <span data-ttu-id="12bb7-146">**针对紧急服务的使用位置只有**   Lync 可以出于各种原因而使用位置信息（例如，通知团队成员当前位置）。</span><span class="sxs-lookup"><span data-stu-id="12bb7-146">**Use location for emergency services only**   Lync can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="12bb7-147">选中此复选框以确保位置信息仅可用于紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="12bb7-147">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="12bb7-148">**PSTN 使用**   公共交换电话网络（PSTN）使用，用于确定将使用此配置文件从客户端路由紧急呼叫的语音路线。</span><span class="sxs-lookup"><span data-stu-id="12bb7-148">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="12bb7-149">与此使用关联的路由应指向专用于紧急呼叫的 SIP 中继，或者指向紧急位置标识号码（ELIN）网关，该网关将紧急呼叫路由到最近的公共安全应答点（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="12bb7-149">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="12bb7-150">**紧急电话号码**   拨打的电话号码，以达到紧急服务。</span><span class="sxs-lookup"><span data-stu-id="12bb7-150">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="12bb7-151">在美国，此值为911。</span><span class="sxs-lookup"><span data-stu-id="12bb7-151">In the United States this value is 911.</span></span> <span data-ttu-id="12bb7-152">该字符串必须由数字0到9组成，并且长度可以介于1到10个数字之间。</span><span class="sxs-lookup"><span data-stu-id="12bb7-152">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="12bb7-153">**紧急拨号屏蔽**   拨号时要转换为 "紧急电话拨号码" 值的号码。</span><span class="sxs-lookup"><span data-stu-id="12bb7-153">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="12bb7-154">例如，如果您在此字段中输入了212的值，"紧急电话拨号码" 字段的值为911，则如果用户212拨打电话，将对911发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="12bb7-154">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="12bb7-155">这样就允许拨打备用紧急号码，并且仍可接通紧急服务（例如，来自使用不同紧急号码的国家/地区的人员可以尝试拨打自己国家/地区的号码，而不是拨打其当前所在国家/地区的号码）。</span><span class="sxs-lookup"><span data-stu-id="12bb7-155">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="12bb7-156">可以通过使用分号分隔值来定义多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="12bb7-156">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="12bb7-157">例如，212;414。</span><span class="sxs-lookup"><span data-stu-id="12bb7-157">For example, 212;414.</span></span> <span data-ttu-id="12bb7-158">字符串的最大长度为100个字符。</span><span class="sxs-lookup"><span data-stu-id="12bb7-158">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="12bb7-159">每个字符都必须为 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="12bb7-159">Each character must be a digit 0 through 9.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="12bb7-160">确保指定的拨号掩码值与 "呼叫驻留" 轨道范围中的数字不同。</span><span class="sxs-lookup"><span data-stu-id="12bb7-160">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="12bb7-161">呼叫寄存路由将优先于紧急拨号字符串转换。</span><span class="sxs-lookup"><span data-stu-id="12bb7-161">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="12bb7-162">若要查看现有的呼叫公园轨道范围，请单击左侧导航栏中的 "<STRONG>语音功能</STRONG>"，然后单击 "<STRONG>呼叫寄存</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-162">To see the existing call park orbit ranges, click <STRONG>Voice Features</STRONG> in the left navigation bar and then click <STRONG>Call Park</STRONG>.</span></span> <span data-ttu-id="12bb7-163">有关详细信息，请参阅<A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">在 Lync Server 2013 中配置停车通话的电话号码扩展</A>。</span><span class="sxs-lookup"><span data-stu-id="12bb7-163">For details, see <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure phone number extensions for parking calls in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="12bb7-164">\*\*\*\*   发出紧急呼叫时通知的一个或多个 SIP 统一资源标识符（uri）的通知 URI。</span><span class="sxs-lookup"><span data-stu-id="12bb7-164">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="12bb7-165">例如，只要进行紧急呼叫，公司安全办公室就会收到即时消息通知。</span><span class="sxs-lookup"><span data-stu-id="12bb7-165">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="12bb7-166">如果呼叫者的位置可用，将在通知中包含该位置。</span><span class="sxs-lookup"><span data-stu-id="12bb7-166">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="12bb7-167">多个 SIP Uri 可以包含为以逗号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="12bb7-167">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="12bb7-168">例如，"sip： security@litwareinc .com"、"sip： kmyer@litwareinc .com"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-168">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="12bb7-169">支持通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="12bb7-169">Distribution lists are supported.</span></span> <span data-ttu-id="12bb7-170">字符串的长度必须介于1到256个字符之间，并且必须以前缀 "sip：" 开头。</span><span class="sxs-lookup"><span data-stu-id="12bb7-170">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="12bb7-171">在通知 URI 字段中单击之前，将显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="12bb7-171">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="12bb7-172">**会议 uri**   将 conferenced 进行任何紧急调用的第三方的电话号码的 SIP uri （如电话号码）。</span><span class="sxs-lookup"><span data-stu-id="12bb7-172">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="12bb7-173">例如，公司安全 office 可以在进行紧急呼叫时接收呼叫，并接听或参与该呼叫（具体取决于**会议模式**字段中提供的值）。</span><span class="sxs-lookup"><span data-stu-id="12bb7-173">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="12bb7-174">该字符串的长度必须介于1到256个字符之间，并且必须以前缀 sip：开头。</span><span class="sxs-lookup"><span data-stu-id="12bb7-174">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="12bb7-175">将显示一个示例，直到您在此字段内单击。</span><span class="sxs-lookup"><span data-stu-id="12bb7-175">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="12bb7-176">**会议模式**   如果在 "**会议 URI** " 字段中指定一个值，则**会议模式**确定第三方是否可以参与呼叫或只能接听。</span><span class="sxs-lookup"><span data-stu-id="12bb7-176">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="12bb7-177">指定下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="12bb7-177">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="12bb7-178">**单向**   第三方只能侦听呼叫方和 PSAP 运营商之间的对话。</span><span class="sxs-lookup"><span data-stu-id="12bb7-178">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="12bb7-179">\*\*\*\* 第三方可以在呼叫者和 PSAP 操作员之间接听并参与呼叫。   </span><span class="sxs-lookup"><span data-stu-id="12bb7-179">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="12bb7-180">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="12bb7-180">Click **Commit**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="12bb7-181">创建用户策略时，最初不会将该策略应用于任何用户或网络网站。</span><span class="sxs-lookup"><span data-stu-id="12bb7-181">When you create a user policy, initially that policy does not apply to any users or network sites.</span></span> <span data-ttu-id="12bb7-182">若要将策略应用于用户，请单击左侧导航栏中的 "<STRONG>用户</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-182">To apply the policy to a user, click <STRONG>Users</STRONG> in the left navigation bar.</span></span> <span data-ttu-id="12bb7-183">查找要对其应用策略的用户。</span><span class="sxs-lookup"><span data-stu-id="12bb7-183">Find the user to which you want to apply the policy.</span></span> <span data-ttu-id="12bb7-184">在“编辑”<STRONG></STRONG>菜单上，单击“显示详细信息”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="12bb7-184">On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>.</span></span> <span data-ttu-id="12bb7-185">在 "<STRONG>编辑 Lync Server 用户</STRONG>" 页面上，从 "<STRONG>位置策略</STRONG>" 下拉列表中选择新的位置策略，然后单击 "<STRONG>提交</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-185">On the <STRONG>Edit Lync Server User</STRONG> page, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span><BR><span data-ttu-id="12bb7-186">若要将策略应用于网络网站，请在左侧导航栏中单击 "<STRONG>网络配置</STRONG>"，然后单击 "<STRONG>网站</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-186">To apply the policy to a network site, click <STRONG>Network Configuration</STRONG> in the left navigation bar and then click <STRONG>Site</STRONG>.</span></span> <span data-ttu-id="12bb7-187">查找要对其应用策略的网络站点。</span><span class="sxs-lookup"><span data-stu-id="12bb7-187">Find the network site to which you want to apply the policy.</span></span> <span data-ttu-id="12bb7-188">在“编辑”<STRONG></STRONG>菜单上，单击“显示详细信息”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="12bb7-188">On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>.</span></span> <span data-ttu-id="12bb7-189">在 "<STRONG>编辑网站</STRONG>" 中，从 "<STRONG>位置策略</STRONG>" 下拉列表中选择新的位置策略，然后单击 "<STRONG>提交</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-189">In <STRONG>Edit Site</STRONG>, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="12bb7-190">在 Lync Server "控制面板" 中修改位置策略</span><span class="sxs-lookup"><span data-stu-id="12bb7-190">To modify a location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="12bb7-191">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="12bb7-191">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12bb7-192">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-192">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12bb7-193">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="12bb7-193">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12bb7-194">在左侧导航栏中，单击 "**网络配置**"，然后单击 "**位置策略**"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-194">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="12bb7-195">在 "**位置策略**" 页面上，选择要修改的位置策略。</span><span class="sxs-lookup"><span data-stu-id="12bb7-195">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="12bb7-196">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="12bb7-196">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="12bb7-197">在 "**编辑位置策略**" 页面上，根据需要修改字段（有关详细信息，请参阅本主题前面的 "创建新的位置策略中的步骤 5"。</span><span class="sxs-lookup"><span data-stu-id="12bb7-197">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="12bb7-198">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="12bb7-198">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12bb7-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12bb7-199">See Also</span></span>


[<span data-ttu-id="12bb7-200">在 Lync Server 2013 中删除位置策略</span><span class="sxs-lookup"><span data-stu-id="12bb7-200">Deleting a location policy in Lync Server 2013</span></span>](lync-server-2013-deleting-a-location-policy.md)  


[<span data-ttu-id="12bb7-201">定义 Lync Server 2013 的位置策略</span><span class="sxs-lookup"><span data-stu-id="12bb7-201">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)  


[<span data-ttu-id="12bb7-202">在 Lync Server 2013 中配置停车通话的电话号码扩展</span><span class="sxs-lookup"><span data-stu-id="12bb7-202">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

