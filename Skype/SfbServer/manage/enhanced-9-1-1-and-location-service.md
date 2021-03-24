---
title: 管理增强型 9-1-1 和位置服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 支持增强型 9-1-1 (E9-1-1) Skype for Business 客户端进行呼叫。 为 E9-1-1 配置 Skype for Business Server 时，从 Skype for Business 拨打的紧急呼叫包括紧急响应位置 (ERL) 位置信息服务数据库中的信息。
ms.openlocfilehash: 4b786d3285b5075a13f43f3b7c7cb75b79182a9f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099058"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a><span data-ttu-id="9a849-104">在 Skype for Busines Server 中管理增强型 9-1-1 和位置服务</span><span class="sxs-lookup"><span data-stu-id="9a849-104">Manage enhanced 9-1-1 and the Location service in Skype for Busines Server</span></span>

<span data-ttu-id="9a849-105">Skype for Business Server 支持增强型 9-1-1 (E9-1-1) Skype for Business 客户端进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="9a849-105">Skype for Business Server supports Enhanced 9-1-1 (E9-1-1) calling from Skype for Business clients.</span></span> <span data-ttu-id="9a849-106">为 E9-1-1 配置 Skype for Business Server 时，从 Skype for Business 拨打的紧急呼叫包括紧急响应位置 (ERL) 位置信息服务数据库中的信息。</span><span class="sxs-lookup"><span data-stu-id="9a849-106">When you configure Skype for Business Server for E9-1-1, emergency calls placed from Skype for Business include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="9a849-107">使用本文中的过程管理位置策略。</span><span class="sxs-lookup"><span data-stu-id="9a849-107">Use the procedures in this article to manage location policy.</span></span>

> [!Note]
> <span data-ttu-id="9a849-108">有关部署高级 企业语音 功能（如 E9-1-1 和位置信息服务）的详细信息，请参阅部署高级企业语音 [功能](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)。</span><span class="sxs-lookup"><span data-stu-id="9a849-108">For details on deploying advanced Enterprise Voice features, such as E9-1-1 and the Location Information service, see [Deploy advanced Enterprise Voice features](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).</span></span>

<span data-ttu-id="9a849-109">在 Skype for Business Server 中，可以使用位置策略应用与增强型 9-1-1 (E9-1-1) 功能以及用户或联系人的位置设置相关的设置。</span><span class="sxs-lookup"><span data-stu-id="9a849-109">In Skype for Business Server, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="9a849-110">位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。</span><span class="sxs-lookup"><span data-stu-id="9a849-110">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="9a849-111">例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。</span><span class="sxs-lookup"><span data-stu-id="9a849-111">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="9a849-112">可以从 Skype for Business Server 控制面板 **中的"网络配置** "组配置位置策略。</span><span class="sxs-lookup"><span data-stu-id="9a849-112">You can configure location policies from the **Network Configuration** group in the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9a849-113">从 Skype for Business Server 控制面板中，可以查看、创建、修改或删除位置策略。</span><span class="sxs-lookup"><span data-stu-id="9a849-113">From the Skype for Business Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="9a849-114">可使用以下过程查看位置策略的信息。</span><span class="sxs-lookup"><span data-stu-id="9a849-114">Use the following procedure to view information about location policies.</span></span> 


## <a name="view-location-policy-information"></a><span data-ttu-id="9a849-115">查看位置策略信息</span><span class="sxs-lookup"><span data-stu-id="9a849-115">View location policy information</span></span> 

1.  <span data-ttu-id="9a849-116">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="9a849-116">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a849-117">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="9a849-117">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9a849-118">在左侧导航栏中，单击"**网络配置"，** 然后单击"位置 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="9a849-118">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="9a849-119">在“位置策略”页上，选择要修改的位置策略。</span><span class="sxs-lookup"><span data-stu-id="9a849-119">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="9a849-120">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="9a849-120">On the **Edit** menu, click **Show details**.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="9a849-121">一次只能查看一个位置策略的信息。</span><span class="sxs-lookup"><span data-stu-id="9a849-121">You can only view information about one location policy at a time.</span></span>

