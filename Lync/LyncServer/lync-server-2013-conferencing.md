---
title: Lync Server 2013 会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3f2a27e252a3e152958a45d53794216308be68e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="a74c7-102">Lync Server 2013 中的会议</span><span class="sxs-lookup"><span data-stu-id="a74c7-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a74c7-103">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="a74c7-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="a74c7-104">借助 Lync Server 2013 中的统一会议，用户可以进行协作、共享信息，并实时协调其努力。</span><span class="sxs-lookup"><span data-stu-id="a74c7-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="a74c7-105">所有用户都可以使用广泛的自发协作、预定会议和会议工具。</span><span class="sxs-lookup"><span data-stu-id="a74c7-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="a74c7-106">可以从任何有 Internet 连接的位置使用语音和视频会议功能，不在计算机旁边的用户可以通过公用电话交换网 (PSTN ) 电话拨入来参加音频会议。</span><span class="sxs-lookup"><span data-stu-id="a74c7-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="a74c7-107">在 Outlook 中集成的会议工具使组织者能够通过一次单击安排会议或启动即席会议，同时使与会者更容易加入。</span><span class="sxs-lookup"><span data-stu-id="a74c7-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="a74c7-108">Web 客户端将丰富的会议功能扩展到未运行桌面版 Lync 的参与者。</span><span class="sxs-lookup"><span data-stu-id="a74c7-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="a74c7-109">音频和视频会议</span><span class="sxs-lookup"><span data-stu-id="a74c7-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="a74c7-110">Lync Server 提供了传统音频桥接服务用户熟悉的用户体验，其中包括带有触摸音呼叫控制命令的 PSTN 电话拨入式服务。</span><span class="sxs-lookup"><span data-stu-id="a74c7-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="a74c7-111">同时，还融合了仅由集成的统一通信平台提供的强大的安排、加入和管理功能。</span><span class="sxs-lookup"><span data-stu-id="a74c7-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="a74c7-112">通过一次单击，用户可以从 Outlook 安排会议。</span><span class="sxs-lookup"><span data-stu-id="a74c7-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="a74c7-113">详细信息，如会议时间、位置和与会者，请遵循熟悉的 Outlook 模板。</span><span class="sxs-lookup"><span data-stu-id="a74c7-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="a74c7-114">此外，还会自动填充特定于电话会议的信息，如拨入号码、会议 ID 和个人标识号 (PIN) 提醒。</span><span class="sxs-lookup"><span data-stu-id="a74c7-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="a74c7-115">为了帮助确保只有授权用户参与呼叫，Lync Server 为参与者提供了多个级别的身份验证。</span><span class="sxs-lookup"><span data-stu-id="a74c7-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="a74c7-116">通过使用 Lync 加入的用户已通过 Active Directory 域服务进行身份验证，无需输入 PIN、传递代码或会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a74c7-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="a74c7-117">Lync 通过将视频集成到统一客户端来简化视频会议用户体验，以便通过视频或快速升级到视频来安排会议，并无缝轻松。</span><span class="sxs-lookup"><span data-stu-id="a74c7-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="a74c7-118">Lync Server 使您只需单击一次即可轻松地将视频添加到标准电话呼叫中。</span><span class="sxs-lookup"><span data-stu-id="a74c7-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="a74c7-119">当视频呼叫或会议中有多个参与者时，每个用户最多能同时观看来自五个其他用户的视频，或者演示者只能选择一个要被所有人以独占方式观看的视频源。</span><span class="sxs-lookup"><span data-stu-id="a74c7-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="a74c7-120">对于在高端计算机上运行 Lync 的用户之间的对等呼叫，支持高清晰度视频（分辨率 1270 x 720; 纵横比16:9）和 VGA 视频（分辨率 640 x 480; 纵横比4:3）。</span><span class="sxs-lookup"><span data-stu-id="a74c7-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="a74c7-121">单次对话中每个参与者所查看的分辨率可能有所不同，具体取决于每个用户的相应硬件的视频功能。</span><span class="sxs-lookup"><span data-stu-id="a74c7-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="a74c7-p108">IT 管理员可以设置策略，限制或禁止在客户端上使用高清或 VGA 视频，具体取决于计算机功能、网络带宽以及可提供所需分辨率的摄像机的状态。通过带内设置实施这些策略。</span><span class="sxs-lookup"><span data-stu-id="a74c7-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="a74c7-124">Web 会议</span><span class="sxs-lookup"><span data-stu-id="a74c7-124">Web conferencing</span></span>

<span data-ttu-id="a74c7-125">Lync Server 将会议共享功能（如桌面、应用程序、附件、白板、投票和 PowerPoint）集成到简化的 Lync 中。</span><span class="sxs-lookup"><span data-stu-id="a74c7-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="a74c7-126">通过与音频或视频会议结合使用，会话变得更加生动，协作更加顺畅。</span><span class="sxs-lookup"><span data-stu-id="a74c7-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="a74c7-127">为了改进演示或查看 PowerPoint 演示文稿的用户的整体体验，Lync Server 2013 使用 Office Web Apps 来处理 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="a74c7-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="a74c7-128">用户可以在 Lync 会议中使用白板共享图片或复制和粘贴文本。</span><span class="sxs-lookup"><span data-stu-id="a74c7-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="a74c7-129">演示者可以在 Lync 会议中进行轮询，以征求与会者的反馈意见。</span><span class="sxs-lookup"><span data-stu-id="a74c7-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="a74c7-130">桌面共享使演示者能够实时将任何视觉对象、应用程序、网页、文档、软件或桌面的一部分广播到远程参与者，从 Lync 直接广播。</span><span class="sxs-lookup"><span data-stu-id="a74c7-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="a74c7-131">观众成员可以通过鼠标移动和键盘输入予以跟进。</span><span class="sxs-lookup"><span data-stu-id="a74c7-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="a74c7-132">演示者可以选择共享整个屏幕或仅共享部分屏幕。</span><span class="sxs-lookup"><span data-stu-id="a74c7-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="a74c7-133">通过共享桌面，演示者可以从任何位置与其受众进行产品或软件互动演示。</span><span class="sxs-lookup"><span data-stu-id="a74c7-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="a74c7-p112">应用程序共享使演示者可以共享其桌面上的软件的控制权，同时还可兼顾参与者的反馈或文本问题。演示者还可以将应用程序的控制权委派给会议参与者。</span><span class="sxs-lookup"><span data-stu-id="a74c7-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="a74c7-136">电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="a74c7-136">Dial-in Conferencing</span></span>

<span data-ttu-id="a74c7-137">对于没有使用个人计算机的用户，有几种方法可用于加入 Lync Server 会议呼叫。</span><span class="sxs-lookup"><span data-stu-id="a74c7-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="a74c7-138">PSTN 用户可以拨打访问号码，访问会议桥，然后输入会议 ID。</span><span class="sxs-lookup"><span data-stu-id="a74c7-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="a74c7-139">对于安全性更高的会议，还可以要求用户输入其 PIN 以针对 Active Directory 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a74c7-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="a74c7-140">Lync Server 还支持 Lync Phone Edition 设备，这是由 Microsoft 合作伙伴提供的独立 IP 电话设备。</span><span class="sxs-lookup"><span data-stu-id="a74c7-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

