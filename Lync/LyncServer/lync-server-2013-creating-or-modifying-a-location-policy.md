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
ms.openlocfilehash: f87bf9aff433b70bc50b3fcff209ecd14ea268e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516779"
---
# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="433de-102">在 Lync Server 2013 中创建或修改位置策略</span><span class="sxs-lookup"><span data-stu-id="433de-102">Creating or modifying a location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="433de-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="433de-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="433de-104">在 Lync Server 2013 中，可以使用位置策略应用与增强的 9-1-1 (E9-1-1) 功能以及用户或联系人的位置设置相关的设置。</span><span class="sxs-lookup"><span data-stu-id="433de-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="433de-105">位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。</span><span class="sxs-lookup"><span data-stu-id="433de-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="433de-106">例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。</span><span class="sxs-lookup"><span data-stu-id="433de-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="433de-107">您可以在 Lync Server 2013 控制面板中的 " **网络配置** " 组中配置位置策略。</span><span class="sxs-lookup"><span data-stu-id="433de-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="433de-108">从 Lync Server 控制面板中，您可以查看、创建、修改或删除位置策略。</span><span class="sxs-lookup"><span data-stu-id="433de-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="433de-109">使用本节中的过程可创建或修改位置策略。</span><span class="sxs-lookup"><span data-stu-id="433de-109">Use the procedures in this section to create or modify a location policy.</span></span> <span data-ttu-id="433de-110">有关删除位置策略的详细信息，请参阅 [在 Lync Server 2013 中删除位置策略](lync-server-2013-deleting-a-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="433de-110">For details on deleting location policies, see [Deleting a location policy in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).</span></span>

