---
title: 管理会议设置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 了解如何管理的用户安排在组织中的团队会议设置。
ms.openlocfilehash: ec43fe9c436de612440bbec687868dc4de749191
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494247"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="0692e-103">在 Microsoft Teams 中管理会议设置</span><span class="sxs-lookup"><span data-stu-id="0692e-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="0692e-104">作为一名管理员，您使用团队会议设置来控制是否匿名用户可以加入团队会议和自定义会议邀请，如果您想要启用服务质量 (QoS) 设置的实时通信的端口范围。</span><span class="sxs-lookup"><span data-stu-id="0692e-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="0692e-105">这些设置应用于所有团队会议在组织中的用户日程安排。</span><span class="sxs-lookup"><span data-stu-id="0692e-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="0692e-106">**会议**管理这些设置 > Microsoft 团队管理中心中的**会议设置**。</span><span class="sxs-lookup"><span data-stu-id="0692e-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="0692e-107">允许匿名用户加入会议</span><span class="sxs-lookup"><span data-stu-id="0692e-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="0692e-108">匿名加入与任何人都可以作为加入会议匿名用户通过单击会议邀请中的链接。</span><span class="sxs-lookup"><span data-stu-id="0692e-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span>

<span data-ttu-id="0692e-109">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="0692e-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0692e-110">在左侧导航窗格中，转到**会议** > **会议设置**。</span><span class="sxs-lookup"><span data-stu-id="0692e-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="0692e-111">在**参与者**下启用**匿名用户可以加入会议**。</span><span class="sxs-lookup"><span data-stu-id="0692e-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="0692e-112">![会议-设置-participants.png](media/meeting-settings-participants.png "Microsoft 团队管理中心中的团队会议的参与者设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="0692e-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="0692e-113">如果您不希望匿名用户可以加入您的组织中的用户安排的会议，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="0692e-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="0692e-114">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="0692e-114">Customize meeting invitations</span></span>

<span data-ttu-id="0692e-115">您可以自定义团队会议邀请，以满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="0692e-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="0692e-116">您可以添加贵组织的徽标和包括有用的信息，如技术支持网站和法律免责声明和纯文本页脚的链接。</span><span class="sxs-lookup"><span data-stu-id="0692e-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="0692e-117">创建会议邀请的徽标的提示</span><span class="sxs-lookup"><span data-stu-id="0692e-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="0692e-118">创建不超过 188 像素宽 x 30 像素高 （它是非常小） 的图像。</span><span class="sxs-lookup"><span data-stu-id="0692e-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="0692e-119">将图像保存为 JPG 格式。</span><span class="sxs-lookup"><span data-stu-id="0692e-119">Save the image in JPG format.</span></span>
3. <span data-ttu-id="0692e-120">将图像存储在您的组织中的所有人都可以访问，如网络共享一个中心位置。</span><span class="sxs-lookup"><span data-stu-id="0692e-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="0692e-121">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="0692e-121">Customize your meeting invitations</span></span>

<span data-ttu-id="0692e-122">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="0692e-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0692e-123">在左侧导航窗格中，转到**会议** > **会议设置**。</span><span class="sxs-lookup"><span data-stu-id="0692e-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="0692e-124">在**电子邮件邀请**，下执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0692e-124">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="0692e-125">![会议-设置-invitation.png](media/meeting-settings-invitation.png "会议的屏幕截图可以自定义团队会议的邀请设置")</span><span class="sxs-lookup"><span data-stu-id="0692e-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="0692e-126">**徽标 URL**输入您的徽标的存储位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="0692e-126">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="0692e-127">**法律 URL**如果您的组织具有您想让用户转到的任何法律问题的法律网站，输入以下 URL。</span><span class="sxs-lookup"><span data-stu-id="0692e-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="0692e-128">**帮助 URL**如果您的组织具有您想让用户转到如果他们遇到问题的支持网站，，输入以下 URL。</span><span class="sxs-lookup"><span data-stu-id="0692e-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="0692e-129">**页脚**输入要作为页脚包含的文本。</span><span class="sxs-lookup"><span data-stu-id="0692e-129">**Footer** Enter text that you want to include as a footer.</span></span>
3. <span data-ttu-id="0692e-130">等待一小时或，更改将传播。</span><span class="sxs-lookup"><span data-stu-id="0692e-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="0692e-131">然后安排团队会议以查看会议邀请如下所示。</span><span class="sxs-lookup"><span data-stu-id="0692e-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="0692e-132">设置您希望如何处理团队会议的实时的媒体流量</span><span class="sxs-lookup"><span data-stu-id="0692e-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="0692e-133"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="0692e-133"></span></span>

<span data-ttu-id="0692e-134">如果您使用的服务质量[(QoS)](qos-in-teams.md)若要设置网络流量，可以启用 QoS 标记，并且您可以设置每种类型的媒体流量的端口范围。</span><span class="sxs-lookup"><span data-stu-id="0692e-134">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span>

 <span data-ttu-id="0692e-135">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="0692e-135">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0692e-136">在左侧导航窗格中，转到**会议** > **会议设置**。</span><span class="sxs-lookup"><span data-stu-id="0692e-136">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="0692e-137">在**网络**下执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0692e-137">Under **Network**, do the following:</span></span>

    <span data-ttu-id="0692e-138">![会议-设置-network.png](media/meeting-settings-network.png "团队会议的 Microsoft 团队管理中心中的网络设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="0692e-138">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="0692e-139">要允许 DSCP 标记，以用于 QoS，请打开**插入的服务质量 (QoS) 标记的实时的媒体流量**。</span><span class="sxs-lookup"><span data-stu-id="0692e-139">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="0692e-140">只有或不; 使用标记的选项不能设置为每种通信类型的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="0692e-140">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="0692e-141">更多有关 DSCP 标记，请参阅[选择 QoS 实现方法](QoS-in-Teams.md#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="0692e-141">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
    - <span data-ttu-id="0692e-142">若要指定端口范围，旁边**选择每种类型的实时的媒体流量的端口范围**，请选择**指定端口范围**，，然后输入音频、 视频和屏幕共享的起始和结束端口。</span><span class="sxs-lookup"><span data-stu-id="0692e-142">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="0692e-143">选择此选项需要实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="0692e-143">Selecting this option is required to implement QoS.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="0692e-144">如果您选择**自动使用任何可用的端口**，1024年之间可用的端口，并使用 65535。</span><span class="sxs-lookup"><span data-stu-id="0692e-144">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="0692e-145">仅当不实现 QoS，请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="0692e-145">Use this option only when not implementing QoS.</span></span>
    >
    > <span data-ttu-id="0692e-146">选择太窄的端口范围会导致丢弃的呼叫和质量欠佳的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="0692e-146">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="0692e-147">下面的建议应最低。</span><span class="sxs-lookup"><span data-stu-id="0692e-147">The recommendations below should be a bare minimum.</span></span>

 <span data-ttu-id="0692e-148">如果您不确定哪些端口范围，在您的环境中使用，以下设置都很好的起点。</span><span class="sxs-lookup"><span data-stu-id="0692e-148">If you are unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="0692e-149">若要了解详细信息，请阅读[实现的服务质量 (QoS) 中的 Microsoft 团队](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0692e-149">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="0692e-150">这些是必需的 DSCP 标记和建议的相应媒体端口范围团队和 ExpressRoute 使用。</span><span class="sxs-lookup"><span data-stu-id="0692e-150">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

<span data-ttu-id="0692e-151">_端口范围和 DSCP 标记_</span><span class="sxs-lookup"><span data-stu-id="0692e-151">_Port ranges and DSCP markings_</span></span>

<span data-ttu-id="0692e-152">媒体通信类型</span><span class="sxs-lookup"><span data-stu-id="0692e-152">Media traffic type</span></span>| <span data-ttu-id="0692e-153">客户端源端口范围\*</span><span class="sxs-lookup"><span data-stu-id="0692e-153">Client source port range \*</span></span> |<span data-ttu-id="0692e-154">协议</span><span class="sxs-lookup"><span data-stu-id="0692e-154">Protocol</span></span>|<span data-ttu-id="0692e-155">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="0692e-155">DSCP value</span></span>|<span data-ttu-id="0692e-156">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="0692e-156">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="0692e-157">音频</span><span class="sxs-lookup"><span data-stu-id="0692e-157">Audio</span></span>            | <span data-ttu-id="0692e-158">50000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="0692e-158">50,000–50,019</span></span>               |<span data-ttu-id="0692e-159">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="0692e-159">TCP/UDP</span></span> |<span data-ttu-id="0692e-160">46</span><span class="sxs-lookup"><span data-stu-id="0692e-160">46</span></span>        |<span data-ttu-id="0692e-161">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="0692e-161">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="0692e-162">视频</span><span class="sxs-lookup"><span data-stu-id="0692e-162">Video</span></span>            | <span data-ttu-id="0692e-163">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="0692e-163">50,020–50,039</span></span>               |<span data-ttu-id="0692e-164">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="0692e-164">TCP/UDP</span></span> |<span data-ttu-id="0692e-165">34</span><span class="sxs-lookup"><span data-stu-id="0692e-165">34</span></span>        |<span data-ttu-id="0692e-166">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="0692e-166">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="0692e-167">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="0692e-167">Application/Screen Sharing</span></span>| <span data-ttu-id="0692e-168">50,040 – 50,059</span><span class="sxs-lookup"><span data-stu-id="0692e-168">50,040–50,059</span></span>      |<span data-ttu-id="0692e-169">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="0692e-169">TCP/UDP</span></span> |<span data-ttu-id="0692e-170">18</span><span class="sxs-lookup"><span data-stu-id="0692e-170">18</span></span>        |<span data-ttu-id="0692e-171">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="0692e-171">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="0692e-172">\*分配的端口范围不能重叠，并且必须彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="0692e-172">\* The port ranges you assign can not overlap and must be adjacent to each other.</span></span>

<span data-ttu-id="0692e-173">设置不同的通信类型的端口范围中处理实时媒体只有一个步骤的更多详细信息，，请参阅[服务质量 (QoS) 中的团队](qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0692e-173">Setting port ranges for different traffic types is only one step in handling real time media, see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span> <span data-ttu-id="0692e-174">如果启用，或更改团队管理中心中的设置，您需要向[匹配将设置应用于所有用户设备](QoS-in-Teams-clients.md)和内部网络设备完全在工作组中实现对 QoS 的更改。</span><span class="sxs-lookup"><span data-stu-id="0692e-174">If you enable or change settings in Teams Admin Center, you will need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and internal network devices to fully implement the changes to QoS in Teams.</span></span>

<span data-ttu-id="0692e-175">QoS 一直在使用后的一段时间，您必须按每个这些三个工作负荷，需使用情况的信息和您可以选择要进行更改基于您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="0692e-175">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="0692e-176">[呼叫质量仪表板](turning-on-and-using-call-quality-dashboard.md)将有用的。</span><span class="sxs-lookup"><span data-stu-id="0692e-176">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>