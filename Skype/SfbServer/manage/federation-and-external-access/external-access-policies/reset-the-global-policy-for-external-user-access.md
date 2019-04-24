---
title: 重置外部用户访问的全局策略
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 不能完全删除全局策略。 使用全局策略上的**删除**选项仅将重置全局策略为默认设置，不包括支持外部用户访问的任何选项。
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197623"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="3cbbb-104">Skype 中的外部用户访问的全局策略重置为业务服务器</span><span class="sxs-lookup"><span data-stu-id="3cbbb-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="3cbbb-105">如果您已创建或配置不再想要使用的外部用户访问策略，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3cbbb-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="3cbbb-106">删除您创建的任何站点或用户策略。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="3cbbb-107">全局策略重置为默认设置。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="3cbbb-108">默认全局策略设置拒绝所有外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="3cbbb-109">无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="3cbbb-110">不能完全删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="3cbbb-111">使用全局策略上的**删除**选项仅将重置全局策略为默认设置，不包括支持外部用户访问的任何选项。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="3cbbb-112">若要将全局策略重置为默认设置</span><span class="sxs-lookup"><span data-stu-id="3cbbb-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="3cbbb-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3cbbb-114">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="3cbbb-115">在左侧的导航栏中，单击**外部用户访问**，单击**外部访问策略**。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="3cbbb-116">在**外部访问策略**选项卡上，单击该全局策略，单击**编辑**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="3cbbb-117">当提示您确认删除操作，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="3cbbb-118">在告知您已被重置全局策略页的顶部显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3cbbb-119">使用 Windows PowerShell Cmdlet 重全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="3cbbb-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3cbbb-120">使用 Windows PowerShell 和 Remove-csexternalaccesspolicy cmdlet，可以重置全局外部访问策略。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="3cbbb-121">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="3cbbb-122">若要重置全局外部访问策略</span><span class="sxs-lookup"><span data-stu-id="3cbbb-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="3cbbb-123">此命令重置全局外部访问策略：</span><span class="sxs-lookup"><span data-stu-id="3cbbb-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="3cbbb-124">有关详细信息，请参阅[Remove-csexternalaccesspolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="3cbbb-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


