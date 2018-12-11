---
title: 启用或禁用匿名用户访问
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 35104d7d7128e76f7691a4ddf1ad9693a427eb40
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222749"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="1977b-102">启用或禁用匿名用户访问中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="1977b-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="1977b-103">匿名用户是没有用户帐户，或组织的 Active Directory 域服务中支持联盟域，但可以邀请远程参加内部会议的用户。</span><span class="sxs-lookup"><span data-stu-id="1977b-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="1977b-104">通过允许匿名参与会议启用匿名用户 （即，用户通过会议或会议仅密钥验证其身份） 加入会议。</span><span class="sxs-lookup"><span data-stu-id="1977b-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="1977b-105">允许匿名参与需要启用您的组织。</span><span class="sxs-lookup"><span data-stu-id="1977b-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="1977b-106">如果您以后想要临时或永久防止匿名用户访问，您可以为组织禁用它。</span><span class="sxs-lookup"><span data-stu-id="1977b-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="1977b-107">使用本节中的过程以启用或禁用匿名用户访问您的组织。</span><span class="sxs-lookup"><span data-stu-id="1977b-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="1977b-108">通过启用匿名用户访问您的组织仅指定运行访问边缘服务的服务器支持匿名用户访问。</span><span class="sxs-lookup"><span data-stu-id="1977b-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="1977b-109">匿名用户不能参与组织中的任何会议，直到您还配置至少一个会议策略，并将其应用于一个或多个用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="1977b-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="1977b-110">可以邀请匿名用户加入会议的唯一用户是指分配配置以支持匿名用户的会议策略的用户。</span><span class="sxs-lookup"><span data-stu-id="1977b-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="1977b-111">有关配置会议策略以支持邀请匿名用户的详细信息，请参阅[管理会议策略](../../conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1977b-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="1977b-112">启用或禁用匿名用户访问您的组织</span><span class="sxs-lookup"><span data-stu-id="1977b-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="1977b-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1977b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1977b-114">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="1977b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1977b-115">在左侧的导航栏中，单击**外部用户访问**，然后单击**访问边缘配置**。</span><span class="sxs-lookup"><span data-stu-id="1977b-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="1977b-116">在**访问边缘配置**页上，单击**全局**，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="1977b-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1977b-117">在**编辑访问边缘配置**中，执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="1977b-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="1977b-118">要为组织的匿名用户访问，请选中**启用与匿名用户的通信**复选框。</span><span class="sxs-lookup"><span data-stu-id="1977b-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="1977b-119">若要禁用匿名用户访问您的组织，请清除**启用与匿名用户的通信**复选框。</span><span class="sxs-lookup"><span data-stu-id="1977b-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="1977b-120">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1977b-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1977b-121">启用或禁用匿名用户访问使用 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="1977b-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1977b-122">您可以使用 Windows PowerShell 和**Set-csaccessedgeconfiguration** cmdlet 来管理匿名用户访问。</span><span class="sxs-lookup"><span data-stu-id="1977b-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="1977b-123">可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1977b-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="1977b-124">若要启用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="1977b-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="1977b-125">要启用匿名用户访问，请将**AllowAnonymousUsers**属性的值设置为 True ($True) 中：</span><span class="sxs-lookup"><span data-stu-id="1977b-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="1977b-126">若要禁用匿名用户访问</span><span class="sxs-lookup"><span data-stu-id="1977b-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="1977b-127">要禁用匿名用户访问，请将**AllowAnonymousUsers**属性的值设置为 False ($False) 中：</span><span class="sxs-lookup"><span data-stu-id="1977b-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="1977b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1977b-128">See Also</span></span>

[<span data-ttu-id="1977b-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="1977b-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
