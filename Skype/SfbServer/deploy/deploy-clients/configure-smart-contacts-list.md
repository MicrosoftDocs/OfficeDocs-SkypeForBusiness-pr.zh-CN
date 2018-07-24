---
title: 为业务客户端中 Skype 配置智能联系人列表
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要： 了解如何启用业务客户端 Skype 中的智能联系人列表功能。
ms.openlocfilehash: 72e8a2e5eb0640215ac4512ff210d30f31295fd8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976210"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="f9309-103">为业务客户端中 Skype 配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="f9309-103">Configure Smart contacts list in Skype for Business clients</span></span>
 
<span data-ttu-id="f9309-104">**摘要：** 了解如何启用业务客户端 Skype 中的智能联系人列表功能。</span><span class="sxs-lookup"><span data-stu-id="f9309-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>
  
<span data-ttu-id="f9309-105">智能联系人列表功能支持自动填充最终用户的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="f9309-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="f9309-106">时第一个 for Business，用户将自动使用 Skype 经理和其他人在上看到他们的团队。</span><span class="sxs-lookup"><span data-stu-id="f9309-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="f9309-107">在为 Office 365 用户，默认情况下启用此功能，但您必须明确启用此功能为您的内部部署用户通过配置客户端策略设置。</span><span class="sxs-lookup"><span data-stu-id="f9309-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>
  
<span data-ttu-id="f9309-108">配置此功能时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="f9309-108">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="f9309-109">用户，最多为 13、 自动添加到按以下顺序智能联系人列表中：</span><span class="sxs-lookup"><span data-stu-id="f9309-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>
    
  1. <span data-ttu-id="f9309-110">经理</span><span class="sxs-lookup"><span data-stu-id="f9309-110">Manager</span></span>
    
  2. <span data-ttu-id="f9309-111">按字母顺序显示下属</span><span class="sxs-lookup"><span data-stu-id="f9309-111">Directs in alphabetical order</span></span>
    
  3. <span data-ttu-id="f9309-112">按字母顺序显示同事</span><span class="sxs-lookup"><span data-stu-id="f9309-112">Peers in alphabetical order</span></span>
    
- <span data-ttu-id="f9309-113">当用户第一次登录时，系统将创建一个名为“我的组”的新组。</span><span class="sxs-lookup"><span data-stu-id="f9309-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="f9309-114">组会自动填入管理器字段中填充的用户别名基于用户的 AD 组关系中的人员。</span><span class="sxs-lookup"><span data-stu-id="f9309-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="f9309-115">请注意，在“我的组”最初填充之后，对 AD 组成员资格做任何更改都不会引起“我的组”发生更新。</span><span class="sxs-lookup"><span data-stu-id="f9309-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="f9309-116">如果用户删除某个联系人或组，则不会重新创建联系人或组。</span><span class="sxs-lookup"><span data-stu-id="f9309-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 
    
- <span data-ttu-id="f9309-117">如果自动标记功能启用，将为列表中的联系人标记状态更改。</span><span class="sxs-lookup"><span data-stu-id="f9309-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="f9309-118">自动标记功能默认情况下启用，但是您可以选择将其禁用。</span><span class="sxs-lookup"><span data-stu-id="f9309-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 
    
- <span data-ttu-id="f9309-119">组中的所有新用户都会收到通知，知晓他们已被添加到联系人列表。</span><span class="sxs-lookup"><span data-stu-id="f9309-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="f9309-120">用户可以手动选择将新成员添加到其“我的组”或其选择的其他组。</span><span class="sxs-lookup"><span data-stu-id="f9309-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>
    
- <span data-ttu-id="f9309-121">此功能仅适用于首次登录的用户。</span><span class="sxs-lookup"><span data-stu-id="f9309-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="f9309-122">如果用户以前曾从任何设备（例如，任何移动设备或 Mac）登录，则该用户无法使用该功能。</span><span class="sxs-lookup"><span data-stu-id="f9309-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>
    
## <a name="configure-smart-contacts-list"></a><span data-ttu-id="f9309-123">配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="f9309-123">Configure Smart contacts list</span></span>

<span data-ttu-id="f9309-124">要为您的用户启用智能联系人列表功能，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f9309-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 
  
- <span data-ttu-id="f9309-125">创建一个新的 CsClientPolicy 条目并将其添加到全局客户端策略。</span><span class="sxs-lookup"><span data-stu-id="f9309-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 
    
- <span data-ttu-id="f9309-126">确保将通讯簿搜索设置为仅限 Web 搜索。</span><span class="sxs-lookup"><span data-stu-id="f9309-126">Make sure that Address Book Search is configured for Web Search only.</span></span>
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="f9309-127">创建策略条目以启用智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="f9309-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="f9309-128">若要创建一个策略项，以便启用智能联系人列表功能，用于[New-csclientpolicyentry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet EnableClientAutoPopulateWithTeam 选项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9309-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="f9309-129">接下来，使用[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 更改写入到的全局策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9309-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>
  
```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="f9309-130">也可以选择创建策略来关闭自动标记功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f9309-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>
  
```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}

```

<span data-ttu-id="f9309-131">还必须将对应策略的 AddressBookAvailability 参数设置为 WebSearchOnly。</span><span class="sxs-lookup"><span data-stu-id="f9309-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="f9309-132">有关详细信息，请参阅[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f9309-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 
  
### <a name="troubleshoot"></a><span data-ttu-id="f9309-133">疑难解答</span><span class="sxs-lookup"><span data-stu-id="f9309-133">Troubleshoot</span></span>

<span data-ttu-id="f9309-134">如果智能联系人列表未按预期工作，请检查以下各项：</span><span class="sxs-lookup"><span data-stu-id="f9309-134">If Smart contacts list is not functioning as expected, check the following:</span></span>
  
- <span data-ttu-id="f9309-135">验证配置。</span><span class="sxs-lookup"><span data-stu-id="f9309-135">Validate the configuration.</span></span> 
    
- <span data-ttu-id="f9309-136">确认已填充 AD 组织信息。</span><span class="sxs-lookup"><span data-stu-id="f9309-136">Confirm that the AD organization information is populated.</span></span>
    
- <span data-ttu-id="f9309-137">为业务客户端日志收集 Skype，供进一步分析新用户。</span><span class="sxs-lookup"><span data-stu-id="f9309-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>
    
- <span data-ttu-id="f9309-138">确认 Business 客户端 UI Skype 不显示一条消息，无法连接到通讯簿。</span><span class="sxs-lookup"><span data-stu-id="f9309-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="f9309-139">若要确认通讯簿连接，请执行业务客户端搜索栏 Skype 中的用户搜索。</span><span class="sxs-lookup"><span data-stu-id="f9309-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>
    
- <span data-ttu-id="f9309-140">AD DS 复制问题可能导致无法解析当用户第一次登录到 for Business 的 Skype 联系人。</span><span class="sxs-lookup"><span data-stu-id="f9309-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>
    

