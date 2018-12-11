---
title: 启用或禁用远程用户访问
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果您启用远程用户的远程用户访问，支持远程用户通过 Internet 连接，且不具有才能与内部用户使用 Skype 业务服务器的协作使用 VPN 进行连接。
ms.openlocfilehash: 34733c4d1912461090ef868e24ae24dc1c870a94
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222875"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="3a05e-103">启用或禁用远程用户访问在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="3a05e-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="3a05e-104">远程用户是贵组织拥有持久的 Active Directory 标识组织内的用户。</span><span class="sxs-lookup"><span data-stu-id="3a05e-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="3a05e-105">远程用户通常登录到 Skype 业务服务器从外部网络在不连接到组织的网络时通过虚拟专用网络 (VPN)。</span><span class="sxs-lookup"><span data-stu-id="3a05e-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="3a05e-106">远程用户包含员工在家工作或在旅途中以及其他远程工作者，例如受信任供应商，人员已被授予企业凭据。</span><span class="sxs-lookup"><span data-stu-id="3a05e-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="3a05e-107">如果您启用远程用户的远程用户访问，支持远程用户通过 Internet 连接，且不具有才能与内部用户使用 Skype 业务服务器的协作使用 VPN 进行连接。</span><span class="sxs-lookup"><span data-stu-id="3a05e-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="3a05e-108">若要支持远程用户访问，必须启用远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="3a05e-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="3a05e-109">当您启用远程用户访问时，您可以为整个组织启用它。</span><span class="sxs-lookup"><span data-stu-id="3a05e-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="3a05e-110">如果您以后想要临时或永久阻止远程用户访问，您可以为组织禁用它。</span><span class="sxs-lookup"><span data-stu-id="3a05e-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="3a05e-111">使用本节中的过程以启用或禁用组织的远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="3a05e-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="3a05e-112">仅启用远程用户访问指定运行访问边缘服务的服务器支持与远程用户的通信，但远程用户无法参与即时消息 (IM) 或您的组织中的会议配置在之前若要管理的远程用户访问使用的至少一个策略。</span><span class="sxs-lookup"><span data-stu-id="3a05e-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="3a05e-113">Skype 的于一个策略级别的企业服务器策略设置可以覆盖其他策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="3a05e-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3a05e-114">业务服务器策略优先顺序的 Skype 是： 用户策略 （大多数影响） 将覆盖站点策略，然后网站策略将覆盖全局策略 （最低影响）。</span><span class="sxs-lookup"><span data-stu-id="3a05e-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3a05e-115">这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。</span><span class="sxs-lookup"><span data-stu-id="3a05e-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="3a05e-116">有关配置为使用远程用户访问的策略的详细信息，请参阅[配置策略以控制 Skype 业务服务器中的远程用户访问](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3a05e-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="3a05e-117">启用或禁用组织的远程用户访问</span><span class="sxs-lookup"><span data-stu-id="3a05e-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="3a05e-118">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3a05e-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a05e-119">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="3a05e-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3a05e-120">在左侧导航栏中，单击“**联盟和外部访问**”，然后单击“**访问边缘配置**”。</span><span class="sxs-lookup"><span data-stu-id="3a05e-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="3a05e-121">在**访问边缘配置**页上，单击**全局**，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="3a05e-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3a05e-122">在**编辑访问边缘配置**中，执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="3a05e-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="3a05e-123">要为组织的远程用户访问，请选中**启用远程用户访问**复选框。</span><span class="sxs-lookup"><span data-stu-id="3a05e-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="3a05e-124">若要禁用组织的远程用户访问，请清除**启用远程用户访问**复选框。</span><span class="sxs-lookup"><span data-stu-id="3a05e-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="3a05e-125">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="3a05e-125">Click **Commit**.</span></span>

<span data-ttu-id="3a05e-126">若要启用远程用户登录到运行 Skype 业务服务器的服务器，还必须配置至少一个外部访问策略以支持远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="3a05e-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="3a05e-127">有关详细信息，请参阅[配置策略以控制 Skype 业务服务器中的远程用户访问](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3a05e-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3a05e-128">启用或禁用远程用户访问使用 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3a05e-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3a05e-129">可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="3a05e-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3a05e-130">从业务 Server 2013 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a05e-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="3a05e-131">若要启用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="3a05e-131">To enable remote user access</span></span>

  - <span data-ttu-id="3a05e-132">要启用远程用户访问，请将**AllowOutsideUsers**属性的值设置为 True ($True) 中：</span><span class="sxs-lookup"><span data-stu-id="3a05e-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="3a05e-133">若要禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="3a05e-133">To disable remote user access</span></span>

  - <span data-ttu-id="3a05e-134">要禁用远程用户访问，请将**AllowOutsideUsers**属性的值设置为 False ($False) 中：</span><span class="sxs-lookup"><span data-stu-id="3a05e-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


