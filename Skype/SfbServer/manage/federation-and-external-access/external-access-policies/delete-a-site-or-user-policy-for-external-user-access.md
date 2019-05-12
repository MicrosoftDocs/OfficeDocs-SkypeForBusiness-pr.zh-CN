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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以删除中列出的 Skype 业务 Server 控制面板的外部访问策略页的任何站点或用户策略。
ms.openlocfilehash: 517c5b015d4e2fe5de584a8079af1bb4f5ed248a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920415"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="02471-103">删除外部用户访问的站点或用户策略</span><span class="sxs-lookup"><span data-stu-id="02471-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="02471-104">如果您已创建或配置不再想要使用的外部用户访问策略，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="02471-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="02471-105">删除您创建的任何站点或用户策略。</span><span class="sxs-lookup"><span data-stu-id="02471-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="02471-106">全局策略重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="02471-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="02471-107">默认全局策略设置拒绝所有外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="02471-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="02471-108">无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="02471-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="02471-109">您可以删除中列出的 Skype 业务 Server 控制面板的**外部访问策略**页的任何站点或用户策略。</span><span class="sxs-lookup"><span data-stu-id="02471-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="02471-110">删除全局策略不会实际删除，但仅将其重置为默认设置，不包括支持外部用户访问的任何选项。</span><span class="sxs-lookup"><span data-stu-id="02471-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="02471-111">有关重置全局策略的详细信息，请参阅[外部用户访问的全局策略重置](reset-the-global-policy-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="02471-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="02471-112">删除外部用户访问的站点或用户策略</span><span class="sxs-lookup"><span data-stu-id="02471-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="02471-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="02471-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02471-114">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="02471-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="02471-115">单击**外部用户访问**，单击**外部访问策略**。</span><span class="sxs-lookup"><span data-stu-id="02471-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="02471-116">在**外部访问策略**选项卡中，单击您想要删除，单击**编辑**，然后单击**删除**站点或用户的策略。</span><span class="sxs-lookup"><span data-stu-id="02471-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="02471-117">当提示您确认删除操作，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="02471-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="02471-118">使用 Windows PowerShell Cmdlet 删除 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="02471-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="02471-119">可以使用 Windows PowerShell 和 Remove-csexternalaccesspolicy cmdlet 删除外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="02471-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="02471-120">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02471-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="02471-121">删除特定外部访问策略</span><span class="sxs-lookup"><span data-stu-id="02471-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="02471-122">此命令删除应用到 Redmond 站点的外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="02471-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="02471-123">若要删除所有外部访问策略应用于每用户范围</span><span class="sxs-lookup"><span data-stu-id="02471-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="02471-124">此命令删除在每用户范围配置的所有外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="02471-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="02471-125">若要删除其中禁用外部用户访问的所有外部访问策略</span><span class="sxs-lookup"><span data-stu-id="02471-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="02471-126">此命令可删除外部用户访问已禁用的所有外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="02471-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="02471-127">有关详细信息，请参阅[Remove-csexternalaccesspolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="02471-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
