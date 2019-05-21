---
title: 启用或禁用匿名用户访问
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280269"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="0322b-102">在 Skype for Business 服务器中启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="0322b-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="0322b-103">匿名用户是在组织的 Active Directory 域服务或受支持的联盟域中没有用户帐户的用户, 但可以邀请他们在本地会议中进行远程参与。</span><span class="sxs-lookup"><span data-stu-id="0322b-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="0322b-104">通过允许匿名参与会议, 你可以启用匿名用户 (即仅通过会议或会议密钥验证身份的用户) 来加入会议。</span><span class="sxs-lookup"><span data-stu-id="0322b-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="0322b-105">允许匿名参与需要为你的组织启用它。</span><span class="sxs-lookup"><span data-stu-id="0322b-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="0322b-106">如果稍后想要临时或永久阻止匿名用户的访问, 则可以为你的组织禁用它。</span><span class="sxs-lookup"><span data-stu-id="0322b-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="0322b-107">使用此部分中的过程可为你的组织启用或禁用匿名用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="0322b-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="0322b-108">通过为你的组织启用匿名用户访问, 仅指定运行 Access Edge 服务的服务器支持匿名用户的访问。</span><span class="sxs-lookup"><span data-stu-id="0322b-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="0322b-109">匿名用户不能参与您的组织中的任何会议, 除非您还配置了至少一个会议策略并将其应用于一个或多个用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="0322b-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="0322b-110">只有分配了会议策略 (配置为支持匿名用户) 的用户才可以邀请匿名用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="0322b-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="0322b-111">有关配置会议策略以支持邀请匿名用户的详细信息, 请参阅[管理会议策略](../../conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0322b-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="0322b-112">为你的组织启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="0322b-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="0322b-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="0322b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0322b-114">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="0322b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0322b-115">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**访问边缘配置**"。</span><span class="sxs-lookup"><span data-stu-id="0322b-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="0322b-116">在 "**访问边缘配置**" 页面上, 单击 "**全局**", 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="0322b-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0322b-117">在 "**编辑访问边缘配置**" 中, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="0322b-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="0322b-118">若要为你的组织启用匿名用户访问, 请选中 "**启用与匿名用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="0322b-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="0322b-119">若要为你的组织禁用匿名用户访问, 请清除 "**启用与匿名用户的通信**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="0322b-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="0322b-120">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="0322b-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0322b-121">使用 Windows PowerShell cmdlet 启用或禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="0322b-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0322b-122">你可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** cmdlet 管理匿名用户访问。</span><span class="sxs-lookup"><span data-stu-id="0322b-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="0322b-123">你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0322b-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="0322b-124">启用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="0322b-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="0322b-125">若要启用匿名用户访问, 请将**AllowAnonymousUsers**属性的值设置为 True ($True):</span><span class="sxs-lookup"><span data-stu-id="0322b-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="0322b-126">禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="0322b-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="0322b-127">若要禁用匿名用户访问, 请将**AllowAnonymousUsers**属性的值设置为 False ($False):</span><span class="sxs-lookup"><span data-stu-id="0322b-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="0322b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0322b-128">See Also</span></span>

[<span data-ttu-id="0322b-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="0322b-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
