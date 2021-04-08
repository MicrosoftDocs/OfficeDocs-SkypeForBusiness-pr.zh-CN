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
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>帮助 EDU 解决 Teams 低带宽问题

使用 Microsoft Teams 时，很多网络元素可能会影响性能。 低带宽是完全无法掌控的情况之一。 请考虑以下情况:

- 学校的低速 Internet 连接。
- 一名或多名学生的低速 Internet 连接。
- 由于区域中网络使用情况，带宽较低时一天中的一个时间。
- 由于既不属于学校也不属于学生的中断而导致的低带宽时段，但仍会影响性能。
- 伪装成低带宽问题的非带宽问题 (例如，硬件问题)。

本文将提供各种 Teams 活动在面临低带宽问题时应遵循的最佳实践。

> [!IMPORTANT]
> 另请参阅 [Microsoft Teams 如何使用内存](teams-memory-usage-perf.md)，因为除了低带宽问题之外，你的设备可能还存在资源问题。 如果在查找 Microsoft Teams 网络指南，请参阅[准备组织网络以使用 Microsoft Teams](prepare-network.md)。

## <a name="resolving-low-bandwidth-issues-for-admins"></a>解决管理员的低带宽问题

作为 IT 管理员，需要记住的重要一点就是，虽然提供了可快速解决问题的低带宽问题的解决方案，但应仔细考虑解决方案。 某些问题可能可以通过在教育者甚至学生/家长层面采取更集中的关注来解决。

简而言之，如果低带宽问题发生在广大学生群体中，或者如果在学生/教师级别采取的措施没有效果，最好以 IT 管理员身份采取措施。

> [!NOTE]
> 如果你有足够的时间，[体验质量审阅指南](quality-of-experience-review-guide.md)是值得一读的（虽然这不是特定于 EDU 的，但仍包含有价值的信息）。 这本指南可以让经验丰富的 IT 管理员深入了解教师和学生的体验。

### <a name="meetings-and-video"></a>会议和视频

低带宽问题的主要关注点是会议; 特别是会议中的视频。 信息技术管理员在处理学生或教育工作者报告的有关在教育环境中获得最佳会议体验的问题时，应考虑以下措施。

#### <a name="meeting-policies"></a>会议策略

关于会议，低带宽情况下最令人担忧的领域之一就是视频。 除了 Teams 能够自动扩展到检测到的带宽之外，作为 IT 管理员还可以在每个组织者和/或每个用户级别设置策略选项。 这些选项允许你根据每个人在特定时间必须使用的带宽，提供最好的体验。

可通过策略设置的一些选项包括：

- 完全禁用视频，任何人都无法启用它。
- 媒体位率 (此设置按用户设置)。

若要详细了解你的选项，以及你需要为会议和视频设置哪些策略，请参阅 [Teams 中的会议策略设置: 音频和视频](meeting-policies-audio-and-video.md)。

#### <a name="screen-sharing-policies"></a>屏幕共享策略

在其他情况下，教师可能会与学生共享整个屏幕，而共享应该仅限于与正在教授的课程相关的应用程序。 如果这是比让教育者单独做出这种选择更理想的方式，这也可以通过策略来设定.

若要详细了解如何通过策略设置来限制屏幕共享，请参阅 [Teams 中的会议策略设置: 音频和视频](meeting-policies-audio-and-video.md)。

#### <a name="dial-in-number-for-meetings"></a>会议拨入号码

对一些学生来说，尝试拨入一些课堂会话可能会更容易些。 可以提供 Teams 会议的拨入号码，这样遇到问题的学生可以打电话进来，而不是参加视频会议。

有关详细信息，请参阅[在 Microsoft Teams 中设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="low-bandwidth-scenarios-as-an-educator"></a>作为教师的低带宽应用场景

教师应感到有能力采取措施来解决低带宽问题，在以下情况下，这可能是比 IT 管理员采取措施更好的选择：

- 问题是间歇性的，或相对短暂。
- 可以预测在一天中的某个特定时间会出现问题，或低带宽时段有一定的可预测性。

在这些情况下，你可以采取一些措施。

有关详细信息，请参阅[在低带宽时使用 Teams 完成课业](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>作为家长/学生的低带宽应用场景

也有一些情况，你应该主动与教师讨论，因为带宽问题可能出在学生这边（例如，很多学生能够顺利观看视频课程，但少数学生遇到问题）。

期望许多家长能够解决这些问题并不合理。 低带宽问题可能是学生或家长无法控制的 (他们的家庭可能无法获得高带宽，他们可能在其附近地区有许多人消耗带宽并影响他们可以做的事情，可能存在网络不稳定等)。

我们也已将面向家长和学生的指南归入[在低带宽时使用 Teams 完成课业](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)一文中；如果你有任何问题，可以查看并尝试其中的建议。