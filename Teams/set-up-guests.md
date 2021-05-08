---
title: 开启或关闭对 Microsoft Teams 的来宾访问。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: 了解如何以管理员或管理员Microsoft Teams或Office 365来宾访问功能。
ms.openlocfilehash: 34759e601f5c0cd232bcd6227ff5c7d1fef1d3fe
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107398"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="acd8b-103">开启或关闭对 Microsoft Teams 的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="acd8b-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="acd8b-104">在 **2021 年 2** 月之前，来宾访问默认已关闭。</span><span class="sxs-lookup"><span data-stu-id="acd8b-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="acd8b-105">必须先为用户启用来宾Teams管理员或团队所有者才能添加来宾。</span><span class="sxs-lookup"><span data-stu-id="acd8b-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="acd8b-106">启用来宾访问后，更改可能需要几个小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="acd8b-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="acd8b-107">如果用户 **尝试将来宾** 添加到团队时看到消息"联系管理员"，则可能是来宾访问尚未打开或设置尚未生效。</span><span class="sxs-lookup"><span data-stu-id="acd8b-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> <span data-ttu-id="acd8b-108">**2021** 年 2 月之后，Microsoft Teams中尚未配置此设置的现有客户的&默认启用来宾访问。</span><span class="sxs-lookup"><span data-stu-id="acd8b-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="acd8b-109">实施此更改后，如果尚未在 Microsoft Teams 中配置来宾访问功能，将在租户中启用该功能。</span><span class="sxs-lookup"><span data-stu-id="acd8b-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="acd8b-110">如果希望组织的来宾访问保持禁用状态，则需要确认来宾访问设置设置为"关闭 **"，而不是**"服务 **默认"。**</span><span class="sxs-lookup"><span data-stu-id="acd8b-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acd8b-111">启用来宾访问取决于Azure Active Directory、Microsoft 365、SharePoint和Teams。</span><span class="sxs-lookup"><span data-stu-id="acd8b-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="acd8b-112">有关详细信息，请参阅 [在团队中与来宾协作](/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="acd8b-112">For more information, see [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="acd8b-113">在管理中心Teams来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="acd8b-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="acd8b-114">登录到管理[Microsoft Teams中心](https://admin.teams.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="acd8b-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="acd8b-115">选择 **"组织范围的设置**  >  **""来宾访问"。**</span><span class="sxs-lookup"><span data-stu-id="acd8b-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="acd8b-116">将 **"允许来宾访问"Microsoft Teams** 设置为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="acd8b-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="acd8b-117">"允许来宾访问"开关设置为"开"</span><span class="sxs-lookup"><span data-stu-id="acd8b-117">Allow guest access switch set to On</span></span> ](media/guest-access-setting.png)

4. <span data-ttu-id="acd8b-118">在 **"呼叫\*\*\*\*、会议**"和"**消息** 传送"下，选择每个功能"开"或"关"，具体取决于要允许来宾用户使用的功能。</span><span class="sxs-lookup"><span data-stu-id="acd8b-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="acd8b-119">**进行私人呼叫** - 将此设置 **设置为"打开** "，允许来宾进行对等呼叫。</span><span class="sxs-lookup"><span data-stu-id="acd8b-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="acd8b-120">**允许 IP 视频** - 启用 **此设置** ，允许来宾在通话和会议中使用视频。</span><span class="sxs-lookup"><span data-stu-id="acd8b-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="acd8b-121">**屏幕共享模式** - 此设置控制来宾用户屏幕共享的可用性。</span><span class="sxs-lookup"><span data-stu-id="acd8b-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="acd8b-122">将此设置设置为 **"已禁用**"，以删除来宾在 Teams 中共享其屏幕Teams。</span><span class="sxs-lookup"><span data-stu-id="acd8b-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="acd8b-123">将此设置设置为 **"单个应用程序** "，以允许共享单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="acd8b-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="acd8b-124">将此设置设置为 **"整个屏幕** "以允许完整的屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="acd8b-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="acd8b-125">**允许"现在** 开会"-**将此设置设置为"打开**"，以允许来宾使用"现在开会"功能Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="acd8b-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="acd8b-126">**编辑已发送的消息** - 将此设置 **设置为"打开** "以允许来宾编辑他们之前发送的消息。</span><span class="sxs-lookup"><span data-stu-id="acd8b-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="acd8b-127">**来宾可以删除已发送的消息** – 将此设置 **设置为"打开** "以允许来宾删除以前发送的消息。</span><span class="sxs-lookup"><span data-stu-id="acd8b-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="acd8b-128">**聊天**- 启用 **此设置，** 使来宾能够在聊天中Teams。</span><span class="sxs-lookup"><span data-stu-id="acd8b-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="acd8b-129">**在对话中使用 Giphy** -启用此设置以允许来宾在对话中使用 Giphy。</span><span class="sxs-lookup"><span data-stu-id="acd8b-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="acd8b-130">Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="acd8b-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="acd8b-131">每个 Giphy 都分配有一个内容分级。</span><span class="sxs-lookup"><span data-stu-id="acd8b-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="acd8b-132">**Giphy 内容分级** - 从下拉列表中选择分级：</span><span class="sxs-lookup"><span data-stu-id="acd8b-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="acd8b-133">**允许所有** 内容 - 来宾能够在聊天中插入所有 Giphy，而不考虑内容分级。</span><span class="sxs-lookup"><span data-stu-id="acd8b-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="acd8b-134">**中等** - 来宾能够在聊天中插入 Giphy，但会适度限制成人内容。</span><span class="sxs-lookup"><span data-stu-id="acd8b-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="acd8b-135">**严格** - 来宾可以在聊天中插入 Giphy，但无法插入成人内容。</span><span class="sxs-lookup"><span data-stu-id="acd8b-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="acd8b-136">**在对话中使用 Meme** -启用此设置以允许来宾在对话中使用 Meme。</span><span class="sxs-lookup"><span data-stu-id="acd8b-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="acd8b-137">**在对话中使用** 贴纸 - 启用此设置以允许来宾在对话中使用贴纸。</span><span class="sxs-lookup"><span data-stu-id="acd8b-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![来宾权限设置Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="acd8b-139">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="acd8b-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="acd8b-140">外部访问（联合身份验证）与来宾访问</span><span class="sxs-lookup"><span data-stu-id="acd8b-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="acd8b-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acd8b-141">See also</span></span>

[<span data-ttu-id="acd8b-142">与 Microsoft 365 建立安全协作</span><span class="sxs-lookup"><span data-stu-id="acd8b-142">Set up secure collaboration with Microsoft 365</span></span>](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="acd8b-143">阻止来自特定团队的来宾用户</span><span class="sxs-lookup"><span data-stu-id="acd8b-143">Block guest users from a specific team</span></span>](/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="acd8b-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="acd8b-144">Set-CsTeamsClientConfiguration</span></span>](/powershell/module/skype/set-csteamsclientconfiguration)