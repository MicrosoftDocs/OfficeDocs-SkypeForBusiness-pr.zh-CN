---
title: 更改 Skype for Business Server 中的现有存档策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要：了解如何更改 Skype for Business Server 的用户存档策略。
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817702"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="395b7-103">更改 Skype for Business Server 中的现有存档策略</span><span class="sxs-lookup"><span data-stu-id="395b7-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="395b7-104">**摘要：** 了解如何更改 Skype for Business Server 的用户存档策略。</span><span class="sxs-lookup"><span data-stu-id="395b7-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="395b7-105">首次部署 Skype for Business Server 时，将设置初始存档策略，以确定如何为部署中的用户实施存档。</span><span class="sxs-lookup"><span data-stu-id="395b7-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="395b7-106">本主题介绍如何管理和修订策略。</span><span class="sxs-lookup"><span data-stu-id="395b7-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="395b7-107">使用控制面板更改存档策略</span><span class="sxs-lookup"><span data-stu-id="395b7-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="395b7-108">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="395b7-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="395b7-109">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="395b7-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="395b7-110">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="395b7-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="395b7-111">在策略列表中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="395b7-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="395b7-112">若要更改整个部署的策略，请单击策略列表中的“全局”，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="395b7-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="395b7-113">若要更改单个站点的策略，请单击策略列表中的站点名称，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="395b7-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="395b7-114">若要更改单个用户或用户组的策略，请单击策略列表中的用户或用户组的名称，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="395b7-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="395b7-115">在“编辑存档策略”页中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="395b7-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="395b7-116">若要为策略启用或禁用内部存档，请选中或清除“存档内部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="395b7-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="395b7-117">若要为策略启用或禁用外部存档，请选中或清除“存档外部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="395b7-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="395b7-118">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="395b7-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="395b7-119">用户策略的设置仅适用于要应用该策略的特定用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="395b7-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="395b7-120">有关详细信息，请参阅 [在 Skype for Business Server 中向用户应用存档策略](apply-a-policy-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="395b7-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="395b7-121">使用策略更改存档Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="395b7-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="395b7-122">您还可以使用 **Set-CsArchivingPolicy** cmdlet Windows PowerShell存档策略。</span><span class="sxs-lookup"><span data-stu-id="395b7-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="395b7-123">启用存档策略</span><span class="sxs-lookup"><span data-stu-id="395b7-123">Enable archiving policies</span></span>

<span data-ttu-id="395b7-124">若要启用内部通信会话的存档，将 ArchiveInternal 参数的值设置为 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="395b7-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="395b7-125">若要启用外部通信会话的存档，将 ArchiveExternal 参数的值设置为 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="395b7-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="395b7-126">若要同时启用内部和外部通信会话的存档，请同时将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 True：</span><span class="sxs-lookup"><span data-stu-id="395b7-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="395b7-127">禁用存档策略</span><span class="sxs-lookup"><span data-stu-id="395b7-127">Disable archiving policies</span></span>

<span data-ttu-id="395b7-128">若要完全禁用存档，请同时将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="395b7-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
