---
title: 在 Skype for Business 客户端中配置智能联系人列表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要：了解如何在 Skype for Business 客户端中启用智能联系人列表功能。
ms.openlocfilehash: 1f049493d591cd561b87611f8a34f9176ace165a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095796"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="e4b1a-103">在 Skype for Business 客户端中配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="e4b1a-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="e4b1a-104">**摘要：** 了解如何在 Skype for Business 客户端中启用智能联系人列表功能。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="e4b1a-105">智能联系人列表功能允许自动填充最终用户的联系人列表。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="e4b1a-106">首次使用 Skype for Business 时，你的用户将自动看到其经理和团队中的其他人。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="e4b1a-107">默认情况下，为 Microsoft 365 和 Office 365 用户启用此功能，但您必须通过配置客户端策略设置为本地用户显式启用此功能。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="e4b1a-108">配置此功能时，请牢记以下事项：</span><span class="sxs-lookup"><span data-stu-id="e4b1a-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="e4b1a-109">用户（最多 13 个）将按以下顺序自动添加到智能联系人列表：</span><span class="sxs-lookup"><span data-stu-id="e4b1a-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="e4b1a-110">Manager</span><span class="sxs-lookup"><span data-stu-id="e4b1a-110">Manager</span></span>

  2. <span data-ttu-id="e4b1a-111">按字母顺序指示</span><span class="sxs-lookup"><span data-stu-id="e4b1a-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="e4b1a-112">按字母顺序排序的对等方</span><span class="sxs-lookup"><span data-stu-id="e4b1a-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="e4b1a-113">用户首次登录时，将创建一个名为"我的组"的新组。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="e4b1a-114">根据"经理"字段中填充的用户别名，组将自动填充用户 AD 组关系中的人。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="e4b1a-115">请注意，对 AD 组成员身份的更改不会导致在最初填充"我的组"后进行更新。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="e4b1a-116">如果用户删除联系人或组，则既不重新创建联系人也不重新创建组。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="e4b1a-117">如果启用自动标记，将为列表中的联系人标记状态更改。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="e4b1a-118">默认情况下，自动标记已打开，但你可以选择将其关闭。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="e4b1a-119">将通知组内的所有新用户，他们已添加到联系人列表。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="e4b1a-120">用户可以手动将新成员添加到其"我的组"或他们选择的其他组。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="e4b1a-121">此功能仅适用于首次登录的用户。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="e4b1a-122">如果用户之前从任何设备（例如，任何移动设备或 Mac）登录，则不为该用户启用该功能。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="e4b1a-123">配置智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="e4b1a-123">Configure Smart contacts list</span></span>

<span data-ttu-id="e4b1a-124">若要为用户启用智能联系人列表功能，需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e4b1a-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="e4b1a-125">创建新的 CsClientPolicy 条目并将其添加到全局客户端策略。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="e4b1a-126">确保仅为 Web 搜索配置通讯簿搜索。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="e4b1a-127">创建策略条目以启用智能联系人列表</span><span class="sxs-lookup"><span data-stu-id="e4b1a-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="e4b1a-128">若要创建策略条目以启用智能联系人列表功能，请使用 [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet 和 EnableClientAutoPopulateWithTeam 选项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4b1a-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="e4b1a-129">接下来，使用 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 将更改写入全局策略，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4b1a-129">Next, use the [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="e4b1a-130">可以选择创建一个策略来关闭自动标记，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4b1a-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="e4b1a-131">还必须将相应策略的 AddressBookAvailability 参数设置为 WebSearchOnly。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="e4b1a-132">有关详细信息，请参阅 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-132">For more information, see [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="e4b1a-133">疑难解答</span><span class="sxs-lookup"><span data-stu-id="e4b1a-133">Troubleshoot</span></span>

<span data-ttu-id="e4b1a-134">如果智能联系人列表未按照预期运行，请检查以下各项：</span><span class="sxs-lookup"><span data-stu-id="e4b1a-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="e4b1a-135">验证配置。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-135">Validate the configuration.</span></span> 

- <span data-ttu-id="e4b1a-136">确认已填充 AD 组织信息。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="e4b1a-137">收集新用户的 Skype for Business 客户端日志，以进一步分析。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="e4b1a-138">确认 Skype for Business 客户端 UI 未显示无法连接到通讯簿的消息。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="e4b1a-139">若要确认通讯簿连接，请执行 Skype for Business 客户端搜索栏中的用户搜索。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="e4b1a-140">当用户首次登录 Skype for Business 时，AD DS 复制问题可能导致无法解析联系人。</span><span class="sxs-lookup"><span data-stu-id="e4b1a-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>