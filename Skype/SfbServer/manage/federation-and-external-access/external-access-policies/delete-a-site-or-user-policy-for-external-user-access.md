---
title: 删除外部用户访问的站点或用户策略
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 你可以删除 "外部访问策略" 页面上 "Skype for Business 服务器" 控制面板中列出的任何网站或用户策略。
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280122"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="3b93b-103">删除外部用户访问的站点或用户策略</span><span class="sxs-lookup"><span data-stu-id="3b93b-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="3b93b-104">如果您已创建或配置了不希望再使用的外部用户访问策略, 则可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3b93b-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="3b93b-105">删除您创建的任何网站或用户策略。</span><span class="sxs-lookup"><span data-stu-id="3b93b-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="3b93b-106">将全局策略重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="3b93b-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="3b93b-107">默认全局策略设置拒绝任何外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="3b93b-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="3b93b-108">无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="3b93b-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="3b93b-109">你可以删除 "**外部访问策略**" 页面上 "Skype For business 服务器" 控制面板中列出的任何网站或用户策略。</span><span class="sxs-lookup"><span data-stu-id="3b93b-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="3b93b-110">删除全局策略实际上并不会将其删除, 而只是将其重置为默认设置, 而不包括对任何外部用户访问选项的支持。</span><span class="sxs-lookup"><span data-stu-id="3b93b-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="3b93b-111">有关重置全局策略的详细信息, 请参阅[重置外部用户访问的全局策略](reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3b93b-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="3b93b-112">删除用于外部用户访问的网站或用户策略</span><span class="sxs-lookup"><span data-stu-id="3b93b-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="3b93b-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3b93b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b93b-114">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="3b93b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3b93b-115">单击 "**外部用户访问**", 单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="3b93b-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="3b93b-116">在 "**外部访问策略**" 选项卡上, 单击要删除的网站或用户策略, 单击 "**编辑**", 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="3b93b-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="3b93b-117">当系统提示确认删除时, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3b93b-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3b93b-118">使用 Windows PowerShell Cmdlet 删除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="3b93b-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3b93b-119">可以使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 删除外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="3b93b-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="3b93b-120">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="3b93b-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="3b93b-121">删除特定的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="3b93b-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="3b93b-122">此命令将删除应用于 Redmond 网站的外部访问策略:</span><span class="sxs-lookup"><span data-stu-id="3b93b-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="3b93b-123">删除应用到每用户范围的所有外部访问策略</span><span class="sxs-lookup"><span data-stu-id="3b93b-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="3b93b-124">此命令将删除在每个用户范围内配置的所有外部访问策略:</span><span class="sxs-lookup"><span data-stu-id="3b93b-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="3b93b-125">删除禁用外部用户访问权限的所有外部访问策略</span><span class="sxs-lookup"><span data-stu-id="3b93b-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="3b93b-126">此命令将删除在禁用外部用户访问权限的所有外部访问策略:</span><span class="sxs-lookup"><span data-stu-id="3b93b-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="3b93b-127">有关详细信息, 请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="3b93b-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
