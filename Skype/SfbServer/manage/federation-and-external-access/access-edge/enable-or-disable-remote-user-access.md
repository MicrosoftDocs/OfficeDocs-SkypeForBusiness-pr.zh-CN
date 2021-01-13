---
title: 启用或禁用远程用户访问
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果为远程用户启用远程用户访问，则受支持的远程用户通过 Internet 进行连接，并且不需要使用 VPN 进行连接，以便使用 Skype for Business Server 与内部用户进行协作。
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817392"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="d95c5-103">在 Skype for Business Server 中启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="d95c5-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="d95c5-104">远程用户是组织内拥有持久 Active Directory 标识的用户。</span><span class="sxs-lookup"><span data-stu-id="d95c5-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="d95c5-105">远程用户通常在未连接到组织的网络时，使用虚拟专用网络 (VPN) 从网络外部登录 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="d95c5-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="d95c5-106">远程用户包括在家或在路上工作的员工以及其他远程工作者，如已被授予企业凭据的受信任供应商。</span><span class="sxs-lookup"><span data-stu-id="d95c5-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="d95c5-107">如果为远程用户启用远程用户访问，则受支持的远程用户通过 Internet 进行连接，并且不需要使用 VPN 进行连接，以便使用 Skype for Business Server 与内部用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="d95c5-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="d95c5-p102">要支持远程用户访问，必须启用远程用户访问。启用远程用户访问即为整个组织启用。如果稍后要暂时或永久阻止远程用户访问，可以为组织将其禁用。可以使用本节中的步骤为组织启用或禁用远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="d95c5-p102">To support remote user access, you must enable remote user access. When you enable remote user access, you enable it for your entire organization. If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization. Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="d95c5-112">启用远程用户访问仅指定运行访问边缘服务的服务器支持与远程用户的通信，但远程用户无法在组织中参与即时消息 (IM) 或会议，除非还配置了至少一个策略来管理远程用户访问的使用。</span><span class="sxs-lookup"><span data-stu-id="d95c5-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="d95c5-113">在一个策略级别应用的 Skype for Business Server 策略设置可以覆盖在另一个策略级别应用的设置。</span><span class="sxs-lookup"><span data-stu-id="d95c5-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d95c5-114">Skype for Business 服务器策略优先级是：用户策略（最大影响力）覆盖站点策略，然后站点策略覆盖全局策略（最小影响）。</span><span class="sxs-lookup"><span data-stu-id="d95c5-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d95c5-115">这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。</span><span class="sxs-lookup"><span data-stu-id="d95c5-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="d95c5-116">有关配置远程用户访问策略的详细信息，请参阅配置策略以控制 Skype [for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md)中的远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="d95c5-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="d95c5-117">为组织启用或禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="d95c5-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="d95c5-118">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="d95c5-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d95c5-119">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d95c5-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d95c5-120">在左侧导航栏中，单击“联盟和外部访问”，然后单击“访问边缘配置”。</span><span class="sxs-lookup"><span data-stu-id="d95c5-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="d95c5-121">在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="d95c5-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d95c5-122">在“编辑访问边缘配置”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d95c5-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="d95c5-123">要为组织启用远程用户访问，请选中“启用远程用户访问”复选框。</span><span class="sxs-lookup"><span data-stu-id="d95c5-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="d95c5-124">要为组织禁用远程用户访问，请清除“启用远程用户访问”复选框。</span><span class="sxs-lookup"><span data-stu-id="d95c5-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="d95c5-125">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="d95c5-125">Click **Commit**.</span></span>

<span data-ttu-id="d95c5-126">若要允许远程用户登录到运行 Skype for Business Server 的服务器，还必须配置至少一个外部访问策略以支持远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="d95c5-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="d95c5-127">有关详细信息，请参阅 [配置策略以控制 Skype for Business Server 中的远程用户访问](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="d95c5-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d95c5-128">使用 cmdlet 启用或禁用Windows PowerShell用户访问</span><span class="sxs-lookup"><span data-stu-id="d95c5-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d95c5-129">可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 管理远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="d95c5-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="d95c5-130">此 cmdlet 可以从 Skype for Business Server 2013 命令行管理程序或远程会话运行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d95c5-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="d95c5-131">启用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="d95c5-131">To enable remote user access</span></span>

  - <span data-ttu-id="d95c5-132">要启用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="d95c5-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="d95c5-133">禁用远程用户访问</span><span class="sxs-lookup"><span data-stu-id="d95c5-133">To disable remote user access</span></span>

  - <span data-ttu-id="d95c5-134">要禁用远程用户访问，请将 **AllowOutsideUsers** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="d95c5-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


