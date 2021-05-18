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
description: '了解如何设置Skype for Business，以便查看同事是否有空。 '
ms.openlocfilehash: 5eec57f295dbb45649fea6590147798881297a1b
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239962"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="48a16-103">在 Skype for Business Online 中配置状态</span><span class="sxs-lookup"><span data-stu-id="48a16-103">Configure presence in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="48a16-104">Microsoft Teams管理中心已Skype for Business旧版门户 (管理) 。</span><span class="sxs-lookup"><span data-stu-id="48a16-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="48a16-105">现在，管理Skype for Business的所有设置都位于Teams中心。</span><span class="sxs-lookup"><span data-stu-id="48a16-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="48a16-106">必须分配全局管理员或 Skype for Business 管理员的[Azure AD](/azure/active-directory/roles/permissions-reference)管理员角色Skype for Business管理中心Teams功能。</span><span class="sxs-lookup"><span data-stu-id="48a16-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="48a16-107">有关详细信息，请参阅[在 Microsoft Teams 管理中心中管理 Skype for Business 设置](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="48a16-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="48a16-108">默认情况下，可以使用"联机"功能与组织中使用 Skype for Business之一通信的任何人也可以查看此人是否在线。</span><span class="sxs-lookup"><span data-stu-id="48a16-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="48a16-109">Skype for Business显示人员是在线、在会议、脱机还是其他指示器中可用。</span><span class="sxs-lookup"><span data-stu-id="48a16-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![用户在线状态的示例Skype for Business。](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="48a16-111">作为 **[企业](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 中的所有人的管理员，你可以选择谁在公司内看到其在线Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="48a16-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="48a16-112">![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**</span><span class="sxs-lookup"><span data-stu-id="48a16-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="48a16-113">转到管理中心>**管理Skype for Business。**  >  </span><span class="sxs-lookup"><span data-stu-id="48a16-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="48a16-114">在 **"Skype for Business管理中心"中**，选择"组织 **"。**</span><span class="sxs-lookup"><span data-stu-id="48a16-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="48a16-115">在 **"状态隐私模式**"下，选择以下设置之一，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="48a16-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="48a16-116">**设置**</span><span class="sxs-lookup"><span data-stu-id="48a16-116">**Setting**</span></span>|<span data-ttu-id="48a16-117">**Who可以查看用户状态**</span><span class="sxs-lookup"><span data-stu-id="48a16-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48a16-118">**自动显示联机状态信息**</span><span class="sxs-lookup"><span data-stu-id="48a16-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="48a16-119">任何Skype for Business未添加到用户的"外部"或"阻止"列表的用户都将能够看到该用户的在线状态。 </span><span class="sxs-lookup"><span data-stu-id="48a16-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="48a16-120">**仅向用户的联系人显示状态信息**</span><span class="sxs-lookup"><span data-stu-id="48a16-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="48a16-121">联系人联系人列表中尚未添加到其外部或阻止列表中的 **任何人**。 </span><span class="sxs-lookup"><span data-stu-id="48a16-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="48a16-122">个人可以在他们的应用内覆盖你的默认设置 **Skype for Business：设置**  >  **工具**  >  **选项"。**</span><span class="sxs-lookup"><span data-stu-id="48a16-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="48a16-123">有关用户可以在应用内更改哪些Skype for Business，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="48a16-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="48a16-124">控制在 Skype for Business 中访问您的状态Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48a16-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="48a16-125">在"设置状态"选项Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48a16-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="48a16-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="48a16-126">Related topics</span></span>

[<span data-ttu-id="48a16-127">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="48a16-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="48a16-128">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="48a16-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
