---
title: Lync Server 2013：面向客户端的新内容
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f938ccc4e4a040307a7cf86a8084353c480cfdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="6e19d-102">Lync Server 2013 中面向客户端的新内容</span><span class="sxs-lookup"><span data-stu-id="6e19d-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e19d-103">_**主题上次修改时间：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="6e19d-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="6e19d-104">Microsoft Lync 2013 具有重新设计的用户界面和重要的新功能。</span><span class="sxs-lookup"><span data-stu-id="6e19d-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="6e19d-105">对于管理员，客户端现已包含在 Office 安装程序中，可提供更简单的方法来部署 Office 和自定义组织中的客户端。</span><span class="sxs-lookup"><span data-stu-id="6e19d-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e19d-106">有关 Lync 2013 用户界面更新的图解视图，请参阅 "Lync 2013 中的新增功能" <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>。</span><span class="sxs-lookup"><span data-stu-id="6e19d-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="6e19d-107">与 Office 安装程序集成</span><span class="sxs-lookup"><span data-stu-id="6e19d-107">Integration with Office Setup</span></span>

<span data-ttu-id="6e19d-108">Lync 2013 客户端和适用于 Lync 2013 的联机会议加载项（它支持来自 Outlook 消息传递和协作客户端的会议管理）现在都包含在 Office 2013 设置程序中。</span><span class="sxs-lookup"><span data-stu-id="6e19d-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="6e19d-109">在早期版本的 Lync 和 Office Communicator 中，你可以使用 Windows Installer 属性自定义和控制 Office 安装。</span><span class="sxs-lookup"><span data-stu-id="6e19d-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="6e19d-110">由于 Lync 2013 与 Office 安装程序集成，因此您可以使用以下方法自定义 Lync 2013 设置：</span><span class="sxs-lookup"><span data-stu-id="6e19d-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="6e19d-111">使用 Office 自定义工具 (OCT)</span><span class="sxs-lookup"><span data-stu-id="6e19d-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="6e19d-112">使用 Config.xml 执行安装任务</span><span class="sxs-lookup"><span data-stu-id="6e19d-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="6e19d-113">使用设置命令行选项</span><span class="sxs-lookup"><span data-stu-id="6e19d-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e19d-114">Lync 2013 安装程序不会卸载以前版本的 Lync 或 Office Communicator。</span><span class="sxs-lookup"><span data-stu-id="6e19d-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="6e19d-115">Lync 2013 客户端与其他 Lync 或 Office Communicator 客户端并行安装</span><span class="sxs-lookup"><span data-stu-id="6e19d-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="6e19d-116">有关详细信息，请参阅[在 Lync Server 2013 中部署 Lync 客户端](lync-server-2013-deploying-lync-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="6e19d-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="6e19d-117">组策略部署</span><span class="sxs-lookup"><span data-stu-id="6e19d-117">Group Policy Deployment</span></span>

