---
title: 在 Skype for Business Online 中配置状态
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- O365P_OnlinePresenceDesc
description: '了解如何设置 Skype for business，以便你可以查看同事的可用性。 '
ms.openlocfilehash: b06139d3614335505c7f8682700aa3d7d6fb5df8
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739190"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="00af6-103">在 Skype for Business Online 中配置状态</span><span class="sxs-lookup"><span data-stu-id="00af6-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00af6-104">Microsoft 团队管理中心已将 Skype for Business 管理中心替换 (旧版门户) 。</span><span class="sxs-lookup"><span data-stu-id="00af6-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="00af6-105">管理 Skype for Business 的所有设置现在均位于团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="00af6-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="00af6-106">若要了解详细信息，请参阅 [在 Microsoft 团队管理中心中管理 Skype For business 设置](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="00af6-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="00af6-107">默认情况下，可以使用 Skype for Business 与组织中的某个人进行通信的任何人都可以查看该人员是否处于联机状态。</span><span class="sxs-lookup"><span data-stu-id="00af6-107">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="00af6-108">Skype for business 显示人员是否可以在线、在会议、脱机或另一个指示器中使用。</span><span class="sxs-lookup"><span data-stu-id="00af6-108">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![Skype for Business 中人员的联机状态的示例。](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="00af6-110">作为企业中每个人的 **[管理员](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** ，您可以选择哪些人可以在 Skype for business 中看到其联机状态。</span><span class="sxs-lookup"><span data-stu-id="00af6-110">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="00af6-111">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="00af6-111">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="00af6-112">转到管理中心 > 管理中心 " **Admin centers**  >  **Skype for**business。</span><span class="sxs-lookup"><span data-stu-id="00af6-112">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="00af6-113">在 **Skype For business 管理中心**中，选择 " **组织**"。</span><span class="sxs-lookup"><span data-stu-id="00af6-113">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="00af6-114">在 " **状态隐私模式**" 下，选择下列设置之一，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="00af6-114">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="00af6-115">**设置**</span><span class="sxs-lookup"><span data-stu-id="00af6-115">**Setting**</span></span>|<span data-ttu-id="00af6-116">**谁可以查看用户的状态**</span><span class="sxs-lookup"><span data-stu-id="00af6-116">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00af6-117">**自动显示联机状态信息**</span><span class="sxs-lookup"><span data-stu-id="00af6-117">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="00af6-118">您的企业中尚未添加到其他人的 **外部** 或 **阻止** 列表的任何 Skype for business 用户都将能够看到该用户的联机状态。</span><span class="sxs-lookup"><span data-stu-id="00af6-118">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="00af6-119">**仅向用户的联系人显示状态信息**</span><span class="sxs-lookup"><span data-stu-id="00af6-119">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="00af6-120">用户联系人列表中未添加到其 **外部** 或 **阻止** 列表的任何人。</span><span class="sxs-lookup"><span data-stu-id="00af6-120">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="00af6-121">个人可在其 Skype for business 应用中替代默认设置： "**设置**  >  **工具**"  >  **选项**。</span><span class="sxs-lookup"><span data-stu-id="00af6-121">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="00af6-122">有关您的用户可以在 Skype for Business 中更改的内容的信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="00af6-122">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="00af6-123">在 Skype for Business 中控制对您的状态信息的访问</span><span class="sxs-lookup"><span data-stu-id="00af6-123">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="00af6-124">在 Skype for Business 中设置状态选项</span><span class="sxs-lookup"><span data-stu-id="00af6-124">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="00af6-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="00af6-125">Related topics</span></span>

[<span data-ttu-id="00af6-126">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="00af6-126">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="00af6-127">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="00af6-127">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


