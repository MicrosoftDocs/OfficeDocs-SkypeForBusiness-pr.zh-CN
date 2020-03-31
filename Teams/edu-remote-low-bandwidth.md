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
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>帮助 EDU 解决 Teams 低带宽问题

使用 Microsoft Teams 时，有许多网络因素可能会影响性能，而低带宽就是一种让人感觉完全无法控制的因素。 比如以下几种情况：

- 学校的低速 Internet 连接。
- 一名或多名学生的低速 Internet 连接。
- 一天中某个地区由于网络使用而出现低带宽的时间。
- 由于既不属于学校也不属于学生的中断而导致的低带宽时段，但仍会影响性能。
- 伪装成低带宽问题的非带宽问题（例如，硬件问题）。

本文介绍了在面临低带宽问题时对各种 Teams 活动遵循的最佳做法。

> [!IMPORTANT]
> 另请参阅 [Microsoft Teams 如何使用内存](teams-memory-usage-perf.md)，因为除了低带宽问题之外，你的设备可能还存在资源问题。 如果在查找 Microsoft Teams 网络指南，请参阅[准备组织网络以使用 Microsoft Teams](prepare-network.md)。

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>作为 IT 管理员解决低带宽问题

作为 IT 管理员，请务必注意，虽然有可以迅速解决广泛低带宽问题的解决方案，但应仔细考虑这一点，因为一些问题可以通过更加重点关注教师或学生/家长级别来解决。

简而言之，如果低带宽问题发生在广大学生群体中，或者如果在学生/教师级别采取的措施没有效果，最好以 IT 管理员身份采取措施。

> [!NOTE]
> 如果你有足够的时间，[体验质量审阅指南](quality-of-experience-review-guide.md)是值得一读的（虽然这不是特定于 EDU 的，但仍包含有价值的信息）。 这样，经验丰富的 IT 管理员可以深入了解教师和学生的体验。

### <a name="meetings-and-video"></a>会议和视频

低带宽问题主要集中在会议上，尤其是会议中的视频。 在处理学生或教师报告的导致无法在教育环境中获得最佳会议体验的问题时，IT 管理员应考虑采取下面的一些措施。

#### <a name="meeting-policies"></a>会议策略

在会议方面，对于低带宽问题，最令人担忧的领域之一是视频。 幸运的是，除了 Teams 能够自动缩放到检测到的带宽以外，你作为 IT 管理员还可以在每组织者和/或每用户级别设置策略选项，以根据每个人在给定时间内需要使用的带宽让他们获得最佳体验。

可通过策略设置的一些选项包括：

- 完全禁用视频，任何人都无法启用它。
- 媒体比特率（每用户设置）。

若要详细了解你的选项，以及你需要为会议和视频设置哪些策略，请参阅 [Teams 中的会议策略设置：音频和视频](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)，以获取详细的演练信息。

#### <a name="screen-sharing-policies"></a>屏幕共享策略

在其他情况下，教师可能会与学生共享整个屏幕，而共享应该仅限于与正在教授的课程相关的应用程序。 这也可以通过策略设置，如果这样做比让教师自己做出选择更可取的话。

若要详细了解如何通过策略设置来限制屏幕共享，请参阅 [Teams 中的会议策略设置：屏幕共享](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video)。

#### <a name="dial-in-number-for-meetings"></a>会议拨入号码

对一些学生来说，尝试拨入一些课堂会话可能会更容易些。 可以提供 Teams 会议的拨入号码，这样遇到问题的学生可以打电话进来，而不是参加视频会议。

有关详细信息，请参阅[在 Microsoft Teams 中设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="low-bandwidth-scenarios-as-an-educator"></a>作为教师解决低带宽问题

教师应感到有能力采取措施来解决低带宽问题，在以下情况下，这可能是比 IT 管理员采取措施更好的选择：

- 问题是间歇性的，或相对短暂。
- 可以预测在一天中的某个特定时间会出现问题，或低带宽时段有一定的可预测性。

在这些情况下，你可以采取一些措施。

有关详细信息，请参阅[在低带宽时使用 Teams 完成课业](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>作为家长/学生解决低带宽问题

也有一些情况，你应该主动与教师讨论，因为带宽问题可能出在学生这边（例如，很多学生能够顺利观看视频课程，但少数学生遇到问题）。

期望许多家长能够排查这些问题是不合理的，低带宽问题可能超出了学生或家长的控制范围（他们家中可能没有高带宽；附近地区可能有很多人在消耗带宽，并对他们的操作产生影响；可能会出现 Internet 不稳定等情况）。

我们也已将面向家长和学生的指南归入[在低带宽时使用 Teams 完成课业](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)一文中；如果你有任何问题，可以查看并尝试其中的建议。
