---
title: 适用于 EDU 的 Microsoft Teams 低带宽指南
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: 适用于 EDU 的 Microsoft Teams 文章，有助于解决与低带宽相关的会议和视频问题。 无论你是家长、教师，还是 IT 管理员，都可以选择改善 Teams 体验。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17520645f23500550c6bc991c9d25ad2f72b2b6e
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598421"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="8b3fc-104">帮助 EDU 解决 Teams 低带宽问题</span><span class="sxs-lookup"><span data-stu-id="8b3fc-104">Help for low-bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="8b3fc-105">使用 Microsoft Teams 时，很多网络元素可能会影响性能。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-105">There are numerous network elements when it comes to working with Microsoft Teams that can affect performance.</span></span> <span data-ttu-id="8b3fc-106">低带宽是完全无法掌控的情况之一。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-106">Low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="8b3fc-107">请考虑以下情况:</span><span class="sxs-lookup"><span data-stu-id="8b3fc-107">Consider the following situations:</span></span>

- <span data-ttu-id="8b3fc-108">学校的低速 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-108">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="8b3fc-109">一名或多名学生的低速 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-109">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="8b3fc-110">由于区域中网络使用情况，带宽较低时一天中的一个时间。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-110">Times of the day when there's low bandwidth because of network usage in an area.</span></span>
- <span data-ttu-id="8b3fc-111">由于既不属于学校也不属于学生的中断而导致的低带宽时段，但仍会影响性能。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-111">Low-bandwidth periods because of outages local to neither the school nor to students, but, which affect performance nonetheless.</span></span>
- <span data-ttu-id="8b3fc-112">伪装成低带宽问题的非带宽问题 (例如，硬件问题)。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-112">Non-bandwidth issues (for example, issues with hardware) that masquerade as low-bandwidth issues.</span></span>

<span data-ttu-id="8b3fc-113">本文将提供各种 Teams 活动在面临低带宽问题时应遵循的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-113">This article will give you best practices to follow for various Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b3fc-114">另请参阅 [Microsoft Teams 如何使用内存](teams-memory-usage-perf.md)，因为除了低带宽问题之外，你的设备可能还存在资源问题。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-114">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="8b3fc-115">如果在查找 Microsoft Teams 网络指南，请参阅[准备组织网络以使用 Microsoft Teams](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-115">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-admins"></a><span data-ttu-id="8b3fc-116">解决管理员的低带宽问题</span><span class="sxs-lookup"><span data-stu-id="8b3fc-116">Resolving low-bandwidth issues for Admins</span></span>

<span data-ttu-id="8b3fc-117">作为 IT 管理员，需要记住的重要一点就是，虽然提供了可快速解决问题的低带宽问题的解决方案，但应仔细考虑解决方案。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-117">The important thing to remember, as an IT Admin, is that while you have solutions for low-bandwidth issues that are wide-spread that will resolve problems quickly, solutions should be considered carefully.</span></span> <span data-ttu-id="8b3fc-118">某些问题可能可以通过在教育者甚至学生/家长层面采取更集中的关注来解决。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-118">Some issues may be able to resolve with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="8b3fc-119">简而言之，如果低带宽问题发生在广大学生群体中，或者如果在学生/教师级别采取的措施没有效果，最好以 IT 管理员身份采取措施。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-119">In short, if the low-bandwidth issue occurs for a wide group of students, taking action as an IT Admin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="8b3fc-120">如果你有足够的时间，[体验质量审阅指南](quality-of-experience-review-guide.md)是值得一读的（虽然这不是特定于 EDU 的，但仍包含有价值的信息）。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-120">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="8b3fc-121">这本指南可以让经验丰富的 IT 管理员深入了解教师和学生的体验。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-121">This guide will allow experienced IT Admins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="8b3fc-122">会议和视频</span><span class="sxs-lookup"><span data-stu-id="8b3fc-122">Meetings and video</span></span>

<span data-ttu-id="8b3fc-123">低带宽问题的主要关注点是会议; 特别是会议中的视频。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-123">A primary focus for low-bandwidth issues is meetings; specifically, video in meetings.</span></span> <span data-ttu-id="8b3fc-124">信息技术管理员在处理学生或教育工作者报告的有关在教育环境中获得最佳会议体验的问题时，应考虑以下措施。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-124">An IT Admin should consider the actions below when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="8b3fc-125">会议策略</span><span class="sxs-lookup"><span data-stu-id="8b3fc-125">Meeting policies</span></span>

