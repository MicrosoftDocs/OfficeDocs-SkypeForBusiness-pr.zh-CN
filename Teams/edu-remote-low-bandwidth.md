---
title: 适用于 EDU 的 Microsoft Teams 低带宽指南
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: 适用于 EDU 的 Microsoft Teams 文章，有助于解决与低带宽相关的会议和视频问题。 无论你是家长、教师，还是 IT 管理员，都可以选择提升 Teams 体验。
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
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034063"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="3059a-104">帮助 EDU 解决 Teams 低带宽问题</span><span class="sxs-lookup"><span data-stu-id="3059a-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="3059a-105">使用 Microsoft Teams 时，有许多网络因素可能会影响性能，而低带宽就是一种让人感觉完全无法控制的因素。</span><span class="sxs-lookup"><span data-stu-id="3059a-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="3059a-106">比如以下几种情况：</span><span class="sxs-lookup"><span data-stu-id="3059a-106">Consider the following:</span></span>

- <span data-ttu-id="3059a-107">学校的低速 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="3059a-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="3059a-108">一名或多名学生的低速 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="3059a-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="3059a-109">一天中某个地区由于网络使用而出现低带宽的时间。</span><span class="sxs-lookup"><span data-stu-id="3059a-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="3059a-110">由于既不属于学校也不属于学生的中断而导致的低带宽时段，但仍会影响性能。</span><span class="sxs-lookup"><span data-stu-id="3059a-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="3059a-111">伪装成低带宽问题的非带宽问题（例如，硬件问题）。</span><span class="sxs-lookup"><span data-stu-id="3059a-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="3059a-112">本文介绍了在面临低带宽问题时对各种 Teams 活动遵循的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3059a-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3059a-113">另请参阅 [Microsoft Teams 如何使用内存](teams-memory-usage-perf.md)，因为除了低带宽问题之外，你的设备可能还存在资源问题。</span><span class="sxs-lookup"><span data-stu-id="3059a-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="3059a-114">如果在查找 Microsoft Teams 网络指南，请参阅[准备组织网络以使用 Microsoft Teams](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="3059a-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="3059a-115">作为 IT 管理员解决低带宽问题</span><span class="sxs-lookup"><span data-stu-id="3059a-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="3059a-116">作为 IT 管理员，请务必注意，虽然有可以迅速解决广泛低带宽问题的解决方案，但应仔细考虑这一点，因为一些问题可以通过更加重点关注教师或学生/家长级别来解决。</span><span class="sxs-lookup"><span data-stu-id="3059a-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="3059a-117">简而言之，如果低带宽问题发生在广大学生群体中，或者如果在学生/教师级别采取的措施没有效果，最好以 IT 管理员身份采取措施。</span><span class="sxs-lookup"><span data-stu-id="3059a-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="3059a-118">如果你有足够的时间，[体验质量审阅指南](quality-of-experience-review-guide.md)是值得一读的（虽然这不是特定于 EDU 的，但仍包含有价值的信息）。</span><span class="sxs-lookup"><span data-stu-id="3059a-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="3059a-119">这样，经验丰富的 IT 管理员可以深入了解教师和学生的体验。</span><span class="sxs-lookup"><span data-stu-id="3059a-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="3059a-120">会议和视频</span><span class="sxs-lookup"><span data-stu-id="3059a-120">Meetings and video</span></span>

<span data-ttu-id="3059a-121">低带宽问题主要集中在会议上，尤其是会议中的视频。</span><span class="sxs-lookup"><span data-stu-id="3059a-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="3059a-122">在处理学生或教师报告的导致无法在教育环境中获得最佳会议体验的问题时，IT 管理员应考虑采取下面的一些措施。</span><span class="sxs-lookup"><span data-stu-id="3059a-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="3059a-123">会议策略</span><span class="sxs-lookup"><span data-stu-id="3059a-123">Meeting policies</span></span>

