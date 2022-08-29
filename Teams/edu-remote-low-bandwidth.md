---
title: 排查 Teams 的低带宽方案
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: 获取有关 Teams 中低带宽问题的会议和视频问题的帮助。 无论你是家长、教师还是 IT 管理员，都有改进 Teams 体验的选项。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f60095f20d62ed14b19d7c23493553efc39b872
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426809"
---
# <a name="troubleshoot-low-bandwidth-scenarios-for-teams"></a>排查 Teams 的低带宽方案

本文将为 IT 管理员提供处理 Teams 中低带宽问题的最佳做法。

使用 Microsoft Teams 时，许多网络元素可能会影响性能。

- 学校的低速 Internet 连接。
- 一个或多个学生的低速 Internet 连接。
- 由于区域中网络使用情况，带宽较低时一天中的一个时间。
- 中断不是学校或学生的本地服务，而是影响性能。
- 导致低带宽问题的硬件问题。

> [!IMPORTANT]
> 阅读 [Microsoft Teams 如何将内存](teams-memory-usage-perf.md) 用于设备上的资源限制。
>
>有关 Teams 网络指南，请参阅 [为 Microsoft Teams 准备组织的网络](prepare-network.md)。

## <a name="resolving-low-bandwidth-issues-for-it-admins"></a>解决 IT 管理员的低带宽问题

某些问题可能仅在单个用户级别以狭窄的焦点解决。

如果许多用户出现带宽问题，或者在用户级别执行的操作没有帮助，则学校范围的操作是下一步。

> [!NOTE]
> 还可以阅读 [体验质量评审指南](quality-of-experience-review-guide.md)。 它不特定于 EDU，但具有有价值的信息。

### <a name="meetings-and-video"></a>会议和视频

处理与低网络带宽相关的会议问题时，请考虑以下操作。

#### <a name="meeting-video-policies"></a>会议视频策略

Teams 会自动将会议质量缩放到用户检测到的带宽。 但是，可以设置进一步的限制来保留带宽。

可以通过策略设置的一些限制包括：

- 完全关闭视频，以便没有人可以使用视频。
- 限制按用户设置的媒体位速率。

有关应为会议和视频设置的更多策略，请阅读 [Teams 中的会议策略设置：音频和视频](meeting-policies-audio-and-video.md)。

#### <a name="screen-sharing-policies"></a>屏幕共享策略

在 Teams 中，用户可以共享其整个屏幕或单个窗口。

共享整个屏幕比仅仅共享窗口使用更多的带宽。

- 限制用户通过策略共享其整个屏幕。
- 指示教师仅共享应用程序，而不是整个屏幕。

了解 [Teams 中会议策略设置中的屏幕共享策略：音频和视频](meeting-policies-audio-and-video.md)。

#### <a name="dial-in-number-for-meetings"></a>会议拨入号码

某些学生可以更轻松地拨入课堂课程。

- 提供 Teams 会议的电话拨入号码，作为参加视频会议的替代方法。

有关详细信息，请参阅 [“设置 Microsoft Teams 中邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)”。

## <a name="low-bandwidth-scenarios-as-an-educator"></a>作为教师的低带宽应用场景

在以下情况下，让教师排查带宽问题可能比 IT 操作更好的选择：

- 问题是间歇性的。
- 有一天中的特定时间，你可以预料到有问题。

对于教师可以采取的解决带宽问题的步骤，请在 [带宽较低时阅读“使用 Teams”进行学校工作](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262)。

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>作为家长/学生的低带宽应用场景

有时带宽问题就站在学生一边。

- 他们的家可能无法获得高带宽。
- 他们可能有很多人在他们的直接区域也消耗带宽。
- 可能存在互联网不稳定。

当家长和学生的 [带宽较低时，我们已在“使用团队”中为学校工作](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) 整理了指导。
