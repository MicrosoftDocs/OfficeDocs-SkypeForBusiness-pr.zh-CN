---
title: 重置外部用户访问的全局策略
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: 您不能完全删除全局策略。 使用全局策略中的 "**删除**" 选项仅将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818263"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="4b415-104">在 Skype for Business 服务器中重置外部用户访问的全局策略</span><span class="sxs-lookup"><span data-stu-id="4b415-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="4b415-105">如果您已创建或配置了不希望再使用的外部用户访问策略，则可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4b415-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="4b415-106">删除您创建的任何网站或用户策略。</span><span class="sxs-lookup"><span data-stu-id="4b415-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="4b415-107">将全局策略重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="4b415-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="4b415-108">默认全局策略设置拒绝任何外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="4b415-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="4b415-109">无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="4b415-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="4b415-110">您不能完全删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="4b415-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="4b415-111">使用全局策略中的 "**删除**" 选项仅将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。</span><span class="sxs-lookup"><span data-stu-id="4b415-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="4b415-112">将全局策略重置为默认设置</span><span class="sxs-lookup"><span data-stu-id="4b415-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="4b415-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4b415-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b415-114">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="4b415-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="4b415-115">在左侧导航栏中，单击 "**外部用户访问**"，单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="4b415-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="4b415-116">在 "**外部访问策略**" 选项卡上，单击 "全局策略"，单击 "**编辑**"，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="4b415-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="4b415-117">当系统提示确认删除时，单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4b415-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="4b415-118">将在页面顶部显示一条消息，通知您全局策略已重置。</span><span class="sxs-lookup"><span data-stu-id="4b415-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4b415-119">使用 Windows PowerShell Cmdlet 重置全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="4b415-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4b415-120">全局外部访问策略可以通过使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 进行重置。</span><span class="sxs-lookup"><span data-stu-id="4b415-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="4b415-121">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从远程会话 Windows PowerShell 运行。</span><span class="sxs-lookup"><span data-stu-id="4b415-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="4b415-122">重置全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="4b415-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="4b415-123">此命令将重置全局外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="4b415-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="4b415-124">有关详细信息，请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="4b415-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