<span data-ttu-id="9a849-p105">默认情况下，存在一个名为“全局”的策略，无法将其删除或进行重命名。但是，您可以修改“全局”策略。该策略将应用于所有用户和联系人，除非您创建站点策略或每用户策略。每用户策略必须应用于特定用户。</span><span class="sxs-lookup"><span data-stu-id="9a849-p105">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>


## <a name="create-or-modify-a-location-policy"></a><span data-ttu-id="9a849-126">创建或修改位置策略</span><span class="sxs-lookup"><span data-stu-id="9a849-126">Create or modify a location policy</span></span> 

<span data-ttu-id="9a849-127">在 Skype for Business Server 中，你可以覆盖从位置信息服务请求位置更新的客户端之间的默认时间量。</span><span class="sxs-lookup"><span data-stu-id="9a849-127">In Skype for Business Server, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="9a849-128">默认值为 4 小时。</span><span class="sxs-lookup"><span data-stu-id="9a849-128">The default value is 4 hours.</span></span> <span data-ttu-id="9a849-129">使用带 LocationRefreshInterval 参数的 **Set-CsLocationPolicy** cmdlet 可覆盖该默认值。</span><span class="sxs-lookup"><span data-stu-id="9a849-129">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a><span data-ttu-id="9a849-130">在 Skype for Business Server 控制面板中创建新的位置策略</span><span class="sxs-lookup"><span data-stu-id="9a849-130">To create a new location policy in the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9a849-131">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="9a849-131">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a849-132">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="9a849-132">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9a849-133">在左侧导航栏中，单击"**网络配置"，** 然后单击"位置 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="9a849-133">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="9a849-134">在“位置策略”页上，单击“新建”，然后选择要创建的策略类型：</span><span class="sxs-lookup"><span data-stu-id="9a849-134">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="9a849-p107">要创建站点策略，请单击“站点策略”。在“选择站点”中，选择您希望应用此策略的站点，然后单击“确定”。在“新建位置策略”页上，“范围”字段包含值“站点”，“名称”字段包含所选站点的名称。您无法修改上述任意字段。站点策略自动应用于指定站点上的所有用户，并且覆盖这些用户的全局策略。</span><span class="sxs-lookup"><span data-stu-id="9a849-p107">To create a site policy, click **Site policy**. In **Select a Site**, choose the site to which you want the policy applied and click **OK**. On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose. You cannot modify either of these fields. A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="9a849-p108">要创建用户策略，请单击“用户策略”。在“新建位置策略”中，“范围”字段包含值“用户”。无法修改该值。在“名称”字段中，键入要赋予此策略的名称。用户策略不会自动应用于任何用户。创建用户策略后，必须手动将此策略授予您希望应用此策略的用户或网络站点。</span><span class="sxs-lookup"><span data-stu-id="9a849-p108">To create a **User policy**, click **User policy**. In the **New Location Policy**, the **Scope** field contains the value **User**. You cannot modify this value. In the **Name** field, type the name you want to give this policy. A user policy does not automatically apply to any users. After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="9a849-146">按如下所示填写剩余字段：</span><span class="sxs-lookup"><span data-stu-id="9a849-146">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="9a849-147">**启用增强型紧急服务**   选中此复选框可启用与此策略关联的 E9-1-1 用户。</span><span class="sxs-lookup"><span data-stu-id="9a849-147">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="9a849-148">启用紧急服务后，Skype for Business Server 客户端将在注册时检索位置信息，并包含进行紧急呼叫时的信息。</span><span class="sxs-lookup"><span data-stu-id="9a849-148">When emergency services are enabled, Skype for Business Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="9a849-149">**位置**   指定以下值之一：</span><span class="sxs-lookup"><span data-stu-id="9a849-149">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="9a849-150">**必需**   当客户端注册到新位置时，将提示用户输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="9a849-150">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="9a849-151">用户可以消除提示，而不输入任何信息。</span><span class="sxs-lookup"><span data-stu-id="9a849-151">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="9a849-152">如果输入了信息，紧急呼叫将首先由紧急服务提供商应答以验证位置，然后再路由到公共安全应答点 (PSAP) 接线员 (即 911 接线员) 。</span><span class="sxs-lookup"><span data-stu-id="9a849-152">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="9a849-153">**不是必需的**   系统不会提示用户输入位置。</span><span class="sxs-lookup"><span data-stu-id="9a849-153">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="9a849-154">当没有位置信息进行呼叫时，紧急服务提供商将应答该呼叫并询问位置。</span><span class="sxs-lookup"><span data-stu-id="9a849-154">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="9a849-155">**免责声明**   此选项与"必需"相同 **，只是** 用户在未输入位置信息的情况下无法消除提示。</span><span class="sxs-lookup"><span data-stu-id="9a849-155">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="9a849-156">用户仍可以完成紧急呼叫，但在未输入信息的情况下无法完成其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="9a849-156">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="9a849-157">此外，还将向用户显示免责声明文本，提醒他们拒绝输入位置信息的后果。</span><span class="sxs-lookup"><span data-stu-id="9a849-157">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="9a849-158">若要设置免责声明文本，必须使用 Skype for Business Server 命令行管理程序运行带 EnhancedEmergencyServiceDisclaimer 参数的 **Set-CsLocationPolicy** cmdlet 或 **New-CsLocationPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a849-158">To set the disclaimer text, you must use the Skype for Business Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="9a849-159">有关详细信息，请参阅[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy)或[New-CsLocationPolicy。](/powershell/module/skype/New-CsLocationPolicy)</span><span class="sxs-lookup"><span data-stu-id="9a849-159">For details, see [Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy).</span></span>
          
    
      - <span data-ttu-id="9a849-160">**仅将位置用于紧急服务** Skype for Business 可以出于各种原因使用位置信息 (例如，通知队友你的当前位置) 。</span><span class="sxs-lookup"><span data-stu-id="9a849-160">**Use location for emergency services only** Skype for Business can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="9a849-161">选中该复选框可确保位置信息只能用于紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="9a849-161">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="9a849-162">**PSTN 用法**   公用电话交换网 (PSTN) 用法，用于确定将使用此配置文件路由来自客户端的紧急呼叫的语音路由。</span><span class="sxs-lookup"><span data-stu-id="9a849-162">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="9a849-163">与此用法关联的路由应指向专用于紧急呼叫的 SIP 中继或紧急位置标识号 (ELIN) 网关，该网关将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="9a849-163">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="9a849-164">**紧急拨号号码**   为获得紧急服务而拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="9a849-164">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="9a849-165">在美国，该值为“911”。</span><span class="sxs-lookup"><span data-stu-id="9a849-165">In the United States this value is 911.</span></span> <span data-ttu-id="9a849-166">该字符串必须由 0 到 9 的数字组成，其长度可以为 1 至 10 位数字。</span><span class="sxs-lookup"><span data-stu-id="9a849-166">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="9a849-167">**紧急拨号掩码**   拨号时要转换为紧急拨号号码值的值的号码。</span><span class="sxs-lookup"><span data-stu-id="9a849-167">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="9a849-168">例如，如果在此字段中输入值 212，并且紧急拨号号码字段的值为 911，则如果用户拨打 212，呼叫将拨打 911。</span><span class="sxs-lookup"><span data-stu-id="9a849-168">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="9a849-169">这样，可以拨打备用紧急号码，并且仍可将呼叫联系紧急服务 (例如，来自具有不同紧急号码的某个国家/地区或地区的用户尝试拨打该国家/地区的号码，而不是当前位于) 中的某个国家/地区的号码。</span><span class="sxs-lookup"><span data-stu-id="9a849-169">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="9a849-170">您可以通过使用分号分隔值来定义多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="9a849-170">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="9a849-171">例如，212;414。</span><span class="sxs-lookup"><span data-stu-id="9a849-171">For example, 212;414.</span></span> <span data-ttu-id="9a849-172">该字符串的最大长度为 100 个字符。</span><span class="sxs-lookup"><span data-stu-id="9a849-172">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="9a849-173">每个字符都必须为 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="9a849-173">Each character must be a digit 0 through 9.</span></span>
      

        > [!IMPORTANT]  
        > <span data-ttu-id="9a849-174">请确保指定的拨号掩码值与呼叫寄存通道范围内的号码不同。</span><span class="sxs-lookup"><span data-stu-id="9a849-174">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="9a849-175">呼叫寄存路由将优先于紧急拨号字符串转换。</span><span class="sxs-lookup"><span data-stu-id="9a849-175">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="9a849-176">要查看现有呼叫寄存通道范围，请单击左侧导航栏中的“语音功能”，然后单击“呼叫寄存”。</span><span class="sxs-lookup"><span data-stu-id="9a849-176">To see the existing call park orbit ranges, click **Voice Features** in the left navigation bar and then click **Call Park**.</span></span> 

    
      - <span data-ttu-id="9a849-177">**通知 URI**   一个或多个 SIP 统一资源标识符 (URI) 进行紧急呼叫时收到通知。</span><span class="sxs-lookup"><span data-stu-id="9a849-177">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="9a849-178">例如，只要发出紧急呼叫，就会通过即时消息通知公司安全办公室。</span><span class="sxs-lookup"><span data-stu-id="9a849-178">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="9a849-179">如果提供了呼叫者的位置，将在通知中包含该位置。</span><span class="sxs-lookup"><span data-stu-id="9a849-179">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="9a849-180">可以采用逗号分隔列表形式包括多个 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="9a849-180">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="9a849-181">例如，"sip:security@litwareinc.com"、"sip:kmyer@litwareinc.com"。</span><span class="sxs-lookup"><span data-stu-id="9a849-181">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="9a849-182">支持通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="9a849-182">Distribution lists are supported.</span></span> <span data-ttu-id="9a849-183">字符串长度必须为 1 到 256 个字符，并且必须以前缀"sip："开头。</span><span class="sxs-lookup"><span data-stu-id="9a849-183">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="9a849-184">在单击"通知 URI"字段中之前，将显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="9a849-184">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="9a849-185">**会议 URI**   将参加任何紧急呼叫会议的第三方的 SIP URI（在这种情况下为电话号码）。</span><span class="sxs-lookup"><span data-stu-id="9a849-185">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="9a849-186">例如，公司安全办公室可以在进行紧急呼叫时接收呼叫，并侦听或参与该呼叫 (具体取决于"会议模式"字段中提供的值) 。 </span><span class="sxs-lookup"><span data-stu-id="9a849-186">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="9a849-187">该字符串的长度必须为 1 到 256 个字符，并且必须以前缀 sip: 开头。</span><span class="sxs-lookup"><span data-stu-id="9a849-187">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="9a849-188">在单击此字段内之前，将显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="9a849-188">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="9a849-189">**会议模式**  如果在"会议 **URI"** 字段中指定值，则会议模式将确定第三方是可参与呼叫还是只能收听呼叫。</span><span class="sxs-lookup"><span data-stu-id="9a849-189">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="9a849-190">指定以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="9a849-190">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="9a849-191">**单向**   第三方只能接听呼叫者与 PSAP 接线员之间的对话。</span><span class="sxs-lookup"><span data-stu-id="9a849-191">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="9a849-192">**双向**   第三方可以接听并参与呼叫者与 PSAP 接线员之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9a849-192">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="9a849-193">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="9a849-193">Click **Commit**.</span></span>


    > [!IMPORTANT]  
    > <span data-ttu-id="9a849-194">创建用户策略时，起初该策略不会应用于任何用户或网络站点。</span><span class="sxs-lookup"><span data-stu-id="9a849-194">When you create a user policy, initially that policy does not apply to any users or network sites.</span></span> <span data-ttu-id="9a849-195">要将此策略应用于某个用户，请单击左侧导航栏中的“用户”。</span><span class="sxs-lookup"><span data-stu-id="9a849-195">To apply the policy to a user, click **Users** in the left navigation bar.</span></span> <span data-ttu-id="9a849-196">查找您希望应用此策略的用户。</span><span class="sxs-lookup"><span data-stu-id="9a849-196">Find the user to which you want to apply the policy.</span></span> <span data-ttu-id="9a849-197">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="9a849-197">On the **Edit** menu, click **Show details**.</span></span> <span data-ttu-id="9a849-198">在"**编辑服务器用户**"页上，从"位置策略"下拉列表中选择新位置策略，然后单击"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="9a849-198">On the **Edit Server User** page, select the new location policy from the **Location policy** drop-down list and then click **Commit**.</span></span><BR><span data-ttu-id="9a849-p122">要将此策略应用于某个网络站点，请单击左侧导航栏中的“网络配置”，然后单击“站点”。查找您希望应用此策略的网络站点。在“编辑”菜单上，单击“显示详细信息”。在“编辑站点”中，从“位置策略”下拉列表中选择新的位置策略，然后单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="9a849-p122">To apply the policy to a network site, click **Network Configuration** in the left navigation bar and then click **Site**. Find the network site to which you want to apply the policy. On the **Edit** menu, click **Show details**. In **Edit Site**, select the new location policy from the **Location policy** drop-down list and then click **Commit**.</span></span>


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a><span data-ttu-id="9a849-203">修改 Skype for Business Server 控制面板中的位置策略</span><span class="sxs-lookup"><span data-stu-id="9a849-203">To modify a location policy in the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9a849-204">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="9a849-204">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a849-205">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="9a849-205">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9a849-206">在左侧导航栏中，单击"**网络配置"，** 然后单击"位置 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="9a849-206">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="9a849-207">在“位置策略”页上，选择要修改的位置策略。</span><span class="sxs-lookup"><span data-stu-id="9a849-207">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="9a849-208">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="9a849-208">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9a849-209">在“编辑位置策略”页上，根据需要修改相应的字段（有关详细信息，请参阅本主题前面介绍的“创建新的位置策略”过程中的步骤 5）。</span><span class="sxs-lookup"><span data-stu-id="9a849-209">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="9a849-210">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="9a849-210">Click **Commit**.</span></span>

        
## <a name="delete-a-location-policy"></a><span data-ttu-id="9a849-211">删除位置策略</span><span class="sxs-lookup"><span data-stu-id="9a849-211">Delete a location policy</span></span>


