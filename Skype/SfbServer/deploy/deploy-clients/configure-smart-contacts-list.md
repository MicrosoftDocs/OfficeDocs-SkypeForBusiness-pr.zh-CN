---
title: 在 Skype for Business Server 中配置智能联系人列表
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要： 了解如何打开 Skype 业务客户端中的智能联系人列表功能。
ms.openlocfilehash: f5b5b8f7baa0ce848765a0f2b62aabb118ecb224
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-smart-contacts-list-in-skype-for-business-server"></a><span data-ttu-id="6c435-103">在 Skype for Business Server 中配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="6c435-103">Configure Smart contacts list in Skype for Business Server</span></span>
 
<span data-ttu-id="6c435-104">**摘要：**了解如何打开 Skype 业务客户端中的智能联系人列表功能。</span><span class="sxs-lookup"><span data-stu-id="6c435-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>
  
<span data-ttu-id="6c435-105">智能联系人列表功能支持自动填充最终用户的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="6c435-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="6c435-106">后第一个使用 Skype 的业务，您的用户将自动看到他们的经理和其他人在他们的团队。</span><span class="sxs-lookup"><span data-stu-id="6c435-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="6c435-107">在默认情况下，Office 365 提供用户启用此功能，但您必须显式启用该功能为您的内部用户通过配置客户端策略设置。</span><span class="sxs-lookup"><span data-stu-id="6c435-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>
  
<span data-ttu-id="6c435-108">配置此功能时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="6c435-108">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="6c435-109">用户，到 13 时，将自动添加到智能联系人列表以下列顺序：</span><span class="sxs-lookup"><span data-stu-id="6c435-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>
    
  1. <span data-ttu-id="6c435-110">经理</span><span class="sxs-lookup"><span data-stu-id="6c435-110">Manager</span></span>
    
  2. <span data-ttu-id="6c435-111">按字母顺序显示下属</span><span class="sxs-lookup"><span data-stu-id="6c435-111">Directs in alphabetical order</span></span>
    
  3. <span data-ttu-id="6c435-112">按字母顺序显示同事</span><span class="sxs-lookup"><span data-stu-id="6c435-112">Peers in alphabetical order</span></span>
    
- <span data-ttu-id="6c435-113">当用户第一次登录时，系统将创建一个名为“我的组”的新组。</span><span class="sxs-lookup"><span data-stu-id="6c435-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="6c435-114">组会自动填充与用户的 AD 组关系基于在经理字段中填充用户别名中的人。</span><span class="sxs-lookup"><span data-stu-id="6c435-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="6c435-115">请注意，在“我的组”最初填充之后，对 AD 组成员资格做任何更改都不会引起“我的组”发生更新。</span><span class="sxs-lookup"><span data-stu-id="6c435-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="6c435-116">如果用户删除某个联系人或组，则不会重新创建联系人或组。</span><span class="sxs-lookup"><span data-stu-id="6c435-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 
    
- <span data-ttu-id="6c435-117">如果自动标记功能启用，将为列表中的联系人标记状态更改。</span><span class="sxs-lookup"><span data-stu-id="6c435-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="6c435-118">自动标记功能默认情况下启用，但是您可以选择将其禁用。</span><span class="sxs-lookup"><span data-stu-id="6c435-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 
    
- <span data-ttu-id="6c435-119">组中的所有新用户都会收到通知，知晓他们已被添加到联系人列表。</span><span class="sxs-lookup"><span data-stu-id="6c435-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="6c435-120">用户可以手动选择将新成员添加到其“我的组”或其选择的其他组。</span><span class="sxs-lookup"><span data-stu-id="6c435-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>
    
- <span data-ttu-id="6c435-121">此功能仅适用于首次登录的用户。</span><span class="sxs-lookup"><span data-stu-id="6c435-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="6c435-122">如果用户以前曾从任何设备（例如，任何移动设备或 Mac）登录，则该用户无法使用该功能。</span><span class="sxs-lookup"><span data-stu-id="6c435-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>
    
## <a name="configure-smart-contacts-list"></a><span data-ttu-id="6c435-123">配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="6c435-123">Configure Smart contacts list</span></span>

<span data-ttu-id="6c435-124">要为您的用户启用智能联系人列表功能，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6c435-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 
  
- <span data-ttu-id="6c435-125">创建一个新的 CsClientPolicy 条目并将其添加到全局客户端策略。</span><span class="sxs-lookup"><span data-stu-id="6c435-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 
    
- <span data-ttu-id="6c435-126">确保将通讯簿搜索设置为仅限 Web 搜索。</span><span class="sxs-lookup"><span data-stu-id="6c435-126">Make sure that Address Book Search is configured for Web Search only.</span></span>
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="6c435-127">创建策略条目以启用智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="6c435-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="6c435-128">若要创建一个策略项，以便启用智能联系人列表功能，使用[New CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet EnableClientAutoPopulateWithTeam 选项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c435-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="6c435-129">接下来，使用[一组 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 将更改写入到的全局策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c435-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>
  
```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="6c435-130">也可以选择创建策略来关闭自动标记功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c435-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>
  
```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}

```

<span data-ttu-id="6c435-131">还必须将对应策略的 AddressBookAvailability 参数设置为 WebSearchOnly。</span><span class="sxs-lookup"><span data-stu-id="6c435-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="6c435-132">有关详细信息，请参阅[设置 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6c435-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 
  
### <a name="troubleshoot"></a><span data-ttu-id="6c435-133">疑难解答</span><span class="sxs-lookup"><span data-stu-id="6c435-133">Troubleshoot</span></span>

<span data-ttu-id="6c435-134">如果智能联系人列表未按预期工作，请检查以下各项：</span><span class="sxs-lookup"><span data-stu-id="6c435-134">If Smart contacts list is not functioning as expected, check the following:</span></span>
  
- <span data-ttu-id="6c435-135">验证配置。</span><span class="sxs-lookup"><span data-stu-id="6c435-135">Validate the configuration.</span></span> 
    
- <span data-ttu-id="6c435-136">确认广告组织信息进行填充。</span><span class="sxs-lookup"><span data-stu-id="6c435-136">Confirm that the AD organization information is populated.</span></span>
    
- <span data-ttu-id="6c435-137">收集的业务客户端登录 Skype 新用户进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="6c435-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>
    
- <span data-ttu-id="6c435-138">请确认 Skype 业务客户端用户界面不会显示一条消息，它不能连接到通讯簿。</span><span class="sxs-lookup"><span data-stu-id="6c435-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="6c435-139">确认通讯簿的连接，执行业务客户端搜索栏的 Skype 用户搜索。</span><span class="sxs-lookup"><span data-stu-id="6c435-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>
    
- <span data-ttu-id="6c435-140">如果连接到通讯簿时出现问题，请使用 Strace 收集 HTTPS 跟踪和 HTTPReplay，以分析收集的跟踪。</span><span class="sxs-lookup"><span data-stu-id="6c435-140">If there are problems connecting to the Address Book, use STrace to collect HTTPS traces and HTTPReplay to analyze the collected traces.</span></span> <span data-ttu-id="6c435-141">有关详细信息，请参阅[相关的博客文章](https://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/)。</span><span class="sxs-lookup"><span data-stu-id="6c435-141">For more information, see the [related blog post](https://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/).</span></span>
    
- <span data-ttu-id="6c435-142">AD DS 复制问题可能导致当用户首次登录 Skype 业务无法解析的联系人。</span><span class="sxs-lookup"><span data-stu-id="6c435-142">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>
    

