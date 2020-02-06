---
title: 启用或禁用远程用户访问
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: 如果为远程用户启用远程用户访问，受支持的远程用户通过 Internet 进行连接，并且不必使用 VPN 进行连接，以便与使用 Skype for Business 服务器的内部用户进行协作。
ms.openlocfilehash: b562dbe7a849ca4266a45303008ff9081903658d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818373"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="c58b5-103">在 Skype for Business 服务器中启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="c58b5-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="c58b5-104">远程用户是组织内具有永久 Active Directory 标识的用户。</span><span class="sxs-lookup"><span data-stu-id="c58b5-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="c58b5-105">当远程用户未连接到您的组织的网络时，通过使用虚拟专用网络（VPN），从网络外部登录 Skype for business 服务器。</span><span class="sxs-lookup"><span data-stu-id="c58b5-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="c58b5-106">远程用户包括在家中或在路上和其他远程工作人员（如受信任的供应商，他们已授予企业凭据）工作的员工。</span><span class="sxs-lookup"><span data-stu-id="c58b5-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="c58b5-107">如果为远程用户启用远程用户访问，受支持的远程用户通过 Internet 进行连接，并且不必使用 VPN 进行连接，以便与使用 Skype for Business 服务器的内部用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="c58b5-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="c58b5-108">若要支持远程用户访问，必须启用远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="c58b5-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="c58b5-109">启用远程用户访问时，将为整个组织启用它。</span><span class="sxs-lookup"><span data-stu-id="c58b5-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="c58b5-110">如果稍后想要临时或永久阻止远程用户访问，则可以为你的组织禁用它。</span><span class="sxs-lookup"><span data-stu-id="c58b5-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="c58b5-111">使用此部分中的过程可为你的组织启用或禁用远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="c58b5-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="c58b5-112">启用远程用户访问仅指定运行 Access Edge 服务的服务器支持与远程用户的通信，但远程用户不能在您的组织中参与即时消息（IM）或会议，除非您还可以在配置管理远程用户访问使用的至少一个策略。</span><span class="sxs-lookup"><span data-stu-id="c58b5-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="c58b5-113">在一个策略级别应用的 Skype for business 服务器策略设置可以覆盖在其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="c58b5-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c58b5-114">Skype for Business 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。</span><span class="sxs-lookup"><span data-stu-id="c58b5-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c58b5-115">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="c58b5-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="c58b5-116">有关配置使用远程用户访问策略的详细信息，请参阅[在 Skype For Business 服务器中配置用于控制远程用户访问的策略](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="c58b5-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="c58b5-117">为你的组织启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="c58b5-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="c58b5-118">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c58b5-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c58b5-119">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="c58b5-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c58b5-120">在左侧导航栏中，单击“**联盟和外部访问**”，然后单击“**访问边缘配置**”。</span><span class="sxs-lookup"><span data-stu-id="c58b5-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="c58b5-121">在 "**访问边缘配置**" 页面上，单击 "**全局**"，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="c58b5-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c58b5-122">在 "**编辑访问边缘配置**" 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c58b5-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="c58b5-123">若要为你的组织启用远程用户访问权限，请选中 "**启用远程用户访问**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c58b5-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="c58b5-124">若要为你的组织禁用远程用户访问权限，请清除 "**启用远程用户访问**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c58b5-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="c58b5-125">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="c58b5-125">Click **Commit**.</span></span>

<span data-ttu-id="c58b5-126">若要使远程用户能够登录到运行 Skype for Business Server 的服务器，还必须至少配置一个外部访问策略以支持远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="c58b5-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="c58b5-127">有关详细信息，请参阅[在 Skype For Business 服务器中配置用于控制远程用户访问的策略](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="c58b5-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c58b5-128">使用 Windows PowerShell cmdlet 启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="c58b5-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c58b5-129">可使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 管理远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="c58b5-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c58b5-130">此 cmdlet 既可以从 Skype for Business Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="c58b5-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="c58b5-131">启用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="c58b5-131">To enable remote user access</span></span>

  - <span data-ttu-id="c58b5-132">若要启用远程用户访问，请将**AllowOutsideUsers**属性的值设置为 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="c58b5-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="c58b5-133">禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="c58b5-133">To disable remote user access</span></span>

  - <span data-ttu-id="c58b5-134">若要禁用远程用户访问，请将**AllowOutsideUsers**属性的值设置为 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="c58b5-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


