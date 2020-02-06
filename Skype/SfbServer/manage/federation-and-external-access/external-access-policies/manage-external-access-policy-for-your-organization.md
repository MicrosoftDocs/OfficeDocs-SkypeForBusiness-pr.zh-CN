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
description: 部署一个或多个边缘服务器后，必须启用组织支持的外部访问类型。
ms.openlocfilehash: e4405585da71dc48f5fa1790f83938a814270d84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818273"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="9e88f-103">管理组织的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="9e88f-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="9e88f-104">部署一个或多个边缘服务器后，必须启用组织支持的外部访问类型。</span><span class="sxs-lookup"><span data-stu-id="9e88f-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="9e88f-105">默认情况下，没有配置任何可支持外部用户访问的策略，包括远程用户访问权限、联盟用户访问权限，即使你已启用组织的外部用户访问支持。</span><span class="sxs-lookup"><span data-stu-id="9e88f-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="9e88f-106">若要控制外部用户访问的使用，必须配置一个或多个策略，指定每个策略支持的外部用户访问类型。</span><span class="sxs-lookup"><span data-stu-id="9e88f-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="9e88f-107">以下策略作用域可用于创建和配置。</span><span class="sxs-lookup"><span data-stu-id="9e88f-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="9e88f-108">默认情况下，创建全局策略，但不能删除。</span><span class="sxs-lookup"><span data-stu-id="9e88f-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="9e88f-109">**全局策略**   当你部署 Edge 服务器时，将创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="9e88f-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="9e88f-110">默认情况下，全局策略中未启用任何外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="9e88f-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="9e88f-111">若要在全局级别支持外部用户访问，请将全局策略配置为支持一种或多种类型的外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="9e88f-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="9e88f-112">全局策略适用于组织中的所有用户，但网站策略和用户策略替代全局策略。</span><span class="sxs-lookup"><span data-stu-id="9e88f-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="9e88f-113">如果您删除全局策略，则不会将其删除。</span><span class="sxs-lookup"><span data-stu-id="9e88f-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="9e88f-114">而是将其重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="9e88f-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="9e88f-115">**网站策略**   您可以创建和配置一个或多个网站策略，以限制对特定网站的外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="9e88f-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="9e88f-116">站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。</span><span class="sxs-lookup"><span data-stu-id="9e88f-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="9e88f-117">例如，如果在全局策略中启用 "远程用户访问"，则可以指定一个网站策略，该策略可禁用特定网站的远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="9e88f-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="9e88f-118">默认情况下，网站策略应用于该网站的所有用户，但你可以将用户策略分配给用户以替代网站策略设置。</span><span class="sxs-lookup"><span data-stu-id="9e88f-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="9e88f-119">**用户策略**   您可以创建和配置一个或多个用户策略，以限制对特定用户的远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="9e88f-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="9e88f-120">用户策略中的配置替代全局和网站策略，但仅适用于为其分配用户策略的特定用户。</span><span class="sxs-lookup"><span data-stu-id="9e88f-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="9e88f-121">例如，如果在全局策略和网站策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="9e88f-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="9e88f-122">如果创建用户策略，则必须将其应用于一个或多个用户，然后它才会生效。</span><span class="sxs-lookup"><span data-stu-id="9e88f-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="9e88f-123">在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="9e88f-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="9e88f-124">Skype for Business 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。</span><span class="sxs-lookup"><span data-stu-id="9e88f-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="9e88f-125">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="9e88f-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="9e88f-126">这些选项包括以下类型的外部访问：</span><span class="sxs-lookup"><span data-stu-id="9e88f-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="9e88f-127">\*\*\*\*   如果你希望支持用户对联盟伙伴域的访问权限，请启用与联盟用户的通信。</span><span class="sxs-lookup"><span data-stu-id="9e88f-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="9e88f-128">此设置将用户配置为与其他 SIP 联盟域以及托管提供商（如 Microsoft Office 365）进行通信的能力。</span><span class="sxs-lookup"><span data-stu-id="9e88f-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="9e88f-129">**启用与远程用户**   的通信如果你希望你的组织中的用户（如出差的远程办公和用户）能够通过 Internet 连接到 Skype for business 服务器，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="9e88f-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="9e88f-130">\*\*\*\*   如果希望内部用户能够与公共 IM 提供商联系人通信，请启用与公共用户的通信。</span><span class="sxs-lookup"><span data-stu-id="9e88f-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="9e88f-131">除了启用外部用户访问支持外，你还必须配置策略，以控制在你的组织中使用外部用户访问，然后再向用户提供任何类型的外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="9e88f-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="9e88f-132">有关创建、配置和应用外部用户访问策略的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9e88f-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="9e88f-133">**使用 Windows PowerShell cmdlet 查看外部访问策略**</span><span class="sxs-lookup"><span data-stu-id="9e88f-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="9e88f-134">你可以使用 Skype for Business Server Management Shell 和**CsExternalAccessPolicy** cmdlet 查看外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="9e88f-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="9e88f-135">你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9e88f-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="9e88f-136">若要查看有关所有外部访问策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="9e88f-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="9e88f-137">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="9e88f-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
