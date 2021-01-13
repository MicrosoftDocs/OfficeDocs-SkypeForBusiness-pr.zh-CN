---
title: 重置外部用户访问的全局策略
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: 无法完全删除全局策略。使用全局策略的“删除”选项只能将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。
ms.openlocfilehash: be4f99c5b98ca46e7fed57781cf1661a2755a4ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817242"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="e075e-104">在 Skype for Business Server 中重置外部用户访问的全局策略</span><span class="sxs-lookup"><span data-stu-id="e075e-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="e075e-105">如果创建或配置了不想再使用的外部用户访问策略，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e075e-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="e075e-106">删除已创建的任何站点策略或用户策略。</span><span class="sxs-lookup"><span data-stu-id="e075e-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="e075e-p102">将全局策略重置为默认设置。默认的全局策略设置拒绝任何外部用户访问。无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="e075e-p102">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>

<span data-ttu-id="e075e-p103">无法完全删除全局策略。使用全局策略的“删除”选项只能将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。</span><span class="sxs-lookup"><span data-stu-id="e075e-p103">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="e075e-112">将全局策略重置为默认设置</span><span class="sxs-lookup"><span data-stu-id="e075e-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="e075e-113">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="e075e-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e075e-114">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="e075e-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="e075e-115">在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。</span><span class="sxs-lookup"><span data-stu-id="e075e-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="e075e-116">在“外部访问策略”选项卡上，单击全局策略，再单击“编辑”，然后单击“删除”。</span><span class="sxs-lookup"><span data-stu-id="e075e-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="e075e-p104">当系统提示您确认删除时，单击“确定”。此时会在页面顶部显示一条消息，通知您已重置全局策略。</span><span class="sxs-lookup"><span data-stu-id="e075e-p104">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e075e-119">使用 cmdlet 重置全局外部访问Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e075e-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e075e-120">全局外部访问策略可以使用 Windows PowerShell 和 Remove-CsExternalAccessPolicy cmdlet 重置。</span><span class="sxs-lookup"><span data-stu-id="e075e-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="e075e-121">此 cmdlet 可以从 Skype for Business Server 命令行管理程序或远程会话命令行管理程序Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e075e-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="e075e-122">重置全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="e075e-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="e075e-123">此命令重置全局外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="e075e-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="e075e-124">有关详细信息，请参阅 [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="e075e-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