<span data-ttu-id="8b3fc-126">关于会议，低带宽情况下最令人担忧的领域之一就是视频。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-126">Regarding meetings, one of the most concerning areas for low-bandwidth situations has to do with videos.</span></span> <span data-ttu-id="8b3fc-127">除了 Teams 能够自动扩展到检测到的带宽之外，作为 IT 管理员还可以在每个组织者和/或每个用户级别设置策略选项。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-127">In addition to Teams being able to scale to detected bandwidth automatically, you as an IT Admin have policy options you can set at the per-organizer and/or per-user level.</span></span> <span data-ttu-id="8b3fc-128">这些选项允许你根据每个人在特定时间必须使用的带宽，提供最好的体验。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-128">These options allow you to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="8b3fc-129">可通过策略设置的一些选项包括：</span><span class="sxs-lookup"><span data-stu-id="8b3fc-129">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="8b3fc-130">完全禁用视频，任何人都无法启用它。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-130">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="8b3fc-131">媒体位率 (此设置按用户设置)。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-131">Media bit rate (this setting is set per-user).</span></span>

<span data-ttu-id="8b3fc-132">若要详细了解你的选项，以及你需要为会议和视频设置哪些策略，请参阅 [Teams 中的会议策略设置: 音频和视频](meeting-policies-audio-and-video.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-132">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="8b3fc-133">屏幕共享策略</span><span class="sxs-lookup"><span data-stu-id="8b3fc-133">Screen sharing policies</span></span>

<span data-ttu-id="8b3fc-134">在其他情况下，教师可能会与学生共享整个屏幕，而共享应该仅限于与正在教授的课程相关的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-134">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="8b3fc-135">如果这是比让教育者单独做出这种选择更理想的方式，这也可以通过策略来设定.</span><span class="sxs-lookup"><span data-stu-id="8b3fc-135">This setting can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="8b3fc-136">若要详细了解如何通过策略设置来限制屏幕共享，请参阅 [Teams 中的会议策略设置: 音频和视频](meeting-policies-audio-and-video.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-136">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="8b3fc-137">会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="8b3fc-137">Dial-in number for meetings</span></span>

<span data-ttu-id="8b3fc-138">对一些学生来说，尝试拨入一些课堂会话可能会更容易些。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-138">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="8b3fc-139">可以提供 Teams 会议的拨入号码，这样遇到问题的学生可以打电话进来，而不是参加视频会议。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-139">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="8b3fc-140">有关详细信息，请参阅[在 Microsoft Teams 中设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-140">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="8b3fc-141">作为教师的低带宽应用场景</span><span class="sxs-lookup"><span data-stu-id="8b3fc-141">Low-bandwidth scenarios as an educator</span></span>

<span data-ttu-id="8b3fc-142">教师应感到有能力采取措施来解决低带宽问题，在以下情况下，这可能是比 IT 管理员采取措施更好的选择：</span><span class="sxs-lookup"><span data-stu-id="8b3fc-142">Educators should feel empowered to take steps to resolve low-bandwidth issues, and may be a superior choice to IT Admin action in the following situations:</span></span>

- <span data-ttu-id="8b3fc-143">问题是间歇性的，或相对短暂。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-143">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="8b3fc-144">可以预测在一天中的某个特定时间会出现问题，或低带宽时段有一定的可预测性。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-144">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="8b3fc-145">在这些情况下，你可以采取一些措施。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-145">In these situations, you can take some actions.</span></span>

<span data-ttu-id="8b3fc-146">有关详细信息，请参阅[在低带宽时使用 Teams 完成课业](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-146">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="8b3fc-147">作为家长/学生的低带宽应用场景</span><span class="sxs-lookup"><span data-stu-id="8b3fc-147">Low-bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="8b3fc-148">也有一些情况，你应该主动与教师讨论，因为带宽问题可能出在学生这边（例如，很多学生能够顺利观看视频课程，但少数学生遇到问题）。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-148">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="8b3fc-149">期望许多家长能够解决这些问题并不合理。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-149">It's not reasonable to expect many parents to be able to troubleshoot these issues.</span></span> <span data-ttu-id="8b3fc-150">低带宽问题可能是学生或家长无法控制的 (他们的家庭可能无法获得高带宽，他们可能在其附近地区有许多人消耗带宽并影响他们可以做的事情，可能存在网络不稳定等)。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-150">Low-bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have numerous people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="8b3fc-151">我们也已将面向家长和学生的指南归入[在低带宽时使用 Teams 完成课业](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)一文中；如果你有任何问题，可以查看并尝试其中的建议。</span><span class="sxs-lookup"><span data-stu-id="8b3fc-151">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>