---
title: 管理组织的外部访问策略
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署一台或多台 Edge 服务器后，必须启用组织支持的外部访问类型。
ms.openlocfilehash: e4405585da71dc48f5fa1790f83938a814270d84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818273"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="66013-103">管理组织的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="66013-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="66013-104">部署一台或多台 Edge 服务器后，必须启用组织支持的外部访问类型。</span><span class="sxs-lookup"><span data-stu-id="66013-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="66013-p101">默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，并指定每个策略支持的外部用户访问类型。可创建和配置以下策略范围。默认情况下，将创建全局策略且无法被删除。</span><span class="sxs-lookup"><span data-stu-id="66013-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="66013-109">**全局策略**   在部署 Edge 服务器时创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="66013-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="66013-110">默认情况下，全局策略中未启用任何外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="66013-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="66013-111">要支持全局级别的外部用户访问，请将全局策略配置为支持一种或多种外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="66013-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="66013-112">全局策略适用于组织中的所有用户，但站点策略和用户策略将覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="66013-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="66013-113">如果删除全局策略，则不要将其移除。</span><span class="sxs-lookup"><span data-stu-id="66013-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="66013-114">相反，将其重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="66013-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="66013-115">**站点策略**   可创建和配置一个或多个站点策略，以将外部用户访问限制到指定站点。</span><span class="sxs-lookup"><span data-stu-id="66013-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="66013-116">站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。</span><span class="sxs-lookup"><span data-stu-id="66013-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="66013-117">例如，如果在全局策略中启用远程用户访问，则可以指定禁用特定站点的远程用户访问的站点策略。</span><span class="sxs-lookup"><span data-stu-id="66013-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="66013-118">默认情况下，站点策略应用于该站点的所有用户，但可以将用户策略分配给用户以覆盖站点策略设置。</span><span class="sxs-lookup"><span data-stu-id="66013-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="66013-119">**用户策略**   可以创建和配置一个或多个用户策略，以将远程用户访问支持限制到指定用户。</span><span class="sxs-lookup"><span data-stu-id="66013-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="66013-120">用户策略中的配置将覆盖全局和站点策略，但仅适用于为其分配策略的特定用户。</span><span class="sxs-lookup"><span data-stu-id="66013-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="66013-121">例如，如果在全局策略和站点策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="66013-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="66013-122">如果创建用户策略，必须将其应用于一个或多个用户，然后才能生效。</span><span class="sxs-lookup"><span data-stu-id="66013-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="66013-123">在一个策略级别应用的策略设置可覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="66013-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="66013-124">Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。</span><span class="sxs-lookup"><span data-stu-id="66013-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="66013-125">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="66013-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="66013-126">这些选项包括以下类型的外部访问：</span><span class="sxs-lookup"><span data-stu-id="66013-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="66013-127">**启用与联盟用户的通信**   如果要支持用户对联合伙伴域的访问，则启用此选项。</span><span class="sxs-lookup"><span data-stu-id="66013-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="66013-128">此设置配置用户与其他 SIP 联盟域以及托管提供商（如 Microsoft Office 365）进行通信的功能。</span><span class="sxs-lookup"><span data-stu-id="66013-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="66013-129">**启用与远程用户的通信**   如果您希望组织中位于防火墙之外的用户（如远程工作者和正在旅行的用户）能够通过 Internet 连接到 Skype for Business，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="66013-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="66013-130"> **启用与公共用户的通信**   如果您希望内部用户能够与公共 IM 提供程序联系人进行通信，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="66013-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="66013-131">除了启用外部用户访问支持外，还必须在用户可以使用任何类型的外部用户访问之前，配置策略以控制组织中外部用户访问的使用。</span><span class="sxs-lookup"><span data-stu-id="66013-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="66013-132">有关为外部用户访问创建、配置和应用策略的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="66013-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="66013-133">**使用 Windows PowerShell cmdlet 查看外部访问策略**</span><span class="sxs-lookup"><span data-stu-id="66013-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="66013-134">可以使用 Skype for Business Server Management Shell 和 **CsExternalAccessPolicy** cmdlet 查看外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="66013-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="66013-135">还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66013-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="66013-136">若要查看有关所有外部访问策略的信息，请在 Lync Server Management Shell 中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="66013-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="66013-137">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="66013-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
