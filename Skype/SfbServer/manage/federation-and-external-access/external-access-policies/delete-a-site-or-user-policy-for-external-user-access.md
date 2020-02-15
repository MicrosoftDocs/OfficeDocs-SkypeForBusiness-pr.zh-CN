---
title: 删除用于外部用户访问的站点或用户策略
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以删除在 "外部访问策略" 页上的 Skype for Business Server 控制面板中列出的任何站点或用户策略。
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041231"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="698df-103">删除用于外部用户访问的站点或用户策略</span><span class="sxs-lookup"><span data-stu-id="698df-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="698df-104">如果创建或配置了不想再使用的外部用户访问策略，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="698df-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="698df-105">删除已创建的任何站点策略或用户策略。</span><span class="sxs-lookup"><span data-stu-id="698df-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="698df-p101">将全局策略重置为默认设置。默认的全局策略设置拒绝任何外部用户访问。无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="698df-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="698df-109">您可以删除在 "**外部访问策略**" 页上的 Skype For Business Server 控制面板中列出的任何站点或用户策略。</span><span class="sxs-lookup"><span data-stu-id="698df-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="698df-110">删除全局策略时不会真正删除该策略，而只是将其重置为不支持任何外部用户访问选项的默认设置。</span><span class="sxs-lookup"><span data-stu-id="698df-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="698df-111">有关重置全局策略的详细信息，请参阅[重置外部用户访问的全局策略](reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="698df-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="698df-112">删除外部用户访问的站点或用户策略</span><span class="sxs-lookup"><span data-stu-id="698df-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="698df-113">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="698df-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="698df-114">打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="698df-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="698df-115">单击“外部用户访问”\*\*\*\*，再单击“外部访问策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="698df-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="698df-116">在“外部访问策略”\*\*\*\* 选项卡上，单击要删除的站点或用户策略，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="698df-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="698df-117">当系统提示您确认删除时，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="698df-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="698df-118">使用 Windows PowerShell Cmdlet 删除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="698df-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="698df-119">可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 删除外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="698df-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="698df-120">此 cmdlet 可从 Skype for Business Server 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="698df-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="698df-121">删除特定的外部访问策略</span><span class="sxs-lookup"><span data-stu-id="698df-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="698df-122">此命令删除适用于 Redmond 站点的外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="698df-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="698df-123">删除应用于每用户作用域的所有外部访问策略</span><span class="sxs-lookup"><span data-stu-id="698df-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="698df-124">此命令删除在每用户范围配置的所有外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="698df-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="698df-125">删除在禁用外部用户访问的所有外部访问策略</span><span class="sxs-lookup"><span data-stu-id="698df-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="698df-126">此命令删除已禁用外部用户访问的所有外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="698df-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="698df-127">有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="698df-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