<span data-ttu-id="3059a-124">在会议方面，对于低带宽问题，最令人担忧的领域之一是视频。</span><span class="sxs-lookup"><span data-stu-id="3059a-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="3059a-125">幸运的是，除了 Teams 能够自动缩放到检测到的带宽以外，你作为 IT 管理员还可以在每组织者和/或每用户级别设置策略选项，以根据每个人在给定时间内需要使用的带宽让他们获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="3059a-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="3059a-126">可通过策略设置的一些选项包括：</span><span class="sxs-lookup"><span data-stu-id="3059a-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="3059a-127">完全禁用视频，任何人都无法启用它。</span><span class="sxs-lookup"><span data-stu-id="3059a-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="3059a-128">媒体比特率（每用户设置）。</span><span class="sxs-lookup"><span data-stu-id="3059a-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="3059a-129">若要详细了解你的选项，以及你需要为会议和视频设置哪些策略，请参阅 [Teams 中的会议策略设置：音频和视频](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)，以获取详细的演练信息。</span><span class="sxs-lookup"><span data-stu-id="3059a-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="3059a-130">屏幕共享策略</span><span class="sxs-lookup"><span data-stu-id="3059a-130">Screen sharing policies</span></span>

<span data-ttu-id="3059a-131">在其他情况下，教师可能会与学生共享整个屏幕，而共享应该仅限于与正在教授的课程相关的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3059a-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="3059a-132">这也可以通过策略设置，如果这样做比让教师自己做出选择更可取的话。</span><span class="sxs-lookup"><span data-stu-id="3059a-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="3059a-133">若要详细了解如何通过策略设置来限制屏幕共享，请参阅 [Teams 中的会议策略设置：屏幕共享](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)。</span><span class="sxs-lookup"><span data-stu-id="3059a-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="3059a-134">会议拨入号码</span><span class="sxs-lookup"><span data-stu-id="3059a-134">Dial-in number for meetings</span></span>

<span data-ttu-id="3059a-135">对一些学生来说，尝试拨入一些课堂会话可能会更容易些。</span><span class="sxs-lookup"><span data-stu-id="3059a-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="3059a-136">可以提供 Teams 会议的拨入号码，这样遇到问题的学生可以打电话进来，而不是参加视频会议。</span><span class="sxs-lookup"><span data-stu-id="3059a-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="3059a-137">有关详细信息，请参阅[在 Microsoft Teams 中设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3059a-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="3059a-138">作为教师解决低带宽问题</span><span class="sxs-lookup"><span data-stu-id="3059a-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="3059a-139">教师应感到有能力采取措施来解决低带宽问题，在以下情况下，这可能是比 IT 管理员采取措施更好的选择：</span><span class="sxs-lookup"><span data-stu-id="3059a-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="3059a-140">问题是间歇性的，或相对短暂。</span><span class="sxs-lookup"><span data-stu-id="3059a-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="3059a-141">可以预测在一天中的某个特定时间会出现问题，或低带宽时段有一定的可预测性。</span><span class="sxs-lookup"><span data-stu-id="3059a-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="3059a-142">在这些情况下，你可以采取一些措施。</span><span class="sxs-lookup"><span data-stu-id="3059a-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="3059a-143">有关详细信息，请参阅[在低带宽时使用 Teams 完成课业](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。</span><span class="sxs-lookup"><span data-stu-id="3059a-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="3059a-144">作为家长/学生解决低带宽问题</span><span class="sxs-lookup"><span data-stu-id="3059a-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="3059a-145">也有一些情况，你应该主动与教师讨论，因为带宽问题可能出在学生这边（例如，很多学生能够顺利观看视频课程，但少数学生遇到问题）。</span><span class="sxs-lookup"><span data-stu-id="3059a-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="3059a-146">期望许多家长能够排查这些问题是不合理的，低带宽问题可能超出了学生或家长的控制范围（他们家中可能没有高带宽；附近地区可能有很多人在消耗带宽，并对他们的操作产生影响；可能会出现 Internet 不稳定等情况）。</span><span class="sxs-lookup"><span data-stu-id="3059a-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="3059a-147">我们也已将面向家长和学生的指南归入[在低带宽时使用 Teams 完成课业](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)一文中；如果你有任何问题，可以查看并尝试其中的建议。</span><span class="sxs-lookup"><span data-stu-id="3059a-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>