<span data-ttu-id="6e19d-118">由于 Lync 2013 现已包含在 Office 安装程序中，因此用于部署 Lync 组策略设置的方法已更改。</span><span class="sxs-lookup"><span data-stu-id="6e19d-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="6e19d-119">在早期版本的 Lync 和 Office Communicator 中，你可以使用 Communicator 定义组策略设置，而在 Lync 2013 中，你现在可以使用与 Office 组策略一起提供的 Lync ADMX 和 ADML 管理模板管理模板。</span><span class="sxs-lookup"><span data-stu-id="6e19d-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="6e19d-120">有关详细信息，请参阅[Lync 2013 的组策略设置](lync-server-2013-group-policy-settings-for-lync-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="6e19d-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="6e19d-121">Outlook 计划外接程序更新</span><span class="sxs-lookup"><span data-stu-id="6e19d-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="6e19d-122">Lync 2013 的联机会议加载项包括 "会议邀请自定义" 和 "新建会议" 选项。</span><span class="sxs-lookup"><span data-stu-id="6e19d-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="6e19d-123">管理员可以通过添加自定义徽标、支持 URL、合法免责声明 URL 或自定义页脚文本来自定义组织的会议邀请。</span><span class="sxs-lookup"><span data-stu-id="6e19d-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="6e19d-124">有关详细信息，请参阅[在 Lync Server 2013 中自定义联机会议加载项](lync-server-2013-customizing-the-online-meeting-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="6e19d-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="6e19d-125">新与会者静音控件允许会议组织者安排在默认情况下将与会者音频和视频设为静音的会议。</span><span class="sxs-lookup"><span data-stu-id="6e19d-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="6e19d-126">虚拟桌面基础结构插件</span><span class="sxs-lookup"><span data-stu-id="6e19d-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="6e19d-127">Lync 2013 客户端现在支持虚拟桌面基础结构（VDI）环境中的音频和视频。</span><span class="sxs-lookup"><span data-stu-id="6e19d-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="6e19d-128">用户可以将音频或视频设备（例如，耳机或相机）连接到本地计算机（例如，瘦客户端或重新使用用途的计算机）。</span><span class="sxs-lookup"><span data-stu-id="6e19d-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="6e19d-129">用户可以连接到虚拟机，登录到在虚拟机上运行的 Lync 2013 客户端，并参与实时音频和视频通信，就像客户端在本地运行一样。</span><span class="sxs-lookup"><span data-stu-id="6e19d-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="6e19d-130">虚拟桌面环境支持以下功能：</span><span class="sxs-lookup"><span data-stu-id="6e19d-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="6e19d-131">音频和视频设备集成，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="6e19d-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="6e19d-132">从设备调用控件</span><span class="sxs-lookup"><span data-stu-id="6e19d-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="6e19d-133">设备上的联机状态集成</span><span class="sxs-lookup"><span data-stu-id="6e19d-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="6e19d-134">多个 HID （人体学接口设备）支持</span><span class="sxs-lookup"><span data-stu-id="6e19d-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="6e19d-135">位置和紧急服务支持。</span><span class="sxs-lookup"><span data-stu-id="6e19d-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="6e19d-136">支持所有 Lync 形式，包括即时消息、音频、视频、应用程序共享、桌面共享、PowerPoint 共享、白板和文件传输。</span><span class="sxs-lookup"><span data-stu-id="6e19d-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="6e19d-137">在联系人通话和电话会议中进行音频和视频支持。</span><span class="sxs-lookup"><span data-stu-id="6e19d-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="6e19d-138">有关部署 VDI 插件的信息，请参阅[在 Lync Server 2013 中部署 LYNC VDI 插件](lync-server-2013-deploying-the-lync-vdi-plug-in.md)。</span><span class="sxs-lookup"><span data-stu-id="6e19d-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="6e19d-139">视频增强</span><span class="sxs-lookup"><span data-stu-id="6e19d-139">Video Enhancements</span></span>

<span data-ttu-id="6e19d-140">许多新功能显著增强了会议参与者的视频体验。</span><span class="sxs-lookup"><span data-stu-id="6e19d-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="6e19d-141">视频通过 "面孔检测" 和 "智能框架" 进行了增强，以便参与者的视频可以在框架中移动以帮助保持其居中。</span><span class="sxs-lookup"><span data-stu-id="6e19d-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="6e19d-142">现在，在两方呼叫和多方会议中支持高清晰度视频。</span><span class="sxs-lookup"><span data-stu-id="6e19d-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="6e19d-143">用户可以体验高达 HD 1080P 的分辨率。</span><span class="sxs-lookup"><span data-stu-id="6e19d-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="6e19d-144">参与者可以从不同的会议版式中进行选择：库视图显示所有参与者的图片或视频;"演讲者" 视图显示会议内容，并且仅显示当前演讲者的视频或图片;演示文稿视图仅显示会议内容;紧凑视图仅显示会议控件。</span><span class="sxs-lookup"><span data-stu-id="6e19d-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="6e19d-145">利用新的库功能，参与者可以同时查看多个视频源。</span><span class="sxs-lookup"><span data-stu-id="6e19d-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="6e19d-146">如果会议具有超过五个参与者，则只有最活跃参与者的视频源显示在顶部行中，并且为其他参与者显示图片。</span><span class="sxs-lookup"><span data-stu-id="6e19d-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="6e19d-147">参与者可以使用视频固定来选择一个或多个可用视频源，以便在任何时候都可见。</span><span class="sxs-lookup"><span data-stu-id="6e19d-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="6e19d-148">演示者可以使用视频聚焦功能选择一个人的视频源，以便会议中的每个参与者仅看到该参与者。</span><span class="sxs-lookup"><span data-stu-id="6e19d-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="6e19d-149">聊天室集成</span><span class="sxs-lookup"><span data-stu-id="6e19d-149">Chat Room Integration</span></span>

<span data-ttu-id="6e19d-150">现在，lync 2013 集成了 Lync 2010 群组聊天以前提供的功能。</span><span class="sxs-lookup"><span data-stu-id="6e19d-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="6e19d-151">不再需要单独的群组聊天客户端。</span><span class="sxs-lookup"><span data-stu-id="6e19d-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="6e19d-152">在 Lync 2013 中，用户可以搜索聊天室、向其联系人添加聊天室、监视聊天室活动以及阅读和发布消息。</span><span class="sxs-lookup"><span data-stu-id="6e19d-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="6e19d-153">用户可以创建主题源，以便在其中一个聊天室中的某人添加包含特定关键字的帖子时收到通知。</span><span class="sxs-lookup"><span data-stu-id="6e19d-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="6e19d-154">使用新的**持久聊天**选项页面，用户可以设置在用户向其聊天室发布消息时应用的通知通知和声音。</span><span class="sxs-lookup"><span data-stu-id="6e19d-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="6e19d-155">Lync Web App 更新</span><span class="sxs-lookup"><span data-stu-id="6e19d-155">Lync Web App Updates</span></span>

<span data-ttu-id="6e19d-156">Lync Web App 是适用于 Lync Server 2013 会议的基于 Web 的会议客户端。</span><span class="sxs-lookup"><span data-stu-id="6e19d-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="6e19d-157">在此版本中，向 Lync Web App 添加计算机音频和视频可为没有本地安装 Lync 客户端的任何人提供完整的会议体验。</span><span class="sxs-lookup"><span data-stu-id="6e19d-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="6e19d-158">会议参与者可访问所有协作和共享功能以及演示者会议控件。</span><span class="sxs-lookup"><span data-stu-id="6e19d-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="6e19d-159">当用户尝试加入会议，但没有本地安装的客户端时，将打开 Lync Web App。</span><span class="sxs-lookup"><span data-stu-id="6e19d-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="6e19d-160">如果想要允许其他选项加入会议，可以配置会议加入页面;请参阅在部署文档中的[Lync Server 2013 中配置会议加入页面](lync-server-2013-configuring-the-meeting-join-page.md)。</span><span class="sxs-lookup"><span data-stu-id="6e19d-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="6e19d-161">由于 Lync Web App 的增强功能，"更新版本的与会者" 在 Lync Server 2013 中不可用。</span><span class="sxs-lookup"><span data-stu-id="6e19d-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="6e19d-162">Lync Web App 是您的组织外部参与者选择的客户。</span><span class="sxs-lookup"><span data-stu-id="6e19d-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="6e19d-163">不需要本地客户端安装，尽管音频、视频和共享功能需要插件在首次使用时安装。</span><span class="sxs-lookup"><span data-stu-id="6e19d-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="6e19d-164">适用于移动客户端更新的 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6e19d-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="6e19d-165">除了增强的状态、联系人和即时消息功能，Lync 2013 移动客户现在还通过 Internet 和手机网络数据连接提供语音和视频通话。</span><span class="sxs-lookup"><span data-stu-id="6e19d-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="6e19d-166">通过点击 "日历" 项目中的会议链接，移动用户可以加入 Lync 语音和视频会议。</span><span class="sxs-lookup"><span data-stu-id="6e19d-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="6e19d-167">有关 Lync 2013 移动客户端的详细信息，请参阅[在 Lync Server 2013 中规划移动客户端](lync-server-2013-planning-for-mobile-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="6e19d-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="6e19d-168">Lync 2013 用户界面更新</span><span class="sxs-lookup"><span data-stu-id="6e19d-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="6e19d-169">辅助功能更新</span><span class="sxs-lookup"><span data-stu-id="6e19d-169">Accessibility Updates</span></span>

<span data-ttu-id="6e19d-170">Lync 2013 包含几个新的辅助功能。</span><span class="sxs-lookup"><span data-stu-id="6e19d-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="6e19d-171">Lync 2013 支持高 DPI 分辨率，从而使用户能够针对125% 和150% 点/英寸缩放文本和图形。</span><span class="sxs-lookup"><span data-stu-id="6e19d-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="6e19d-172">Lync 提供高对比度支持，以便在 Windows 中与高对比度主题配合使用时，用户界面保持完全正常工作。</span><span class="sxs-lookup"><span data-stu-id="6e19d-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="6e19d-173">Lync 提供了100多个键盘快捷方式，以便用户无需鼠标即可访问重要的功能。</span><span class="sxs-lookup"><span data-stu-id="6e19d-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="6e19d-174">例如，用户可以按 Alt + C 接受呼叫，或按 Alt + I 忽略它，而无需 tab 或设置焦点。</span><span class="sxs-lookup"><span data-stu-id="6e19d-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="6e19d-175">按下（Alt + Q）结束呼叫（Ctrl + N）启动 OneNote，（Alt + T）将打开 "工具" 菜单。</span><span class="sxs-lookup"><span data-stu-id="6e19d-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="6e19d-176">Lync 2013 中的扩展屏幕阅读器支持可确保在启用屏幕阅读器时高声阅读所有通知、传入的请求和即时消息。</span><span class="sxs-lookup"><span data-stu-id="6e19d-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="6e19d-177">共享时的状态</span><span class="sxs-lookup"><span data-stu-id="6e19d-177">Presence While Sharing</span></span>

<span data-ttu-id="6e19d-178">当 Lync 检测到用户正在共享时，Lync 会自动为用户分配演示状态。</span><span class="sxs-lookup"><span data-stu-id="6e19d-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="6e19d-179">除非向发件人分配了工作组私人关系，否则此状态将阻止所有传入通信。</span><span class="sxs-lookup"><span data-stu-id="6e19d-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="6e19d-180">如果用户完全在辅助监视器上使用共享功能，则 Lync 不会分配演示状态。</span><span class="sxs-lookup"><span data-stu-id="6e19d-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="6e19d-181">对话窗口更新</span><span class="sxs-lookup"><span data-stu-id="6e19d-181">Conversation Window Updates</span></span>

<span data-ttu-id="6e19d-182">重新设计的对话窗口可更快地访问重要功能。</span><span class="sxs-lookup"><span data-stu-id="6e19d-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="6e19d-183">通过新的选项卡式对话功能，用户现在可以在一个对话窗口中保留其所有 Im 和聊天室。</span><span class="sxs-lookup"><span data-stu-id="6e19d-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="6e19d-184">沿对话窗口左侧的选项卡使用户可以轻松地在所有活动对话中导航。</span><span class="sxs-lookup"><span data-stu-id="6e19d-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="6e19d-185">用户可以将单个对话弹出到单独的窗口中，然后调整窗口大小。</span><span class="sxs-lookup"><span data-stu-id="6e19d-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="6e19d-186">他们还可以将窗口弹出回到主对话窗口中。</span><span class="sxs-lookup"><span data-stu-id="6e19d-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="6e19d-187">当用户注销并重新登录到 Lync 时，Lync 2013 将重新打开用户的对话。</span><span class="sxs-lookup"><span data-stu-id="6e19d-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="6e19d-188">用户可以向任何对话快速添加即时消息、视频、程序共享、桌面共享或 web 会议工具（白板、会议笔记、共享的笔记本和附件）。</span><span class="sxs-lookup"><span data-stu-id="6e19d-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="6e19d-189">在正在共享视频或内容的会议中，用户可以弹出会议视频或共享内容，然后调整窗口大小。</span><span class="sxs-lookup"><span data-stu-id="6e19d-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="6e19d-190">Lync 主窗口更新</span><span class="sxs-lookup"><span data-stu-id="6e19d-190">Lync Main Window Updates</span></span>

<span data-ttu-id="6e19d-191">新的精简外观保留了熟悉的功能，如**今天所发生的情况？** 备注域、状态选择器和 "**设置您的位置**选择器"。</span><span class="sxs-lookup"><span data-stu-id="6e19d-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="6e19d-192">启用聊天室时，用户可在主 Lync 页面上看到新的**聊天室**图标。</span><span class="sxs-lookup"><span data-stu-id="6e19d-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="6e19d-193">使用聊天室**图标，** 用户可以快速访问其聊天室和筛选器。</span><span class="sxs-lookup"><span data-stu-id="6e19d-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="6e19d-194">用户可以单击 "视图" 图标切换到 "**联系人**" 视图、"**聊天室**" 视图、"**对话**" 视图或 "**电话**" 视图。</span><span class="sxs-lookup"><span data-stu-id="6e19d-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="6e19d-195">如果用户已迁移到 Exchange 2013，他们可以上载高分辨率的图片。</span><span class="sxs-lookup"><span data-stu-id="6e19d-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="6e19d-196">联系人视图和联系人卡片更新</span><span class="sxs-lookup"><span data-stu-id="6e19d-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="6e19d-197">Lync 2013 为用户提供了在其 "**联系人**" 视图中查看联系人和组的不同方式。</span><span class="sxs-lookup"><span data-stu-id="6e19d-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="6e19d-198">使用新的统一联系人存储，将用户的 Lync 联系人迁移到 Exchange 2013 之后，用户可以从 Lync 2013、Outlook 或 Outlook Web App 访问和管理其联系人，其收藏夹保持同步。</span><span class="sxs-lookup"><span data-stu-id="6e19d-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="6e19d-199">例如，如果用户将联系人添加到 Outlook 中的 "收藏夹"，则该联系人将显示在 Lync 2013 的 "收藏夹" 组中。</span><span class="sxs-lookup"><span data-stu-id="6e19d-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="6e19d-200">如果你已添加并配置 XMPP 代理和 XMPP 网关，则用户可以添加来自基于 XMPP 的合作伙伴的联系人，以便发送即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="6e19d-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="6e19d-201">新的 **"添加不在我的组织中的联系人"** 功能为用户提供了一种添加组织外部人员的简便方法。</span><span class="sxs-lookup"><span data-stu-id="6e19d-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="6e19d-202">新的 **"常用联系人"** 组让用户可以构建用户最常联系的人员列表，以便快速访问。</span><span class="sxs-lookup"><span data-stu-id="6e19d-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="6e19d-203">用户可以使用新的 "**联系人列表**" 选项页来选择用户希望如何排序和显示联系人。</span><span class="sxs-lookup"><span data-stu-id="6e19d-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="6e19d-204">用户可以选择一个展开的两行视图，显示联系人的图片或简洁的单行视图。</span><span class="sxs-lookup"><span data-stu-id="6e19d-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="6e19d-205">用户还可以按字母顺序或按可用性对联系人进行排序。</span><span class="sxs-lookup"><span data-stu-id="6e19d-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="6e19d-206">会议更新</span><span class="sxs-lookup"><span data-stu-id="6e19d-206">Conferencing Updates</span></span>

<span data-ttu-id="6e19d-207">Lync 2013 提供了多项会议功能增强功能。</span><span class="sxs-lookup"><span data-stu-id="6e19d-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="6e19d-208">根据会议的类型，用户现在可以将观众设为静音，并在安排会议时允许或阻止视频共享。</span><span class="sxs-lookup"><span data-stu-id="6e19d-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="6e19d-209">"**会议选项**" 页面上提供了这些选项，建议使用超过20个参与者的大型会议。</span><span class="sxs-lookup"><span data-stu-id="6e19d-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="6e19d-210">在会议室中轻松使用音频控件允许用户控制音频选项，如静音、取消静音、更改设备等。</span><span class="sxs-lookup"><span data-stu-id="6e19d-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="6e19d-211">当共享程序时，如果需要使用多个程序，用户可以选择多个要共享的程序。</span><span class="sxs-lookup"><span data-stu-id="6e19d-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="6e19d-212">用户现在可以上载 PowerPoint 文件，并将鼠标指针悬停在幻灯片上以显示视频控件（如播放、暂停和音频控件），从而上载包含视频剪辑的演示文稿。</span><span class="sxs-lookup"><span data-stu-id="6e19d-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="6e19d-213">在会议中，用户可以通过将**此呼叫合并到**"**更多选项**" （**...**）菜单中，将另一个打开的对话合并到会议中。</span><span class="sxs-lookup"><span data-stu-id="6e19d-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="6e19d-214">若要查看参与者的姓名，用户可以将鼠标悬停在 "**视图参与者**" 按钮上，或单击 "**显示参与者列表**" 以在会议中停靠面板。</span><span class="sxs-lookup"><span data-stu-id="6e19d-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="6e19d-215">用户可以从多个不同的内容和参与者视图中进行选择，具体取决于会议类型。</span><span class="sxs-lookup"><span data-stu-id="6e19d-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="6e19d-216">会议录制将自动保存为在 Windows Media Player （工作表示）中播放的格式。</span><span class="sxs-lookup"><span data-stu-id="6e19d-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="6e19d-217">用户可以轻松地与任何人共享文件，或使用录制管理器中的 "**发布**" 功能将录制内容发布到共享位置。</span><span class="sxs-lookup"><span data-stu-id="6e19d-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="6e19d-218">OneNote 支持在会议中进行协作的新方法。</span><span class="sxs-lookup"><span data-stu-id="6e19d-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="6e19d-219">在会议期间，用户可以使用 OneNote 做笔记，以便在会议后个人使用，或者与会议参与者实时使用共享笔记本和共同编辑会议参与者。</span><span class="sxs-lookup"><span data-stu-id="6e19d-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="6e19d-220">所有团队成员都可以访问共享笔记来参与信息、集体讨论创意或将笔记本页面用作虚拟白板。</span><span class="sxs-lookup"><span data-stu-id="6e19d-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="6e19d-221">会议中共享的人员和内容会自动添加到笔记中。</span><span class="sxs-lookup"><span data-stu-id="6e19d-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="6e19d-222">用户可以使用会议室底部的 "**共享内容" 和 "主持会议活动**" 在内容类型之间进行切换。</span><span class="sxs-lookup"><span data-stu-id="6e19d-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="6e19d-223">用户还可以使用 "**管理可演示内容**" 菜单选择要共享的内容。</span><span class="sxs-lookup"><span data-stu-id="6e19d-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e19d-224">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e19d-224">See Also</span></span>


[<span data-ttu-id="6e19d-225">在 Lync Server 2013 中规划客户端</span><span class="sxs-lookup"><span data-stu-id="6e19d-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

