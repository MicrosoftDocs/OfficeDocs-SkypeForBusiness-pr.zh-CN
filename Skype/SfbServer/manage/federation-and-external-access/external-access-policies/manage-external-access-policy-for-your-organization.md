---
title: 管理组织的外部访问策略
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 后部署一个或多个边缘服务器，必须启用将为您的组织支持的外部访问的类型。
ms.openlocfilehash: bdc1a87476849a6e8383d5561af6e1b3af477869
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199882"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="2bf2b-103">管理组织的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="2bf2b-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="2bf2b-104">后部署一个或多个边缘服务器，必须启用将为您的组织支持的外部访问的类型。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="2bf2b-105">默认情况下，没有配置为支持外部用户访问，即使您已为您的组织已启用外部用户访问支持包括远程用户访问、 联盟的用户访问的策略。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="2bf2b-106">若要控制外部用户访问的使用，必须配置一个或多个策略，指定类型的外部用户访问支持的每个策略。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="2bf2b-107">为创建和配置提供了以下策略作用域。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="2bf2b-108">默认情况下，全局策略创建后，但不能删除。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="2bf2b-109">**全局策略**   部署边缘服务器时创建的全局策略。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="2bf2b-110">默认情况下，没有外部用户访问选项被启用在全局策略。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="2bf2b-111">若要支持外部用户访问，在全局级别，您可以配置全局策略以支持一个或多个类型的外部用户访问选项。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="2bf2b-112">全局策略应用于组织中的所有用户，但网站策略和用户策略将覆盖全局策略。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="2bf2b-113">如果您删除全局策略，则不要删除它。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="2bf2b-114">相反，您其重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="2bf2b-115">**站点策略**   可以创建并配置一个或多个站点策略，以限制到特定站点的外部用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="2bf2b-116">站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="2bf2b-117">例如，如果您启用远程用户访问，在全局策略，您可能指定禁用特定站点的远程用户访问的站点策略。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="2bf2b-118">默认情况下的站点策略应用于所有用户的网站，但可以将用户策略分配给用户将会覆盖站点策略设置。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="2bf2b-119">**用户策略**   可以创建并配置一个或多个用户策略，以限制为特定用户的远程用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="2bf2b-120">在用户策略重写全局和站点策略，但仅限于为其分配的用户策略的特定用户的配置。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="2bf2b-121">例如，如果您启用远程用户访问中的全局策略和站点策略，您可能指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="2bf2b-122">如果您创建的用户策略，您必须将它应用于一个或多个用户才能生效。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="2bf2b-123">在一个策略级别应用的策略设置可能会覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="2bf2b-124">业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="2bf2b-125">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="2bf2b-126">这些选项包括以下类型的外部访问：</span><span class="sxs-lookup"><span data-stu-id="2bf2b-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="2bf2b-127">**启用与联盟用户的通信**   启用此项如果您想要支持联盟的伙伴域用户访问。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="2bf2b-128">此设置可配置的用户进行通信，与其他 SIP 联盟域，以及托管提供程序，如 Microsoft Office 365 的功能。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> 


  - <span data-ttu-id="2bf2b-129">**启用与远程用户的通信**   启用此选项，如果您希望您的组织防火墙，如远程办公和用户在旅行，以便能够通过 Internet 业务服务器连接到 Skype 之外的用户。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="2bf2b-130">**启用与公共用户的通信**   启用此选项，如果您希望内部用户可以与公共 IM 提供程序联系人进行通信。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="2bf2b-131">除了启用外部用户访问支持，您还必须配置策略以控制您的组织中的外部用户访问使用任何类型的外部用户访问之前对用户可用。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="2bf2b-132">有关创建、 配置和外部用户访问的应用策略的详细信息，请参阅[启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="2bf2b-133">**使用 Windows PowerShell cmdlet 查看外部访问策略**</span><span class="sxs-lookup"><span data-stu-id="2bf2b-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="2bf2b-134">您可以通过使用 Skype 业务 Server 命令行管理程序和**Get-csexternalaccesspolicy** cmdlet 查看外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="2bf2b-135">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2bf2b-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="2bf2b-136">若要查看有关所有外部访问策略的信息，请在 Lync Server Management Shell 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="2bf2b-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="2bf2b-137">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="2bf2b-137">This command returns information similar to the following:</span></span>
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
