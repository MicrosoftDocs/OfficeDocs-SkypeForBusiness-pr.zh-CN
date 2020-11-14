---
title: 打开或关闭对 Microsoft 团队的来宾访问
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
description: 了解如何在 Microsoft 团队中打开或关闭来宾访问功能，作为 Office 365 管理员。
ms.openlocfilehash: 0920e9d8b8184f7f7ca83a71f0bd97d3a4d78470
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031188"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="66142-103">打开或关闭对 Microsoft 团队的来宾访问</span><span class="sxs-lookup"><span data-stu-id="66142-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="66142-104">默认情况下会关闭来宾访问。</span><span class="sxs-lookup"><span data-stu-id="66142-104">By default, guest access is turned off.</span></span> <span data-ttu-id="66142-105">必须先为团队启用来宾访问权限，管理员或团队所有者才能添加来宾。</span><span class="sxs-lookup"><span data-stu-id="66142-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="66142-106">启用来宾访问后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="66142-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="66142-107">如果用户尝试向其团队中添加来宾时看到消息 "请联系你的管理员"，则很可能是来宾访问尚未打开，或者设置尚未生效。</span><span class="sxs-lookup"><span data-stu-id="66142-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66142-108">启用来宾访问取决于 Azure Active Directory、Microsoft 365、SharePoint 和团队中的设置。</span><span class="sxs-lookup"><span data-stu-id="66142-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="66142-109">有关详细信息，请参阅 [与团队中的来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="66142-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="66142-110">配置团队管理中心中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="66142-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="66142-111">登录到 [Microsoft 团队管理中心](https://admin.teams.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="66142-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="66142-112">选择 " **组织范围设置** "  >  **来宾访问** 。</span><span class="sxs-lookup"><span data-stu-id="66142-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="66142-113">将 " **允许 Microsoft 团队中的来宾访问** " 设置为 **"打开"** 。</span><span class="sxs-lookup"><span data-stu-id="66142-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="66142-114">允许来宾访问开关设置为 "开"</span><span class="sxs-lookup"><span data-stu-id="66142-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="66142-115">在 " **呼叫** 、 **会议** 和 **消息** " 下，为每个功能选择 **"开" 或 "** **关** "，具体取决于您希望来宾用户允许的功能。</span><span class="sxs-lookup"><span data-stu-id="66142-115">Under **Calling** , **Meeting** , and **Messaging** , select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="66142-116">**进行专用通话** –打开此设置可允许来宾 **进行对等** 呼叫。</span><span class="sxs-lookup"><span data-stu-id="66142-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="66142-117">**允许使用 IP 视频** -打开此 **设置可允许来宾在其** 呼叫和会议中使用视频。</span><span class="sxs-lookup"><span data-stu-id="66142-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="66142-118">**屏幕共享模式** -此设置控制来宾用户的屏幕共享的可用性。</span><span class="sxs-lookup"><span data-stu-id="66142-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="66142-119">将此设置启用为 " **已禁用** "，以删除来宾在团队中共享其屏幕的功能。</span><span class="sxs-lookup"><span data-stu-id="66142-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="66142-120">将此设置转换为 " **单应用程序** " 以允许共享单个应用程序。</span><span class="sxs-lookup"><span data-stu-id="66142-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="66142-121">将此设置转换为 **整个屏幕** ，以允许完成屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="66142-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="66142-122">**允许立即开会** –打开 **此设置可允许来宾在 Microsoft** 团队中使用 "立即开会" 功能。</span><span class="sxs-lookup"><span data-stu-id="66142-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="66142-123">**编辑已发送的邮件** -打开 **此设置可** 允许来宾编辑以前发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="66142-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="66142-124">**来宾可以删除已发送的邮件** -打开 **此设置可** 允许来宾删除以前发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="66142-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="66142-125">**聊天** -启用 **此设置，让来宾能够在** 团队中使用聊天功能。</span><span class="sxs-lookup"><span data-stu-id="66142-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="66142-126">**在对话中使用 giphy** -打开此 **设置可允许来宾在对话** 中使用 giphy。</span><span class="sxs-lookup"><span data-stu-id="66142-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="66142-127">Giphy 是一个联机数据库和搜索引擎，允许用户搜索和共享动态 GIF 文件。</span><span class="sxs-lookup"><span data-stu-id="66142-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="66142-128">每个 Giphy 都分配有一个内容分级。</span><span class="sxs-lookup"><span data-stu-id="66142-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="66142-129">**Giphy 内容分级** -从下拉列表中选择分级：</span><span class="sxs-lookup"><span data-stu-id="66142-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="66142-130">**允许所有内容** -无论内容分级如何，来宾都能够插入聊天中的所有 giphy。</span><span class="sxs-lookup"><span data-stu-id="66142-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="66142-131">" **中等** "-来宾将能够在聊天中插入 giphy，但将按成人内容适度限制。</span><span class="sxs-lookup"><span data-stu-id="66142-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="66142-132">**严格** -来宾将能够在聊天中插入 giphy，但将受到限制，无法插入成人内容。</span><span class="sxs-lookup"><span data-stu-id="66142-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="66142-133">**在对话中使用 meme** -打开此 **设置可允许来宾在对话** 中使用 meme。</span><span class="sxs-lookup"><span data-stu-id="66142-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="66142-134">**在对话中使用贴纸** -启用 **此设置可允许来宾在对话** 中使用贴纸。</span><span class="sxs-lookup"><span data-stu-id="66142-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![团队中的来宾权限设置](media/manage-guest-access-image1.png)

5. <span data-ttu-id="66142-136">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="66142-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="66142-137">外部访问（联合身份验证）与来宾访问</span><span class="sxs-lookup"><span data-stu-id="66142-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="66142-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66142-138">See also</span></span>

[<span data-ttu-id="66142-139">与 Microsoft 365 建立安全协作</span><span class="sxs-lookup"><span data-stu-id="66142-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="66142-140">阻止来自特定团队的来宾用户</span><span class="sxs-lookup"><span data-stu-id="66142-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="66142-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="66142-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
