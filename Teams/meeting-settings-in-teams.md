---
title: 在 Microsoft Teams 中管理会议设置
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
f1keywords: ms.teamsadmincenter.meetingsettings.overview
MS.collection: Teams_ITAdmin_Help
description: 了解如何管理的用户安排在组织中的团队会议设置。
ms.openlocfilehash: e4eba5f585f7621add95101d06194bebead507e2
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754414"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="ac3d6-103">在 Microsoft Teams 中管理会议设置</span><span class="sxs-lookup"><span data-stu-id="ac3d6-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="ac3d6-104">作为一名管理员，您使用团队会议设置来控制是否匿名用户可以加入团队会议和自定义会议邀请，如果您想要启用服务质量 (QoS) 设置的实时通信的端口。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set ports for real-time traffic.</span></span> <span data-ttu-id="ac3d6-105">这些设置应用于所有团队会议在组织中的用户日程安排。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="ac3d6-106">**会议**管理这些设置 > Microsoft 团队管理中心中的**会议设置**。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span> 

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="ac3d6-107">允许匿名用户加入会议</span><span class="sxs-lookup"><span data-stu-id="ac3d6-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="ac3d6-108">匿名加入与任何人都可以作为加入会议匿名用户通过单击会议邀请中的链接。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> 

<span data-ttu-id="ac3d6-109">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="ac3d6-109">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="ac3d6-110">在左侧导航窗格中，转到**会议** > **会议设置**。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="ac3d6-111">在**参与者**下启用**匿名用户可以加入会议**。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span> 

    <span data-ttu-id="ac3d6-112">![会议-设置-participants.png](media/meeting-settings-participants.png "Microsoft 团队管理中心中的团队会议的参与者设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="ac3d6-112">![meeting-settings-participants.png](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="ac3d6-113">如果您不希望匿名用户可以加入您的组织中的用户安排的会议，请关闭此设置。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span> 

## <a name="customize-meeting-invitations"></a><span data-ttu-id="ac3d6-114">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="ac3d6-114">Customize meeting invitations</span></span>

<span data-ttu-id="ac3d6-115">您可以自定义团队会议邀请，以满足您组织的需求。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="ac3d6-116">您可以添加贵组织的徽标和包括有用的信息，如技术支持网站和法律免责声明和纯文本页脚的链接。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span> 

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="ac3d6-117">创建会议邀请的徽标的提示</span><span class="sxs-lookup"><span data-stu-id="ac3d6-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="ac3d6-118">创建不超过 188 像素宽 x 30 像素高 （它是非常小） 的图像。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span> 
2. <span data-ttu-id="ac3d6-119">将图像保存为 JPG 格式。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-119">Save the image in JPG format.</span></span> 
3. <span data-ttu-id="ac3d6-120">将图像存储在您的组织中的所有人都可以访问，如网络共享一个中心位置。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span> 

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="ac3d6-121">自定义会议邀请</span><span class="sxs-lookup"><span data-stu-id="ac3d6-121">Customize your meeting invitations</span></span>

<span data-ttu-id="ac3d6-122">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="ac3d6-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ac3d6-123">在左侧导航窗格中，转到**会议** > **会议设置**。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-123">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="ac3d6-124">在**电子邮件邀请**，下执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ac3d6-124">Under **Email invitation**, do the following:</span></span> 

    <span data-ttu-id="ac3d6-125">![会议-设置-invitation.png](media/meeting-settings-invitation.png "会议的屏幕截图可以自定义团队会议的邀请设置")</span><span class="sxs-lookup"><span data-stu-id="ac3d6-125">![meeting-settings-invitation.png](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span> 

    - <span data-ttu-id="ac3d6-126">**徽标 URL**输入您的徽标的存储位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-126">**Logo URL** Enter the URL where your logo is stored.</span></span> 
    - <span data-ttu-id="ac3d6-127">**法律 URL**如果您的组织具有您想让用户转到的任何法律问题的法律网站，输入以下 URL。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-127">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span> 
    - <span data-ttu-id="ac3d6-128">**帮助 URL**如果您的组织具有您想让用户转到如果他们遇到问题的支持网站，，输入以下 URL。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-128">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="ac3d6-129">**页脚**输入要作为页脚包含的文本。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-129">**Footer** Enter text that you want to include as a footer.</span></span> 
3. <span data-ttu-id="ac3d6-130">等待一小时或，更改将传播。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-130">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="ac3d6-131">然后安排团队会议以查看会议邀请如下所示。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-131">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="ac3d6-132">设置您希望如何处理团队会议的实时的媒体流量</span><span class="sxs-lookup"><span data-stu-id="ac3d6-132">Set how you want to handle real-time media traffic for Teams meetings</span></span>
<span data-ttu-id="ac3d6-133">如果您使用的服务质量 (QoS) 若要设置网络流量，可以启用 QoS 标记，并且您可以设置每种类型的媒体流量的端口范围。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-133">If you're using Quality of Service (QoS) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span> 

 <span data-ttu-id="ac3d6-134">![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**</span><span class="sxs-lookup"><span data-stu-id="ac3d6-134">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ac3d6-135">在左侧导航窗格中，转到**会议** > **会议设置**。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-135">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span> 
2. <span data-ttu-id="ac3d6-136">在**网络**下执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ac3d6-136">Under **Network**, do the following:</span></span>

    <span data-ttu-id="ac3d6-137">![会议-设置-network.png](media/meeting-settings-network.png "团队会议的 Microsoft 团队管理中心中的网络设置的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="ac3d6-137">![meeting-settings-network.png](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="ac3d6-138">若要启用 QoS 标记，打开**插入的服务质量 (QoS) 标记的实时的媒体流量**。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-138">To enable QoS markers, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span>
    - <span data-ttu-id="ac3d6-139">若要指定端口范围，旁边**选择每种类型的实时的媒体流量的端口范围**，请选择**指定端口范围**，，然后输入音频、 视频和屏幕共享的起始和结束端口。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-139">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> 
    
        <span data-ttu-id="ac3d6-140">如果您选择**自动使用任何可用的端口**，1024年之间可用的端口，并使用 65535。</span><span class="sxs-lookup"><span data-stu-id="ac3d6-140">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> 

 ### <a name="related-topics"></a><span data-ttu-id="ac3d6-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="ac3d6-141">Related topics</span></span>
- [<span data-ttu-id="ac3d6-142">服务质量 (QoS 中的团队)</span><span class="sxs-lookup"><span data-stu-id="ac3d6-142">Quality of Service (QoS) in Teams</span></span>](qos-in-teams.md)