1.  <span data-ttu-id="9a849-212">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="9a849-212">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a849-213">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="9a849-213">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9a849-214">在左侧导航栏中，单击"**网络配置"，** 然后单击"位置 **策略"。**</span><span class="sxs-lookup"><span data-stu-id="9a849-214">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="9a849-215">在“位置策略”页上，选择要删除的位置策略。</span><span class="sxs-lookup"><span data-stu-id="9a849-215">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="9a849-p123">可一次性删除多个位置策略。要执行此操作，请按住 Ctrl 键，同时选择多个策略。或者，要选中全部策略，请单击“编辑”菜单中的“全选”。</span><span class="sxs-lookup"><span data-stu-id="9a849-p123">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click **Select all** on the **Edit** menu.</span></span>


5.  <span data-ttu-id="9a849-219">在“编辑”菜单上，单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="9a849-219">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="9a849-220">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="9a849-220">Click **OK**.</span></span>

    > [!IMPORTANT]  
    > <span data-ttu-id="9a849-p124">无法删除“全局”位置策略。如果尝试删除“全局”策略，您将收到一条警告消息，而该策略将重置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="9a849-p124">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>


## <a name="see-also"></a><span data-ttu-id="9a849-223">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a849-223">See Also</span></span>

[<span data-ttu-id="9a849-224">创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="9a849-224">Create or modify network sites</span></span>](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[<span data-ttu-id="9a849-225">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="9a849-225">New-CsLocationPolicy</span></span>](/powershell/module/skype/New-CsLocationPolicy)  

[<span data-ttu-id="9a849-226">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="9a849-226">Set-CsLocationPolicy</span></span>](/powershell/module/skype/Set-CsLocationPolicy) 
 
[<span data-ttu-id="9a849-227">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="9a849-227">Remove-CsLocationPolicy</span></span>](/powershell/module/skype/Remove-CsLocationPolicy)  

[<span data-ttu-id="9a849-228">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="9a849-228">Get-CsLocationPolicy</span></span>](/powershell/module/skype/Get-CsLocationPolicy)