<span data-ttu-id="433de-111">在 Lync Server 2013 中，可以在位置信息服务中覆盖客户端请求位置更新之间的默认时间长度。</span><span class="sxs-lookup"><span data-stu-id="433de-111">In Lync Server 2013, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="433de-112">默认值为 4 小时。</span><span class="sxs-lookup"><span data-stu-id="433de-112">The default value is 4 hours.</span></span> <span data-ttu-id="433de-113">使用带 LocationRefreshInterval 参数的 **Set-CsLocationPolicy** cmdlet 可覆盖该默认值。</span><span class="sxs-lookup"><span data-stu-id="433de-113">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="433de-114">在 Lync Server "控制面板" 中创建新位置策略</span><span class="sxs-lookup"><span data-stu-id="433de-114">To create a new location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="433de-115">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="433de-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="433de-116">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="433de-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="433de-117">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="433de-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="433de-118">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“位置策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="433de-118">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="433de-119">在“位置策略”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后选择要创建的策略类型：</span><span class="sxs-lookup"><span data-stu-id="433de-119">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="433de-p105">要创建站点策略，请单击“站点策略”\*\*\*\*。在“选择站点”\*\*\*\* 中，选择您希望应用此策略的站点，然后单击“确定”\*\*\*\*。在“新建位置策略”\*\*\*\* 页上，“范围”\*\*\*\* 字段包含值“站点”\*\*\*\*，“名称”\*\*\*\* 字段包含所选站点的名称。您无法修改上述任意字段。站点策略自动应用于指定站点上的所有用户，并且覆盖这些用户的全局策略。</span><span class="sxs-lookup"><span data-stu-id="433de-p105">To create a site policy, click **Site policy**. In **Select a Site**, choose the site to which you want the policy applied and click **OK**. On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose. You cannot modify either of these fields. A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="433de-p106">要创建用户策略\*\*\*\*，请单击“用户策略”\*\*\*\*。在“新建位置策略”\*\*\*\* 中，“范围”\*\*\*\* 字段包含值“用户”\*\*\*\*。无法修改该值。在“名称”\*\*\*\* 字段中，键入要赋予此策略的名称。用户策略不会自动应用于任何用户。创建用户策略后，必须手动将此策略授予您希望应用此策略的用户或网络站点。</span><span class="sxs-lookup"><span data-stu-id="433de-p106">To create a **User policy**, click **User policy**. In the **New Location Policy**, the **Scope** field contains the value **User**. You cannot modify this value. In the **Name** field, type the name you want to give this policy. A user policy does not automatically apply to any users. After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="433de-131">按如下所示填写剩余字段：</span><span class="sxs-lookup"><span data-stu-id="433de-131">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="433de-132">**启用增强的紧急服务**    选中此复选框可为与此策略关联的用户启用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="433de-132">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="433de-133">启用紧急服务后，Lync Server 客户端将在注册时检索位置信息，并在发出紧急呼叫时包含该信息。</span><span class="sxs-lookup"><span data-stu-id="433de-133">When emergency services are enabled, Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="433de-134">**位置**    指定下列值之一：</span><span class="sxs-lookup"><span data-stu-id="433de-134">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="433de-135">**必需**    当客户端注册到新位置时，系统将提示用户输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="433de-135">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="433de-136">用户可以消除提示，而不输入任何信息。</span><span class="sxs-lookup"><span data-stu-id="433de-136">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="433de-137">如果输入了信息，紧急呼叫将首先由紧急服务提供商应答，以验证在路由到公共安全应答点 (PSAP) operator (即911运算符) 之前的位置。</span><span class="sxs-lookup"><span data-stu-id="433de-137">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="433de-138">**不需要**    将不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="433de-138">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="433de-139">在不使用位置信息的情况下进行呼叫时，紧急服务提供商将应答呼叫并要求提供一个位置。</span><span class="sxs-lookup"><span data-stu-id="433de-139">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="433de-140">**免责声明**    此选项与**必需**的相同，只是用户无法在不输入位置信息的情况下取消提示。</span><span class="sxs-lookup"><span data-stu-id="433de-140">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="433de-141">用户仍可以完成紧急呼叫，但无需输入信息即可完成任何其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="433de-141">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="433de-142">此外，还会向用户显示免责声明文本，以向用户发出警告，指出拒绝输入位置信息的后果。</span><span class="sxs-lookup"><span data-stu-id="433de-142">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="433de-143">若要设置免责声明文本，必须使用 Lync Server 命令行管理 **程序运行 new-cslocationpolicy** cmdlet 或带有 EnhancedEmergencyServiceDisclaimer 参数的 **new-cslocationpolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="433de-143">To set the disclaimer text, you must use Lync Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="433de-144">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 [new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 或 [new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="433de-144">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) in the Lync Server Management Shell documentation.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="433de-145">在 Lync Server 2013 中，可以使用位置策略为不同的区域设置或不同的用户集设置不同的免责声明，这与在 Lync Server 2010 中不同，在这种情况下，您只能为整个组织指定全局免责声明。</span><span class="sxs-lookup"><span data-stu-id="433de-145">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users, unlike in Lync Server 2010 where you could specify only a global disclaimer for the entire organization.</span></span>

            
            </div>
    
      - <span data-ttu-id="433de-146">仅对紧急**服务使用位置**    由于各种原因，Lync 可以使用位置信息 (例如，通知团队成员的当前位置) 。</span><span class="sxs-lookup"><span data-stu-id="433de-146">**Use location for emergency services only**   Lync can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="433de-147">选中该复选框可确保位置信息只能用于紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="433de-147">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="433de-148">**PSTN 用法**    公开交换电话网络 (PSTN) 使用，用于确定将使用此配置文件从客户端路由紧急呼叫的语音路由。</span><span class="sxs-lookup"><span data-stu-id="433de-148">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="433de-149">与此使用关联的路由应指向 "紧急呼叫专用" 的 SIP 中继或 "紧急位置标识号" (ELIN) 网关，该号码将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="433de-149">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="433de-150">**紧急拨号号码**    为达到紧急服务而拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="433de-150">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="433de-151">在美国，该值为“911”。</span><span class="sxs-lookup"><span data-stu-id="433de-151">In the United States this value is 911.</span></span> <span data-ttu-id="433de-152">该字符串必须由 0 到 9 的数字组成，其长度可以为 1 至 10 位数字。</span><span class="sxs-lookup"><span data-stu-id="433de-152">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="433de-153">**紧急拨号掩码**    拨号时要转换为 "紧急拨号号码" 值的号码。</span><span class="sxs-lookup"><span data-stu-id="433de-153">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="433de-154">例如，如果在此字段中输入值212，并且 "紧急拨号号码" 字段的值为911，如果用户212拨打电话，则会对911发出呼叫。</span><span class="sxs-lookup"><span data-stu-id="433de-154">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="433de-155">这样，就可以拨打备用紧急号码，并且仍然可以呼叫紧急服务 (例如，如果来自具有不同紧急号码的某个国家或地区的人尝试拨打该国家或地区的号码，而不是其当前在) 中的国家或地区号码。</span><span class="sxs-lookup"><span data-stu-id="433de-155">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="433de-156">您可以通过使用分号分隔值来定义多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="433de-156">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="433de-157">例如，212; 414。</span><span class="sxs-lookup"><span data-stu-id="433de-157">For example, 212;414.</span></span> <span data-ttu-id="433de-158">该字符串的最大长度为 100 个字符。</span><span class="sxs-lookup"><span data-stu-id="433de-158">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="433de-159">每个字符都必须为 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="433de-159">Each character must be a digit 0 through 9.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="433de-160">请确保指定的拨号掩码值与呼叫寄存通道范围内的号码不同。</span><span class="sxs-lookup"><span data-stu-id="433de-160">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="433de-161">呼叫寄存路由将优先于紧急拨号字符串转换。</span><span class="sxs-lookup"><span data-stu-id="433de-161">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="433de-162">要查看现有呼叫寄存通道范围，请单击左侧导航栏中的“语音功能”<STRONG></STRONG>，然后单击“呼叫寄存”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="433de-162">To see the existing call park orbit ranges, click <STRONG>Voice Features</STRONG> in the left navigation bar and then click <STRONG>Call Park</STRONG>.</span></span> <span data-ttu-id="433de-163">有关详细信息，请参阅 <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">在 Lync Server 2013 中配置停车呼叫的电话号码扩展</A>。</span><span class="sxs-lookup"><span data-stu-id="433de-163">For details, see <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure phone number extensions for parking calls in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="433de-164">**通知 URI**    发出紧急呼叫时，) 要通知的一个或多个 SIP 统一资源标识符 (Uri。</span><span class="sxs-lookup"><span data-stu-id="433de-164">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="433de-165">例如，只要发出紧急呼叫，就会通过即时消息通知公司安全办公室。</span><span class="sxs-lookup"><span data-stu-id="433de-165">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="433de-166">如果提供了呼叫者的位置，将在通知中包含该位置。</span><span class="sxs-lookup"><span data-stu-id="433de-166">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="433de-167">可以采用逗号分隔列表形式包括多个 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="433de-167">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="433de-168">例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。</span><span class="sxs-lookup"><span data-stu-id="433de-168">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="433de-169">支持通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="433de-169">Distribution lists are supported.</span></span> <span data-ttu-id="433de-170">该字符串的长度必须介于1到256个字符之间，且必须以前缀 "sip：" 开头。</span><span class="sxs-lookup"><span data-stu-id="433de-170">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="433de-171">在 "通知 URI" 字段中单击之前，将显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="433de-171">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="433de-172">**会议 URI**    SIP URI，在此示例中，将 conferenced 的第三方的电话号码，以进行任何紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="433de-172">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="433de-173">例如，在发出紧急呼叫时，公司安全办公室可以接收呼叫，并根据 **会议模式** 字段) 中提供的值 (接听或参与呼叫。</span><span class="sxs-lookup"><span data-stu-id="433de-173">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="433de-174">该字符串的长度必须为 1 到 256 个字符，并且必须以前缀 sip: 开头。</span><span class="sxs-lookup"><span data-stu-id="433de-174">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="433de-175">在此字段中单击时，将显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="433de-175">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="433de-176">**会议模式**    如果在 "**会议 URI** " 字段中指定一个值，则**会议模式**将确定第三方是否可以参与呼叫或只能接听。</span><span class="sxs-lookup"><span data-stu-id="433de-176">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="433de-177">指定以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="433de-177">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="433de-178">**单向**    第三方只能侦听呼叫方和 PSAP 运算符之间的对话。</span><span class="sxs-lookup"><span data-stu-id="433de-178">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="433de-179">**双向**    第三方可以侦听和参与呼叫方和 PSAP 操作员之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="433de-179">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="433de-180">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="433de-180">Click **Commit**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="433de-p119">创建用户策略时，起初该策略不会应用于任何用户或网络站点。要将此策略应用于某个用户，请单击左侧导航栏中的“用户”<STRONG></STRONG>。查找您希望应用此策略的用户。在“编辑”<STRONG></STRONG>菜单上，单击“显示详细信息”<STRONG></STRONG>。在“编辑 Lync Server 用户”<STRONG></STRONG>页上，从“位置策略”<STRONG></STRONG>下拉列表中选择新的位置策略，然后单击“提交”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="433de-p119">When you create a user policy, initially that policy does not apply to any users or network sites. To apply the policy to a user, click <STRONG>Users</STRONG> in the left navigation bar. Find the user to which you want to apply the policy. On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>. On the <STRONG>Edit Lync Server User</STRONG> page, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span><BR><span data-ttu-id="433de-p120">要将此策略应用于某个网络站点，请单击左侧导航栏中的“网络配置”<STRONG></STRONG>，然后单击“站点”<STRONG></STRONG>。查找您希望应用此策略的网络站点。在“编辑”<STRONG></STRONG>菜单上，单击“显示详细信息”<STRONG></STRONG>。在“编辑站点”<STRONG></STRONG>中，从“位置策略”<STRONG></STRONG>下拉列表中选择新的位置策略，然后单击“提交”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="433de-p120">To apply the policy to a network site, click <STRONG>Network Configuration</STRONG> in the left navigation bar and then click <STRONG>Site</STRONG>. Find the network site to which you want to apply the policy. On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>. In <STRONG>Edit Site</STRONG>, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="433de-190">在 Lync Server 控制面板中修改位置策略</span><span class="sxs-lookup"><span data-stu-id="433de-190">To modify a location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="433de-191">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="433de-191">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="433de-192">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="433de-192">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="433de-193">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="433de-193">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="433de-194">在左侧导航栏中，单击“网络配置”\*\*\*\*，然后单击“位置策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="433de-194">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="433de-195">在“位置策略”\*\*\*\* 页上，选择要修改的位置策略。</span><span class="sxs-lookup"><span data-stu-id="433de-195">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="433de-196">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="433de-196">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="433de-197">在“编辑位置策略”\*\*\*\* 页上，根据需要修改相应的字段（有关详细信息，请参阅本主题前面介绍的“创建新的位置策略”过程中的步骤 5）。</span><span class="sxs-lookup"><span data-stu-id="433de-197">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="433de-198">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="433de-198">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="433de-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="433de-199">See Also</span></span>


[<span data-ttu-id="433de-200">在 Lync Server 2013 中删除位置策略</span><span class="sxs-lookup"><span data-stu-id="433de-200">Deleting a location policy in Lync Server 2013</span></span>](lync-server-2013-deleting-a-location-policy.md)  


[<span data-ttu-id="433de-201">定义 Lync Server 2013 的位置策略</span><span class="sxs-lookup"><span data-stu-id="433de-201">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)  


[<span data-ttu-id="433de-202">在 Lync Server 2013 中配置停车呼叫的电话号码分机</span><span class="sxs-lookup"><span data-stu-id="433de-202">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

