---
title: 在 Skype for Business Server 2015 中更改现有存档策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要： 了解如何更改用户的业务服务器 2015 Skype 的存档策略。
ms.openlocfilehash: f03ddc0799868e825c46fad2f93ba93d3b8a071a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="d38f9-103">在 Skype for Business Server 2015 中更改现有存档策略</span><span class="sxs-lookup"><span data-stu-id="d38f9-103">Change an existing archiving policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d38f9-104">**摘要：**了解如何更改用户的业务服务器 2015 Skype 的存档策略。</span><span class="sxs-lookup"><span data-stu-id="d38f9-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d38f9-105">当您第一次部署业务服务器 2015 Skype 时，您设置初始归档策略，用以确定如何归档为您部署中的用户实现。</span><span class="sxs-lookup"><span data-stu-id="d38f9-105">When you first deploy Skype for Business Server 2015, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="d38f9-106">本主题介绍了如何管理和修订策略。</span><span class="sxs-lookup"><span data-stu-id="d38f9-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="d38f9-107">使用控制面板更改存档策略</span><span class="sxs-lookup"><span data-stu-id="d38f9-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="d38f9-108">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d38f9-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d38f9-109">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="d38f9-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d38f9-110">在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档策略**”。</span><span class="sxs-lookup"><span data-stu-id="d38f9-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d38f9-111">在策略列表中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d38f9-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="d38f9-112">若要更改整个部署的策略，请单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="d38f9-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="d38f9-113">若要更改单个站点的策略，请单击策略列表中的站点名称，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="d38f9-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="d38f9-114">若要更改单个用户或用户组的策略，请单击策略列表中的用户或用户组的名称，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="d38f9-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d38f9-115">在“**编辑存档策略**”页中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d38f9-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="d38f9-116">若要为策略启用或禁用内部存档，请选中或清除“**存档内部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d38f9-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d38f9-117">若要为策略启用或禁用外部存档，请选中或清除“**存档外部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d38f9-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="d38f9-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d38f9-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d38f9-119">用户策略的设置仅适用于要应用该策略的特定用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="d38f9-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="d38f9-120">有关详细信息，请参阅[应用中业务服务器 2015年的 Skype 用户的存档策略](apply-a-policy-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="d38f9-120">For details, see [Apply an archiving policy to users in Skype for Business Server 2015](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="d38f9-121">使用 Windows PowerShell 更改存档策略</span><span class="sxs-lookup"><span data-stu-id="d38f9-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="d38f9-122">您也可以使用 Windows PowerShell **Set-CsArchivingPolicy** cmdlet 更改存档策略。</span><span class="sxs-lookup"><span data-stu-id="d38f9-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="d38f9-123">启用存档策略</span><span class="sxs-lookup"><span data-stu-id="d38f9-123">Enable archiving policies</span></span>

<span data-ttu-id="d38f9-124">要启用内部通信会话的存档，请将 ArchiveInternal 参数的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="d38f9-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True

```

<span data-ttu-id="d38f9-125">要启用外部通信会话的存档，请将 ArchiveExternal 数的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="d38f9-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True

```

<span data-ttu-id="d38f9-126">要启用这两个内部和外部通信会话存档，请使用 ArchiveInternal 和 ArchiveExternal 参数的值设置为 True:</span><span class="sxs-lookup"><span data-stu-id="d38f9-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

```

### <a name="disable-archiving-policies"></a><span data-ttu-id="d38f9-127">禁用存档策略</span><span class="sxs-lookup"><span data-stu-id="d38f9-127">Disable archiving policies</span></span>

<span data-ttu-id="d38f9-128">要禁用全部存档，请将 ArchiveInternal 和 ArchiveExternal 参数的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="d38f9-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False

```